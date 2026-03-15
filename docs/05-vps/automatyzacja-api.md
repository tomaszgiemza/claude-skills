---
layout: with-comments
title: "Automatyzacja zadań Claude przez API na VPS"
parent: "🖥️ Claude na serwerze VPS"
nav_order: 2
description: "Jak automatyzować zadania z Claude API na serwerze VPS – skrypty bash, cron jobs, Python i przykłady praktyczne."
permalink: /vps/automatyzacja-api/
---

# Automatyzacja przez API na VPS

Mając VPS i klucz API możesz tworzyć automatyczne procesy które używają Claude bez Twojego udziału.

## Prosty skrypt bash z Claude API

```bash
#!/bin/bash
# analyze-logs.sh – analizuj logi i wyślij raport emailem

LOG_FILE="/var/log/nginx/access.log"
API_KEY="$ANTHROPIC_API_KEY"

# Pobierz ostatnie 100 linii logów
LOGS=$(tail -100 "$LOG_FILE")

# Wyślij do Claude
RESPONSE=$(curl -s https://api.anthropic.com/v1/messages \
  -H "x-api-key: $API_KEY" \
  -H "anthropic-version: 2023-06-01" \
  -H "content-type: application/json" \
  -d "{
    \"model\": \"claude-haiku-4-5-20251001\",
    \"max_tokens\": 500,
    \"messages\": [{
      \"role\": \"user\",
      \"content\": \"Przeanalizuj te logi nginx i wypisz: 1) top 5 IP, 2) błędy 5xx, 3) podejrzane requesty:\n$LOGS\"
    }]
  }")

# Wyciągnij tekst odpowiedzi
ANALYSIS=$(echo "$RESPONSE" | python3 -c "import sys,json; print(json.load(sys.stdin)['content'][0]['text'])")

# Wyślij emailem
echo "$ANALYSIS" | mail -s "Raport logów nginx - $(date +%Y-%m-%d)" admin@twojadomena.pl
```

## Cron job – automatyczna analiza

```bash
# Dodaj do crontab (crontab -e):
# Każdego dnia o 8:00 rano
0 8 * * * /home/user/scripts/analyze-logs.sh
```

## Przykłady automatyzacji

**Codzienne podsumowanie GitHuba:**
```bash
# Pobierz commity z ostatniego dnia i poproś Claude o podsumowanie
```

**Monitoring i alerty:**
```bash
# Sprawdź status strony, jeśli down – wyślij raport przez Claude
```

**Generowanie raportów SEO:**
```bash
# Pobierz dane z Google Search Console API i poproś Claude o analizę
```

{: .highlight }
**Wskazówka kosztowa:** Do automatyzacji używaj modelu **Haiku** – jest 10x tańszy od Sonnet i wystarczający do prostych zadań analizy i podsumowań.
