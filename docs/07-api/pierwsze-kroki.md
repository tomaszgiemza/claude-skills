---
layout: with-comments
title: "Pierwsze kroki z Claude API"
parent: "🔌 Claude API"
nav_order: 1
description: "Jak zacząć z Claude API – rejestracja, klucz API, pierwsze zapytanie curl, limity i dobre praktyki bezpieczeństwa."
permalink: /api/pierwsze-kroki/
---

# Pierwsze kroki z Claude API

## Krok 1 – Utwórz konto w Anthropic Console

Wejdź na [console.anthropic.com](https://console.anthropic.com) i zarejestruj się.

## Krok 2 – Wygeneruj klucz API

Console → **API Keys** → **Create Key**

Nadaj mu opisową nazwę (np. "moj-sklep-wordpress") i skopiuj. **Zobaczysz go tylko raz** – zapisz w bezpiecznym miejscu.

## Krok 3 – Dodaj środki

API jest płatne za użycie (pay-as-you-go). Console → **Billing** → dodaj kartę i środki (minimum $5).

{: .highlight }
Dla małych projektów i testów $5 wystarczy na długo. Haiku to $0.80/1M tokenów – za $5 możesz przetworzyć ~6 milionów tokenów.

## Krok 4 – Pierwsze zapytanie (curl)

```bash
curl https://api.anthropic.com/v1/messages \
  -H "x-api-key: $ANTHROPIC_API_KEY" \
  -H "anthropic-version: 2023-06-01" \
  -H "content-type: application/json" \
  -d '{
    "model": "claude-haiku-4-5-20251001",
    "max_tokens": 1024,
    "messages": [
      {
        "role": "user",
        "content": "Cześć! Napisz krótkie powitanie po polsku."
      }
    ]
  }'
```

## Struktura odpowiedzi

```json
{
  "id": "msg_01XFDUDYJgAACzvnptvVoYEL",
  "type": "message",
  "role": "assistant",
  "content": [
    {
      "type": "text",
      "text": "Cześć! Miło Cię poznać..."
    }
  ],
  "model": "claude-haiku-4-5-20251001",
  "usage": {
    "input_tokens": 15,
    "output_tokens": 28
  }
}
```

## Bezpieczeństwo klucza API

{: .warning }
Klucz API = pełny dostęp do Twojego konta. Ktoś kto go zdobędzie może generować koszty na Twój rachunek.

**Zasady:**
- Nigdy nie wklejaj klucza w kodzie który commitujesz do GitHub
- Używaj zmiennych środowiskowych (`.env` w `.gitignore`)
- Ogranicz uprawnienia klucza w Console
- Monitoruj użycie w Console → Usage
