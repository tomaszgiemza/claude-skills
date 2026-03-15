---
layout: with-comments
title: "Claude API w JavaScript – Node.js i frontend"
parent: "🔌 Claude API"
nav_order: 3
description: "Jak używać Claude API w JavaScript i Node.js – przykłady, SDK, streaming i integracja z aplikacjami webowymi."
permalink: /api/przyklad-js/
---

# Claude API w JavaScript

## Instalacja SDK

```bash
npm install @anthropic-ai/sdk
```

## Podstawowy przykład Node.js

```javascript
import Anthropic from '@anthropic-ai/sdk';

const client = new Anthropic({
  apiKey: process.env.ANTHROPIC_API_KEY
});

async function generateContent(prompt) {
  const message = await client.messages.create({
    model: 'claude-sonnet-4-20250514',
    max_tokens: 1024,
    messages: [
      {
        role: 'user',
        content: prompt
      }
    ]
  });
  
  return message.content[0].text;
}

// Użycie
const result = await generateContent(
  'Napisz krótki opis produktu dla słuchawek bezprzewodowych Sony WH-1000XM5'
);
console.log(result);
```

## Streaming – odpowiedź na żywo

```javascript
const stream = await client.messages.stream({
  model: 'claude-sonnet-4-20250514',
  max_tokens: 1024,
  messages: [{ role: 'user', content: 'Napisz długi artykuł o...' }]
});

// Wypisuj tekst w miarę jak się pojawia
for await (const chunk of stream) {
  if (chunk.type === 'content_block_delta') {
    process.stdout.write(chunk.delta.text);
  }
}
```

## System prompt – stały kontekst

```javascript
const message = await client.messages.create({
  model: 'claude-haiku-4-5-20251001',
  max_tokens: 500,
  system: 'Jesteś pomocnym asystentem obsługi klienta sklepu z elektroniką. Odpowiadaj po polsku, krótko i rzeczowo.',
  messages: [
    { role: 'user', content: 'Jak zwrócić produkt?' }
  ]
});
```

{: .highlight }
**Wskazówka:** Używaj `system` do ustawiania kontekstu i zachowania modelu, a `messages` do samej rozmowy. System prompt nie jest liczony jako "turn" w konwersacji.
