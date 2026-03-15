---
layout: default
title: "Skill – WordPress"
parent: "🛠️ Claude Code – skille"
nav_order: 1
description: "Publiczny skill do Claude Code dla WordPress – tworzenie wtyczek motywów funkcji PHP i snippetów z najlepszymi praktykami."
permalink: /claude-code-skille/wordpress/
---

# Skill – WordPress

Skopiuj poniższy kod do pliku `SKILL.md` w swoim projekcie WordPress.

## Pobierz skill

```bash
# Pobierz bezpośrednio
curl -o SKILL.md https://raw.githubusercontent.com/tomaszgiemza/claude-skills/main/skills/wordpress/SKILL.md
```

## Treść pliku SKILL.md

````markdown
---
name: wordpress
description: "Tworzenie i modyfikacja kodu WordPress – wtyczki, motywy, functions.php, hooks, shortcodes"
---

# WordPress Development Skill

## Stack
- WordPress 6.x
- PHP 8.1+
- MySQL 8.0
- Gutenberg Block Editor

## Zasady kodowania

### PHP
- Używaj PSR-12 + WordPress Coding Standards
- Zawsze sanityzuj input: `sanitize_text_field()`, `absint()`, `wp_kses_post()`
- Zawsze escapuj output: `esc_html()`, `esc_attr()`, `esc_url()`
- Używaj nonces dla formularzy: `wp_nonce_field()` / `wp_verify_nonce()`
- Prefixuj wszystkie funkcje, klasy i hooki: `prefix_function_name()`

### Hooki (Actions & Filters)
```php
// DOBRY pattern
add_action('init', 'prefix_init_function');
function prefix_init_function() {
    // kod
}

// Usuwanie hooków
remove_action('wp_head', 'wp_generator');
```

### Zapytania do bazy danych
```php
// ZAWSZE używaj $wpdb->prepare() dla własnych zapytań
global $wpdb;
$results = $wpdb->get_results(
    $wpdb->prepare(
        "SELECT * FROM {$wpdb->posts} WHERE post_author = %d",
        $user_id
    )
);

// Dla standardowych zapytań używaj WP_Query
$query = new WP_Query([
    'post_type' => 'post',
    'posts_per_page' => 10,
    'meta_key' => '_featured',
    'meta_value' => '1',
]);
```

### Enqueue scripts/styles
```php
// ZAWSZE używaj wp_enqueue_scripts, nigdy <script> w template
add_action('wp_enqueue_scripts', 'prefix_enqueue_assets');
function prefix_enqueue_assets() {
    wp_enqueue_style(
        'prefix-style',
        get_stylesheet_uri(),
        [],
        wp_get_theme()->get('Version')
    );
    
    wp_enqueue_script(
        'prefix-script',
        get_template_directory_uri() . '/js/main.js',
        ['jquery'],
        '1.0.0',
        true // w stopce
    );
}
```

## Struktura wtyczki
```
my-plugin/
├── my-plugin.php          ← główny plik z headerem
├── includes/
│   ├── class-main.php     ← główna klasa
│   ├── class-admin.php    ← panel admina
│   └── class-frontend.php ← frontend
├── admin/
│   ├── css/
│   └── js/
├── public/
│   ├── css/
│   └── js/
└── README.md
```

## Bezpieczeństwo – checklist
- [ ] Sanityzacja wszystkich inputów
- [ ] Escapowanie wszystkich outputów
- [ ] Nonces dla formularzy i AJAX
- [ ] Sprawdzanie uprawnień: `current_user_can()`
- [ ] Ochrona bezpośredniego dostępu: `if (!defined('ABSPATH')) exit;`
- [ ] Przygotowane zapytania SQL
````
