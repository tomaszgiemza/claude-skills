---
layout: with-comments
title: "🌐 Prompty – WordPress"
parent: "⚡ Prompty i skille"
nav_order: 2
description: "Gotowe prompty Claude do WordPress – GeneratePress, FSE, PHP snippety, CSS, wtyczki i konfiguracja strony."
permalink: /prompty/wordpress/
---

# Prompty – WordPress

## Snippet PHP do functions.php

```
Napisz snippet PHP do pliku functions.php WordPress.

Zadanie: [OPIS CO MA ROBIĆ]
Motyw: [NAZWA MOTYWU, np. GeneratePress]
WordPress: 6.5+
PHP: 8.2

Wymagania:
- Prefiks funkcji: [PREFIKS]_ (np. giemza_)
- Komentarze w kodzie po polsku
- Sanityzacja input i escapowanie output
- Sprawdzenie uprawnień current_user_can() jeśli dotyczy
- Nonce jeśli formularz

Dodaj na końcu: przykład użycia w szablonie.
```

## CSS dla GeneratePress

```
Napisz CSS dla motywu GeneratePress.

Zadanie: [CO CHCESZ ZMIENIĆ – opis wizualny]
Sekcja strony: [nagłówek / stopka / sidebar / treść / konkretny element]
Responsywność: tak, breakpoint mobile: 768px
Używaj zmiennych CSS GeneratePress jeśli możliwe (np. --color-primary)

Dodaj komentarze wyjaśniające każdy blok.
Nie używaj !important chyba że konieczne.
```

## Konfiguracja GeneratePress – strona firmowa

```
Jestem [OPIS FIRMY/KLIENTA].
Chcę skonfigurować stronę firmową na GeneratePress (darmowy).

Doradź mi:
1. Ustawienia Wygląd → Dostosuj → które opcje skonfigurować w jakiej kolejności
2. Które bezpłatne wtyczki dodać (maksymalnie 8 pozycji)
3. Strukturę stron (które strony stworzyć)
4. Jak ustawić menu główne
5. Pierwsze 3 kroki SEO do zrobienia od razu

Odpowiedz konkretnie, z nazwami opcji z panelu WordPress.
```

## Hook WooCommerce – customizacja

```
Napisz kod PHP używający hooków WooCommerce.

Zadanie: [OPIS – co chcesz zmienić w WooCommerce]
Gdzie: [np. strona produktu / koszyk / checkout / email / strona konta]
WordPress: 6.5, WooCommerce: 9.x

Użyj oficjalnych hooków WooCommerce (nie jQuery ani CSS do logiki).
Podaj nazwę hooka, priorytet i wyjaśnienie.
Dodaj przykład jak usunąć/wyłączyć ten hook jeśli potrzeba.
```

## Tworzenie child theme GeneratePress

```
Krok po kroku pomóż mi stworzyć child theme dla GeneratePress.

Moje umiejętności: [początkujący / średniozaawansowany / zaawansowany]
Co chcę zmienić: [LISTA zmian wizualnych lub funkcjonalnych]

Potrzebuję:
1. Strukturę plików child theme (jakie pliki stworzyć)
2. Zawartość style.css z nagłówkiem
3. Zawartość functions.php
4. Jak wgrać i aktywować przez cPanel/FTP

Pisz krok po kroku, zakładaj że używam cPanela.
```
