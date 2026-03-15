---
layout: with-comments
title: "Claude jako autonomiczny agent na serwerze"
parent: "🖥️ Claude na serwerze VPS"
nav_order: 3
description: "Jak skonfigurować Claude Code jako autonomiczny agent na VPS – tryb non-interactive, zadania wsadowe i monitorowanie."
permalink: /vps/agent/
---

# Claude jako agent na serwerze

Claude Code w trybie `--no-interactive` może wykonywać zadania autonomicznie – bez Twojej obecności przy klawiaturze.

## Tryb nieinteraktywny

```bash
# Wykonaj zadanie i wyjdź
claude --no-interactive "Przejrzyj wszystkie pliki PHP w tym projekcie i wypisz potencjalne problemy bezpieczeństwa"

# Z przekierowaniem do pliku
claude --no-interactive "Stwórz dokumentację dla wszystkich funkcji w functions.php" > dokumentacja.md
```

## Przykład – automatyczny code review

```bash
#!/bin/bash
# code-review.sh

# Uruchom po każdym commicie (git hook)
CHANGED_FILES=$(git diff --name-only HEAD~1 HEAD | grep ".php$")

if [ -n "$CHANGED_FILES" ]; then
  claude --no-interactive "
    Zrób code review następujących plików PHP.
    Skup się na: bezpieczeństwo, wydajność, standardy WP.
    Pliki: $CHANGED_FILES
    Zawartość: $(cat $CHANGED_FILES)
  " > review-$(date +%Y%m%d-%H%M).md
  
  echo "Code review zapisany"
fi
```

## Git hook – review przed commitem

```bash
# .git/hooks/pre-push
#!/bin/bash
echo "Uruchamiam Claude Code review..."
claude --no-interactive "Sprawdź czy nowe zmiany mają oczywiste błędy" 
```

{: .warning }
Agenty autonomiczne mogą modyfikować pliki i wykonywać komendy. Zawsze testuj na środowisku deweloperskim, nie na produkcji. Używaj `--allowedTools` żeby ograniczyć co agent może robić.
