---
layout: with-comments
title: "Lekcja 4 – Agenty AI i MCP"
parent: "🚀 Kurs zaawansowany"
nav_order: 4
description: "Jak budować agenty AI z Claude – autonomiczne zadania, MCP serwery, tool use i bezpieczeństwo agentów."
permalink: /kurs-zaawansowany/lekcja-4/
---

# Lekcja 4 – Agenty AI i MCP

Agent AI to coś więcej niż chatbot – to system który może samodzielnie planować, działać i korygować kurs na podstawie wyników.

## Czym różni się agent od chatbota?

| Chatbot | Agent AI |
|---------|----------|
| Odpowiada na pytania | Wykonuje wielokrokowe zadania |
| Jedna wymiana | Planuje i iteruje |
| Potrzebuje człowieka do każdego kroku | Działa autonomicznie |
| Narzędzia: tekst | Narzędzia: pliki, API, kod |

## Claude Code jako agent

Claude Code to w istocie agent. Gdy mu powiesz: *"Dodaj funkcję X do projektu"* – on:

1. Przegląda pliki projektu
2. Planuje co zmienić
3. Pisze kod
4. Uruchamia testy
5. Koryguje błędy
6. Informuje o wyniku

Wszystko bez Twojego udziału między krokami.

## Tool Use – Claude z narzędziami

Przez API możesz dać Claude narzędzia – funkcje które może wywoływać:

```python
tools = [
    {
        "name": "search_products",
        "description": "Wyszukaj produkty w bazie danych sklepu",
        "input_schema": {
            "type": "object",
            "properties": {
                "query": {"type": "string"},
                "category": {"type": "string"},
                "max_price": {"type": "number"}
            }
        }
    },
    {
        "name": "create_order",
        "description": "Utwórz nowe zamówienie",
        "input_schema": {
            "type": "object", 
            "properties": {
                "product_id": {"type": "string"},
                "quantity": {"type": "integer"},
                "customer_email": {"type": "string"}
            }
        }
    }
]

# Claude decyduje kiedy i jak użyć narzędzi
response = client.messages.create(
    model="claude-sonnet-4-20250514",
    tools=tools,
    messages=[{
        "role": "user",
        "content": "Zamów 2 sztuki najtańszych słuchawek bezprzewodowych dla jan@example.com"
    }]
)
```

## Bezpieczeństwo agentów

{: .warning }
Agenty które mogą modyfikować dane, wysyłać emaile lub wykonywać transakcje – wymagają bardzo starannego zaprojektowania zabezpieczeń.

Moje zasady przy budowie agentów:

1. **Zasada minimalnych uprawnień** – agent ma dostęp tylko do tego co potrzebuje
2. **Human in the loop** – dla nieodwracalnych akcji (wysyłka, płatność) wymagaj potwierdzenia
3. **Logowanie** – każda akcja agenta jest logowana
4. **Rate limiting** – ogranicz ile akcji agent może wykonać w jednostce czasu
5. **Sandbox** – testuj agenty w środowisku deweloperskim, nie produkcyjnym

{: .note }
Następna lekcja: [Claude w workflow firmy](/kurs-zaawansowany/lekcja-5/)
