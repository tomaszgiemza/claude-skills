---
layout: default
title: "Repozytoria promptów i skilli"
parent: "🔗 Przydatne repozytoria"
nav_order: 3
description: "Najlepsze repozytoria GitHub z promptami i skillami do Claude i innych modeli AI."
permalink: /przydatne-repo/prompty-repo/
---

# Repozytoria promptów i skilli

## Kolekcje promptów

### anthropics/prompt-eng-interactive-tutorial
Oficjalny interaktywny tutorial prompt engineeringu od Anthropic.

- **URL:** github.com/anthropics/prompt-eng-interactive-tutorial
- **Format:** Jupyter Notebooks
- **Zawiera:** 9 rozdziałów od podstaw do zaawansowanych

### f/awesome-chatgpt-prompts
Największa kolekcja promptów (działa też z Claude).

- **URL:** github.com/f/awesome-chatgpt-prompts
- **Gwiazdki:** 100k+
- **Zawiera:** Setki promptów do różnych zadań i ról

### dair-ai/Prompt-Engineering-Guide
Kompletny przewodnik po prompt engineeringu.

- **URL:** github.com/dair-ai/Prompt-Engineering-Guide
- **Zawiera:** Techniki, przykłady, research, zastosowania

## Skille i konfiguracje Claude Code

### Oficjalne skille Anthropic (claude.ai)
Skille wbudowane w claude.ai (dostępne przez `/mnt/skills/public/`):
- `docx/SKILL.md` – tworzenie dokumentów Word
- `pptx/SKILL.md` – tworzenie prezentacji PowerPoint
- `pdf/SKILL.md` – tworzenie i edycja PDF
- `xlsx/SKILL.md` – tworzenie arkuszy Excel

## Konfiguracje CLAUDE.md

Plik `CLAUDE.md` w katalogu projektu daje Claude kontekst projektu:

```markdown
# Projekt: Mój Blog WordPress

## Stack
- WordPress 6.5
- PHP 8.2
- MySQL 8.0
- Motyw: Kadence

## Zasady
- Pisz komentarze po polsku
- Używaj PSR-12
- Zawsze sprawdzaj bezpieczeństwo (sanitize/escape)

## Struktura projektu
- /wp-content/themes/moj-motyw/ ← aktywny motyw
- /wp-content/plugins/ ← wtyczki
```
