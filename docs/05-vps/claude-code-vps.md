---
layout: with-comments
title: "Claude Code na VPS – instalacja i konfiguracja"
parent: "🖥️ Claude na serwerze VPS"
nav_order: 1
description: "Jak zainstalować i skonfigurować Claude Code na serwerze VPS z Ubuntu. SSH, Node.js, API key, tmux i praca zdalna."
permalink: /vps/claude-code-vps/
---

# Claude Code na VPS

Uruchomienie Claude Code na VPS otwiera nowe możliwości – możesz mieć agenta AI działającego na Twoim serwerze, automatyzującego zadania 24/7.

## Wymagania

- VPS z Ubuntu 22.04 lub 24.04 (lub inny Linux)
- Minimum 1 GB RAM (zalecane 2 GB)
- Dostęp SSH
- Klucz API Anthropic lub plan Pro

## Krok 1 – Połącz się przez SSH

```bash
ssh user@twoj-serwer.com
```

## Krok 2 – Zainstaluj Node.js

```bash
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt-get install -y nodejs
node --version  # sprawdź czy działa
```

## Krok 3 – Zainstaluj Claude Code

```bash
npm install -g @anthropic-ai/claude-code
```

## Krok 4 – Skonfiguruj klucz API

Na VPS nie możesz kliknąć w link przeglądarki. Użyj klucza API:

```bash
export ANTHROPIC_API_KEY="sk-ant-api03-twój-klucz"
# Lub dodaj na stałe do ~/.bashrc:
echo 'export ANTHROPIC_API_KEY="sk-ant-api03-twój-klucz"' >> ~/.bashrc
source ~/.bashrc
```

Klucz API pobierzesz z [console.anthropic.com](https://console.anthropic.com) → API Keys.

## Krok 5 – Uruchom Claude Code

```bash
cd /var/www/twoj-projekt
claude
```

## Praca zdalna bez rozłączania – tmux

Żeby Claude Code działał nawet po zamknięciu SSH:

```bash
# Zainstaluj tmux
sudo apt install tmux

# Utwórz sesję
tmux new -s claude

# Uruchom Claude Code
claude

# Odłącz sesję (Ctrl+B, potem D)
# Sesja działa w tle!

# Wróć do sesji później
tmux attach -t claude
```

{: .warning }
Klucz API to jak hasło – nie wklejaj go w miejscach publicznych, nie commituj do GitHub. Używaj zmiennych środowiskowych lub pliku `.env` w `.gitignore`.

{: .note }
Następna strona: [Automatyzacja przez API](/vps/automatyzacja-api/)
