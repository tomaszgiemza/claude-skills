---
layout: with-comments
title: "Instalacja Claude Code – krok po kroku"
parent: "💻 Claude i kodowanie"
nav_order: 2
description: "Jak zainstalować Claude Code na Linux, macOS i Windows. Wymagania, instalacja Node.js, konfiguracja API key i pierwsze uruchomienie."
permalink: /kodowanie/instalacja-claude-code/
---

# Instalacja Claude Code – krok po kroku

Pokażę Ci jak to zrobić od zera. Jeśli nigdy nie używałeś terminala – nie panikuj, wyjaśnię każdy krok.

## Wymagania

- **Node.js** w wersji 18 lub nowszej
- **Konto Anthropic** z planem Pro (lub klucz API)
- Terminal (Linux/macOS: wbudowany, Windows: PowerShell lub WSL)
- Połączenie z internetem

## Krok 1 – Sprawdź czy masz Node.js

Otwórz terminal i wpisz:
```bash
node --version
```

Jeśli zobaczysz np. `v20.11.0` – masz Node.js, przejdź do kroku 3.

Jeśli zobaczysz błąd – zainstaluj Node.js.

## Krok 2 – Zainstaluj Node.js

**Linux (Ubuntu/Debian):**
```bash
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt-get install -y nodejs
```

**macOS:**
```bash
# Zainstaluj Homebrew jeśli nie masz:
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
# Potem Node.js:
brew install node
```

**Windows:**
Pobierz instalator z [nodejs.org](https://nodejs.org) i uruchom.

## Krok 3 – Zainstaluj Claude Code

```bash
npm install -g @anthropic-ai/claude-code
```

Poczekaj chwilę na instalację. Sprawdź czy działa:
```bash
claude --version
```

## Krok 4 – Zaloguj się

```bash
claude
```

Przy pierwszym uruchomieniu Claude Code zapyta o autoryzację. Otwórz podany link w przeglądarce, zaloguj się na swoje konto Anthropic i autoryzuj.

{: .highlight }
Potrzebujesz planu **Pro** ($20/mies) lub aktywnego klucza API z saldem. Claude Code nie działa na darmowym planie.

## Krok 5 – Pierwsze użycie

Przejdź do katalogu swojego projektu:
```bash
cd /ścieżka/do/projektu
claude
```

I zacznij rozmawiać! Przykład:
```
> Opisz mi strukturę tego projektu
> Dodaj obsługę błędów do funkcji w pliku functions.php
> Napisz mi test jednostkowy dla tej klasy
```

## Skróty i przydatne komendy

| Komenda | Opis |
|---------|------|
| `claude` | Uruchom w trybie interaktywnym |
| `claude "zrób X"` | Wykonaj zadanie od razu |
| `claude --help` | Lista opcji |
| `/clear` | Wyczyść historię rozmowy |
| `/exit` | Wyjdź |
| Ctrl+C | Przerwij generowanie |

{: .note }
Następna strona: [CLAUDE.md – konfiguracja projektu](/kodowanie/claude-md/)
