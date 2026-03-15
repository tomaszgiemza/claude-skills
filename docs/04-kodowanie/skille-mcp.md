---
layout: with-comments
title: "Skille i MCP w Claude Code"
parent: "💻 Claude i kodowanie"
nav_order: 4
description: "Jak używać skilli i MCP (Model Context Protocol) w Claude Code – instalacja serwerów MCP, pliki SKILL.md i rozszerzanie możliwości agenta."
permalink: /kodowanie/skille-mcp/
---

# Skille i MCP w Claude Code

## Skille (SKILL.md)

Skille to pliki `SKILL.md` zawierające instrukcje dla konkretnych technologii. Claude Code czyta je przed wykonaniem zadania i wie jak pracować z danym stackiem.

### Gdzie umieścić skille?

```bash
# Globalnie – dla wszystkich projektów
~/.claude/skills/wordpress/SKILL.md

# Lokalnie – dla konkretnego projektu
/projekt/SKILL.md
```

### Gotowe skille z tej strony

W sekcji [Prompty i skille → Development](/prompty/development) znajdziesz moje skille dla:
- WordPress + PHP
- Jekyll / Just the Docs
- Docker Compose

## MCP – Model Context Protocol

MCP to standard stworzony przez Anthropic który pozwala Claude Code łączyć się z zewnętrznymi narzędziami i danymi.

### Konfiguracja MCP

Plik `~/.claude.json` (lub `~/.claude/claude_desktop_config.json`):

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/home/user/projekty"
      ]
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_twój_token"
      }
    }
  }
}
```

### Popularne serwery MCP

| Serwer | Co daje | Instalacja |
|--------|---------|-----------|
| **filesystem** | Dostęp do plików | `@modelcontextprotocol/server-filesystem` |
| **github** | Repozytoria, PR, issues | `@modelcontextprotocol/server-github` |
| **sqlite** | Baza SQLite | `@modelcontextprotocol/server-sqlite` |
| **fetch** | Pobieranie stron | `@modelcontextprotocol/server-fetch` |
| **puppeteer** | Automatyzacja przeglądarki | `@modelcontextprotocol/server-puppeteer` |

### Sprawdź dostępne MCP serwery

```bash
# Lista zainstalowanych
claude mcp list

# Dodaj serwer
claude mcp add nazwa -- npx -y @modelcontextprotocol/server-nazwa
```

{: .highlight }
**Moje ulubione połączenie:** Claude Code + filesystem MCP + GitHub MCP. Mam agenta który widzi moje pliki, może czytać i commitować do GitHub – całe workflow w terminalu.
