---
layout: with-comments
title: "Claude API w PHP – integracja z WordPress"
parent: "🔌 Claude API"
nav_order: 2
description: "Jak używać Claude API w PHP – przykład integracji z WordPress, generowanie treści i analiza danych z wtyczki."
permalink: /api/przyklad-php/
---

# Claude API w PHP – WordPress

Pokażę jak zintegrować Claude API z WordPressem. Zbudujemy prostą funkcję która generuje meta opis dla wpisu.

## Instalacja biblioteki PHP

```bash
composer require anthropic-php/client
```

Lub ręcznie przez curl (bez Composera):

## Prosta funkcja z curl

```php
<?php
/**
 * Generuje meta opis dla wpisu używając Claude API
 * Umieść w functions.php lub własnej wtyczce
 */
function giemza_generate_meta_description($post_content, $focus_keyword) {
    
    $api_key = defined('ANTHROPIC_API_KEY') ? ANTHROPIC_API_KEY : '';
    
    if (empty($api_key)) {
        return new WP_Error('no_api_key', 'Brak klucza API Anthropic');
    }
    
    // Skróć treść do 2000 znaków
    $excerpt = wp_strip_all_tags(substr($post_content, 0, 2000));
    
    $request_body = json_encode([
        'model' => 'claude-haiku-4-5-20251001',
        'max_tokens' => 200,
        'messages' => [[
            'role' => 'user',
            'content' => "Na podstawie poniższej treści napisz meta opis SEO.
Słowo kluczowe: {$focus_keyword}
Wymagania: max 155 znaków, zawiera słowo kluczowe, zachęca do kliknięcia.
Odpowiedz TYLKO meta opisem, bez dodatkowego tekstu.

Treść:
{$excerpt}"
        ]]
    ]);
    
    $response = wp_remote_post('https://api.anthropic.com/v1/messages', [
        'headers' => [
            'x-api-key'         => $api_key,
            'anthropic-version' => '2023-06-01',
            'content-type'      => 'application/json',
        ],
        'body'    => $request_body,
        'timeout' => 30,
    ]);
    
    if (is_wp_error($response)) {
        return $response;
    }
    
    $body = json_decode(wp_remote_retrieve_body($response), true);
    
    if (isset($body['content'][0]['text'])) {
        return sanitize_text_field($body['content'][0]['text']);
    }
    
    return new WP_Error('api_error', 'Błąd API: ' . json_encode($body));
}
```

## Użycie w WordPress

```php
// W wp-config.php (poza public_html):
define('ANTHROPIC_API_KEY', 'sk-ant-api03-...');

// Użycie:
$post_id = get_the_ID();
$content = get_post_field('post_content', $post_id);
$keyword = 'instalacja wordpress';

$meta_desc = giemza_generate_meta_description($content, $keyword);

if (!is_wp_error($meta_desc)) {
    echo esc_html($meta_desc);
}
```

{: .warning }
Nigdy nie wklejaj klucza API bezpośrednio w kodzie PHP który może być dostępny publicznie. Używaj `define()` w `wp-config.php` który jest poza `public_html`.
