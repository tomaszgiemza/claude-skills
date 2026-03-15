---
layout: default
title: "MCP Serwery"
parent: "🔗 Przydatne repozytoria"
nav_order: 2
description: "Najlepsze repozytoria MCP (Model Context Protocol) do Claude – serwery integracje z zewnętrznymi narzędziami."
permalink: /przydatne-repo/mcp-serwery/
---

# MCP Serwery

## Czym jest MCP?

MCP (Model Context Protocol) to standard stworzony przez Anthropic pozwalający Claude łączyć się z zewnętrznymi narzędziami i danymi.

{: .highlight }
MCP to jak „wtyczki" dla Claude – pozwala mu odczytywać pliki, wysyłać emaile, zarządzać kalendarzem i wiele więcej.

## Oficjalne MCP Serwery

### modelcontextprotocol/servers
Oficjalne repozytorium z gotowymi MCP serwerami.

- **URL:** github.com/modelcontextprotocol/servers
- **Zawiera:**
  - Filesystem – dostęp do plików lokalnych
  - GitHub – zarządzanie repozytoriami
  - Google Drive – pliki w chmurze
  - PostgreSQL / SQLite – bazy danych
  - Slack – wiadomości
  - Puppeteer – automatyzacja przeglądarki
  - Fetch – pobieranie stron

## Popularne zewnętrzne MCP

| Serwer | Co robi | URL |
|--------|---------|-----|
| **mcp-gmail** | Czyta i wysyła emaile Gmail | github.com |
| **mcp-gcal** | Google Calendar | github.com |
| **mcp-notion** | Dostęp do Notion | github.com |
| **mcp-linear** | Zarządzanie taskami Linear | github.com |
| **mcp-asana** | Asana tasks | github.com |

## Jak dodać MCP do Claude.ai?

1. Wejdź na claude.ai → Settings → Connectors
2. Wybierz integrację (Gmail, Google Calendar, itp.)
3. Autoryzuj dostęp
4. Gotowe – Claude ma dostęp do Twoich danych

## Jak dodać MCP do Claude Code?

W pliku `~/.claude/claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/home/user/projekty"]
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_..."
      }
    }
  }
}
```
