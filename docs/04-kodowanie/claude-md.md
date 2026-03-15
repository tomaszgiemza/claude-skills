---
layout: with-comments
title: "CLAUDE.md – konfiguracja projektu"
parent: "💻 Claude i kodowanie"
nav_order: 3
description: "Czym jest plik CLAUDE.md, jak go skonfigurować i jakie instrukcje wpisać żeby Claude Code działał optymalnie w Twoim projekcie."
permalink: /kodowanie/claude-md/
---

# CLAUDE.md – konfiguracja projektu

To jeden z tych plików który robi ogromną różnicę a mało kto o nim wie.

## Czym jest CLAUDE.md?

`CLAUDE.md` to plik tekstowy w głównym katalogu projektu który Claude Code czyta automatycznie przy każdym uruchomieniu. To Twoje instrukcje dla Claude – kontekst projektu, zasady kodowania, struktura, stack technologiczny.

Bez CLAUDE.md Claude Code musi za każdym razem samodzielnie odkrywać projekt. Z CLAUDE.md wie od razu z czym ma do czynienia.

## Przykładowy CLAUDE.md dla projektu WordPress

```markdown
# Projekt: Sklep giemza.nl

## Stack technologiczny
- WordPress 6.5
- PHP 8.2
- MySQL 8.0
- Motyw: GeneratePress Premium (child theme)
- WooCommerce 9.x

## Struktura projektu
- /wp-content/themes/giemza-child/ ← aktywny child theme
- /wp-content/plugins/giemza-custom/ ← własna wtyczka
- Nie modyfikuj plików poza tymi katalogami

## Zasady kodowania
- PHP: PSR-12 + WordPress Coding Standards
- Komentarze: po polsku
- Nazwy funkcji i klas: przedrostek "giemza_"
- Zawsze sanityzuj input, escapuj output
- Używaj nonces dla formularzy

## Ważne informacje
- Środowisko deweloperskie: localhost:8080
- Produkcja: giemza.nl
- Backup przed każdą zmianą w bazie

## Czego NIE robić
- Nie edytuj plików core WordPress
- Nie używaj przestarzałych funkcji WP (sprawdź czy są deprecated)
- Nie commituj danych wrażliwych (.env, wp-config.php)
```

## Gdzie umieścić CLAUDE.md?

```
projekt/
├── CLAUDE.md          ← główne instrukcje
├── wp-content/
│   └── themes/
│       └── moj-motyw/
│           └── CLAUDE.md  ← opcjonalne, dla konkretnego modułu
```

## Co warto wpisać do CLAUDE.md?

1. **Stack technologiczny** – wersje, frameworki, biblioteki
2. **Strukturę projektu** – co jest gdzie i po co
3. **Zasady kodowania** – standardy, prefiksy, konwencje
4. **Czego NIE robić** – ograniczenia, pliki których nie ruszać
5. **Kontekst biznesowy** – dla kogo, jaki cel
6. **Środowisko** – dev vs produkcja, bazy danych, porty

{: .highlight }
Im więcej kontekstu dasz w CLAUDE.md, tym mniej będziesz powtarzał te same informacje w każdej rozmowie. Oszczędza czas i tokeny.

{: .note }
Następna strona: [Skille i MCP w Claude Code](/kodowanie/skille-mcp/)
