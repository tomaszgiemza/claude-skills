---
layout: with-comments
title: "Claude z Zapier, n8n i Make"
parent: "🔗 Integracje Claude"
nav_order: 4
description: "Jak zintegrować Claude z narzędziami automatyzacji – Zapier, n8n i Make. Przykłady workflow bez kodowania."
permalink: /integracje/automatyzacja/
---

# Claude z Zapier, n8n i Make

## Zapier – bez kodowania

Zapier ma natywną integrację z Claude.

1. Zapier → Create Zap
2. Trigger: np. "Nowy email w Gmail"
3. Action: **Anthropic Claude** → **Send Message**
4. Skonfiguruj prompt i model
5. Następna akcja: np. wyślij odpowiedź lub zapisz do Sheets

**Przykładowy workflow:**
```
Trigger: Nowa wiadomość w Formularzu Google
↓
Claude: Kategoryzuj pytanie i napisz wstępną odpowiedź
↓
Gmail: Wyślij odpowiedź do klienta
↓
Sheets: Zapisz do arkusza z historią
```

## n8n – self-hosted, za darmo

n8n to open-source Zapier który możesz hostować sam (patrz: [selfhosted.giemza.nl](https://selfhosted.giemza.nl)).

**Instalacja (Docker):**
```bash
docker run -d   -p 5678:5678   -v n8n_data:/home/node/.n8n   n8nio/n8n
```

**Node Claude w n8n:**
1. Dodaj node → szukaj "Anthropic"
2. Skonfiguruj credentials (klucz API)
3. Wpisz prompt i wybierz model

**Przykładowy workflow n8n:**
```
Webhook (nowe zamówienie WooCommerce)
↓
Claude: Napisz spersonalizowany email potwierdzający
↓
Gmail/SMTP: Wyślij email
```

## Make (dawny Integromat)

Make → Create scenario → Add module → Anthropic → Create Message

Podobnie jak Zapier – drag & drop workflow z Claude.

{: .highlight }
**Moja rekomendacja:** n8n jeśli dbasz o prywatność danych i chcesz self-hosted. Zapier jeśli chcesz gotowe szablony i prostotę. Make – gdzieś pośrodku.
