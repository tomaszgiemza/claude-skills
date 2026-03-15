---
layout: with-comments
title: "Lekcja 3 – Automatyzacje przez API"
parent: "🚀 Kurs zaawansowany"
nav_order: 3
description: "Jak budować automatyzacje z Claude API – skrypty, webhooks, integracje z WordPress i przykłady produkcyjne."
permalink: /kurs-zaawansowany/lekcja-3/
---

# Lekcja 3 – Automatyzacje przez API

API to tam gdzie Claude staje się naprawdę potężny. Zamiast ręcznie pisać prompty, budujesz systemy które pracują za Ciebie.

## Architektura typowej automatyzacji

```
Trigger (event) → Dane → Claude API → Wynik → Akcja
```

Przykład:
```
Nowe zamówienie WooCommerce
↓
Pobierz dane zamówienia (PHP)
↓
Claude API: "Napisz spersonalizowany email potwierdzający dla..."
↓
Wyślij email przez SendGrid
↓
Zapisz do logu
```

## Praktyczny przykład – generator meta opisów

```php
<?php
// Uruchamiany przez cron co noc
// Dla wpisów bez meta opisu generuje jeden przez Claude

function giemza_generate_missing_meta_descriptions() {
    
    // Pobierz wpisy bez meta opisu (Rank Math)
    $posts = get_posts([
        'post_type'   => 'post',
        'post_status' => 'publish',
        'numberposts' => 10, // po 10 na raz
        'meta_query'  => [[
            'key'     => 'rank_math_description',
            'compare' => 'NOT EXISTS',
        ]]
    ]);
    
    foreach ($posts as $post) {
        $content  = wp_strip_all_tags(substr($post->post_content, 0, 1500));
        $keyword  = get_post_meta($post->ID, 'rank_math_focus_keyword', true);
        
        $meta_desc = giemza_call_claude_api(
            "Napisz meta opis SEO (max 155 znaków) dla artykułu.
            Słowo kluczowe: {$keyword}
            Treść: {$content}
            Odpowiedz TYLKO meta opisem."
        );
        
        if ($meta_desc && !is_wp_error($meta_desc)) {
            update_post_meta($post->ID, 'rank_math_description', $meta_desc);
        }
        
        // Pauza żeby nie przekroczyć limitu API
        sleep(1);
    }
}

// Uruchom przez WP-Cron
add_action('giemza_nightly_seo', 'giemza_generate_missing_meta_descriptions');
```

## Obsługa błędów i retry

W produkcji zawsze obsługuj błędy i ponów próbę:

```php
function giemza_call_claude_with_retry($prompt, $max_retries = 3) {
    for ($i = 0; $i < $max_retries; $i++) {
        $result = giemza_call_claude_api($prompt);
        
        if (!is_wp_error($result)) {
            return $result;
        }
        
        // Czekaj coraz dłużej przed kolejną próbą
        sleep(pow(2, $i)); // 1s, 2s, 4s
    }
    
    // Zaloguj błąd
    error_log('Claude API failed after ' . $max_retries . ' retries');
    return false;
}
```

{: .note }
Następna lekcja: [Agenty AI i MCP](/kurs-zaawansowany/lekcja-4/)
