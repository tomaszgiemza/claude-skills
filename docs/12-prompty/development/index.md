---
layout: with-comments
title: "💻 Prompty – Development"
parent: "⚡ Prompty i skille"
nav_order: 5
description: "Gotowe prompty Claude do programowania – PHP, JavaScript, HTML/CSS, code review, debugowanie i dokumentacja."
permalink: /prompty/development/
---

# Prompty – Development

## Code Review PHP/WordPress

```
Zrób code review poniższego kodu PHP/WordPress.

Kontekst: [CO TEN KOD ROBI]
Stack: PHP [wersja], WordPress [wersja]

[WKLEJ KOD]

Oceń:
1. Bezpieczeństwo (SQL injection, XSS, CSRF, sanitize/escape)
2. Wydajność (niepotrzebne zapytania do bazy, brak cache)
3. Zgodność z WordPress Coding Standards
4. Czytelność i maintainability
5. Edge cases i potencjalne błędy

Format: lista z priorytetem KRYTYCZNE / WAŻNE / SUGESTIA.
Dla każdego problemu: co jest nie tak + jak naprawić (z kodem).
```

## Debugowanie błędu

```
Pomóż mi zdebugować błąd.

Środowisko: [PHP wersja / WordPress wersja / serwer]
Komunikat błędu: [DOKŁADNY KOMUNIKAT]
Stack trace: [WKLEJ]
Kontekst: [CO ROBIŁEM GDY WYSTĄPIŁ BŁĄD]

Kod który powoduje błąd:
[WKLEJ KOD]

Krok 1: Zdiagnozuj przyczynę (bez sugerowania fix – najpierw rozumiem problem).
Krok 2: Zaproponuj fix z wyjaśnieniem.
Krok 3: Jak przetestować że fix działa?
Krok 4: Jak uniknąć tego błędu w przyszłości?
```

## Pisanie funkcji JavaScript

```
Napisz funkcję JavaScript.

Zadanie: [OPIS CO MA ROBIĆ]
Input: [OPIS DANYCH WEJŚCIOWYCH + przykład]
Output: [OCZEKIWANY WYNIK + przykład]
Środowisko: [browser / Node.js / oba]
ES: [ES6+ / starszy]
Zależności: [czy możesz używać npm packages]

Wymagania:
- JSDoc komentarze
- Obsługa błędów / edge cases
- Unit test (jeśli dotyczy)
- Przykład użycia

Nie używaj zewnętrznych bibliotek jeśli nie potrzeba.
```

## HTML/CSS – komponent

```
Napisz komponent HTML/CSS.

Komponent: [OPIS WIZUALNY – co ma wyglądać]
Kontekst: [gdzie będzie użyty – WordPress / standalone / email]
Responsywność: tak, mobile-first
CSS: [vanilla CSS / Tailwind / BEM / inne]
Interakcja: [hover / click / animacja – jeśli dotyczy]

Wymagania:
- Semantyczny HTML5
- Dostępność (ARIA jeśli potrzeba, kontrast kolorów)
- Komentarze CSS wyjaśniające nie-oczywiste rzeczy
- Nie używaj inline styles

Daj mi: kod HTML + CSS + jak zintegrować z WordPress jeśli dotyczy.
```

## Dokumentacja – README.md

```
Napisz dokumentację README.md dla projektu.

Projekt: [NAZWA I OPIS]
Technologie: [STACK]
Typ: [wtyczka WP / motyw / skrypt / aplikacja]

Sekcje:
- Opis (2-3 zdania, co robi i dla kogo)
- Wymagania (wersje)
- Instalacja (krok po kroku)
- Konfiguracja (zmienne, ustawienia)
- Użycie z przykładami (code blocks)
- Hooks/Filters (jeśli WP plugin)
- Changelog
- Licencja

Format: Markdown, gotowy do wklejenia na GitHub.
```

---

## 🛠️ Skill do Claude Code – WordPress

Skopiuj poniższy plik jako `SKILL.md` do swojego projektu WordPress:

```markdown
---
name: wordpress-development
description: Tworzenie i modyfikacja kodu WordPress
---

# WordPress Development

## Stack
- WordPress 6.5+, PHP 8.2+, MySQL 8.0

## Zasady
- PSR-12 + WordPress Coding Standards
- Prefiks: [TWOJ_PREFIKS]_
- Sanitize input: sanitize_text_field(), absint(), wp_kses_post()
- Escape output: esc_html(), esc_attr(), esc_url()
- Nonces dla formularzy
- Sprawdzaj current_user_can() przed każdą akcją admina
- Nie edytuj core WordPress

## Enqueue assets
Zawsze przez wp_enqueue_scripts, nigdy inline.

## Baza danych
Zawsze $wpdb->prepare() dla własnych zapytań.
Dla standardowych – WP_Query lub get_posts().
```

📁 **Źródło na GitHub:** [tomaszgiemza/claude-skills](https://github.com/tomaszgiemza/claude-skills)
