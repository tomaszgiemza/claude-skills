---
layout: with-comments
title: "Claude w VS Code i edytorach kodu"
parent: "🔗 Integracje Claude"
nav_order: 3
description: "Jak używać Claude w VS Code, Cursor i JetBrains – rozszerzenia, konfiguracja i produktywne skróty."
permalink: /integracje/edytory/
---

# Claude w edytorach kodu

## VS Code – rozszerzenie Claude

1. VS Code → Extensions (Ctrl+Shift+X)
2. Szukaj: **Claude Dev** lub **Continue** (obsługuje Claude)
3. Zainstaluj i skonfiguruj klucz API

Popularne rozszerzenia VS Code z Claude:
- **Continue** – open source, obsługuje Claude i inne modele
- **Claude Dev** – oficjalne rozszerzenie Anthropic

## Cursor – edytor z Claude wbudowanym

Cursor to fork VS Code z głęboko wbudowanym AI (obsługuje Claude Sonnet).

**Instalacja:**
Pobierz z [cursor.com](https://cursor.com)

**Konfiguracja Claude:**
Cursor Settings → Models → wybierz Claude Sonnet/Opus

**Skróty Cursor:**
- `Ctrl+K` – edytuj zaznaczony kod
- `Ctrl+L` – otwórz czat
- `Ctrl+Shift+L` – dodaj do czatu

## JetBrains (PhpStorm, WebStorm)

Plugin: **AI Assistant** lub **Continue**

Settings → Plugins → szukaj Continue → zainstaluj → skonfiguruj API key Anthropic.

## Claude Code vs rozszerzenia edytora

| | Claude Code (terminal) | Rozszerzenia edytora |
|---|---|---|
| **Dostęp do plików** | ✅ Pełny | Tylko otwarty projekt |
| **Uruchamianie komend** | ✅ | ❌ |
| **Autonomia** | ✅ Wysoka | Niska |
| **Integracja z edytorem** | Zewnętrzna | ✅ Natywna |
| **Dla kogo** | Zaawansowani | Każdy |

{: .highlight }
**Mój setup:** Claude Code w terminalu do większych zadań i refaktoryzacji. Continue w VS Code do szybkich pytań i inline suggestions.
