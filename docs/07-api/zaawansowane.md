---
layout: with-comments
title: "Zaawansowane funkcje Claude API"
parent: "🔌 Claude API"
nav_order: 4
description: "Zaawansowane funkcje Claude API – Batch API, Function Calling, tool use, wizja, PDF i embeddingi."
permalink: /api/zaawansowane/
---

# Zaawansowane funkcje Claude API

## Batch API – 50% taniej

Batch API przetwarza żądania w tle i jest o 50% tańsze. Idealne gdy nie potrzebujesz odpowiedzi w czasie rzeczywistym.

```python
import anthropic

client = anthropic.Anthropic()

# Utwórz batch
batch = client.messages.batches.create(
    requests=[
        {
            "custom_id": "produkt-001",
            "params": {
                "model": "claude-haiku-4-5-20251001",
                "max_tokens": 200,
                "messages": [{"role": "user", "content": "Opisz: iPhone 16 Pro"}]
            }
        },
        {
            "custom_id": "produkt-002", 
            "params": {
                "model": "claude-haiku-4-5-20251001",
                "max_tokens": 200,
                "messages": [{"role": "user", "content": "Opisz: Samsung Galaxy S25"}]
            }
        }
    ]
)

print(f"Batch ID: {batch.id}")
# Sprawdź wyniki później
```

## Tool Use (Function Calling)

Claude może wywoływać zdefiniowane przez Ciebie funkcje:

```python
tools = [
    {
        "name": "get_product_info",
        "description": "Pobierz informacje o produkcie z bazy danych",
        "input_schema": {
            "type": "object",
            "properties": {
                "product_id": {
                    "type": "string",
                    "description": "ID produktu"
                }
            },
            "required": ["product_id"]
        }
    }
]

response = client.messages.create(
    model="claude-sonnet-4-20250514",
    max_tokens=1024,
    tools=tools,
    messages=[{"role": "user", "content": "Podaj informacje o produkcie ABC-123"}]
)
```

## Wizja – analiza obrazów

```python
import base64

with open("produkt.jpg", "rb") as f:
    image_data = base64.b64encode(f.read()).decode()

response = client.messages.create(
    model="claude-sonnet-4-20250514",
    max_tokens=500,
    messages=[{
        "role": "user",
        "content": [
            {
                "type": "image",
                "source": {
                    "type": "base64",
                    "media_type": "image/jpeg",
                    "data": image_data
                }
            },
            {
                "type": "text",
                "text": "Opisz ten produkt do użycia w sklepie internetowym"
            }
        ]
    }]
)
```
