---
layout: with-comments
title: "Claude z Gmail i Google Calendar"
parent: "🔗 Integracje Claude"
nav_order: 1
description: "Jak połączyć Claude z Gmail i Google Calendar przez MCP serwery – czytanie emaili, tworzenie wydarzeń i automatyzacja."
permalink: /integracje/google/
---

# Claude z Gmail i Google Calendar

## Przez Claude.ai – najprostsza opcja

1. Wejdź na [claude.ai](https://claude.ai) → Settings → **Connectors**
2. Znajdź **Gmail** i kliknij Connect
3. Zaloguj się na Google i zezwól na dostęp
4. Powtórz dla **Google Calendar**

Od teraz możesz pytać Claude:
- *"Podsumuj moje emaile z dzisiaj"*
- *"Co mam w kalendarzu na przyszły tydzień?"*
- *"Napisz odpowiedź na ostatni email od klienta X"*
- *"Utwórz wydarzenie: spotkanie z Tomkiem, piątek 14:00, 1 godzina"*

## Przez MCP – dla Claude Code

```json
// ~/.claude/claude_desktop_config.json
{
  "mcpServers": {
    "gmail": {
      "command": "npx",
      "args": ["-y", "@anthropic/mcp-server-gmail"],
      "env": {
        "GMAIL_CREDENTIALS": "/home/user/.gmail-credentials.json"
      }
    },
    "gcal": {
      "command": "npx", 
      "args": ["-y", "@anthropic/mcp-server-gcal"],
      "env": {
        "GCAL_CREDENTIALS": "/home/user/.gcal-credentials.json"
      }
    }
  }
}
```

## Przykładowe zadania

```
# W Claude Code:
"Przejrzyj emaile z ostatnich 3 dni i stwórz listę TODO z rzeczy do zrobienia"
"Znajdź wszystkie emaile od klientów z niezaopłaconymi fakturami"
"Zaplanuj followup emaile do kontaktów z targów – po 3 dniach od spotkania"
```

{: .highlight }
**Wskazówka prywatności:** Integracja przez claude.ai wysyła Twoje emaile i kalendarz do Anthropic. Jeśli masz wrażliwe dane – rozważ własny MCP server z lokalnym modelem.
