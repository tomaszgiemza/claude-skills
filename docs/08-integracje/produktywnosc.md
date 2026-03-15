---
layout: with-comments
title: "Claude z Notion, Slack i Asana"
parent: "🔗 Integracje Claude"
nav_order: 2
description: "Jak połączyć Claude z Notion, Slack i Asaną przez MCP – zarządzanie notatkami, wiadomościami i zadaniami."
permalink: /integracje/produktywnosc/
---

# Claude z Notion, Slack i Asana

## Notion

**Przez claude.ai Connectors:**
Settings → Connectors → Notion → Connect

Możesz pytać:
- *"Stwórz notatkę z dzisiejszego spotkania"*
- *"Znajdź wszystkie strony dotyczące projektu X"*
- *"Dodaj zadanie do bazy danych projektów"*

**Przez MCP:**
```bash
npx @notionhq/notion-mcp-server
```

## Slack

**Przez MCP:**
```json
{
  "mcpServers": {
    "slack": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-slack"],
      "env": {
        "SLACK_BOT_TOKEN": "xoxb-twój-token",
        "SLACK_TEAM_ID": "T..."
      }
    }
  }
}
```

Przykładowe zadania:
```
"Podsumuj dyskusję w kanale #projekty z ostatnich 2 dni"
"Napisz wiadomość do kanału #ogłoszenia o nowym release"
"Znajdź wiadomości gdzie ktoś wspomniał o błędzie w checkout"
```

## Asana

```bash
# Instalacja MCP serwera Asana
npx -y asana-mcp-server
```

```
"Utwórz zadanie: Naprawić błąd w formularzu kontaktowym, deadline piątek"
"Pokaż moje zadania na ten tydzień"
"Zaktualizuj status zadania X na Ukończone"
```

{: .note }
Więcej MCP serwerów: [github.com/modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers)
