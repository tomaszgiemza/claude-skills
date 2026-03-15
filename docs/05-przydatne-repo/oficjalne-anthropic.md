---
layout: default
title: "Oficjalne repozytoria Anthropic"
parent: "🔗 Przydatne repozytoria"
nav_order: 1
description: "Oficjalne repozytoria GitHub Anthropic – Claude SDK dokumentacja przykłady i narzędzia deweloperskie."
permalink: /przydatne-repo/oficjalne-anthropic/
---

# Oficjalne repozytoria Anthropic

## Główne repozytoria

### anthropics/anthropic-sdk-python
Python SDK do Claude API.

- **URL:** github.com/anthropics/anthropic-sdk-python
- **Dla kogo:** Python developerzy
- **Zawiera:** Oficjalny klient API, przykłady, streaming

```python
import anthropic

client = anthropic.Anthropic()
message = client.messages.create(
    model="claude-sonnet-4-5-20251022",
    max_tokens=1024,
    messages=[{"role": "user", "content": "Cześć Claude!"}]
)
print(message.content)
```

### anthropics/anthropic-sdk-typescript
TypeScript/JavaScript SDK do Claude API.

- **URL:** github.com/anthropics/anthropic-sdk-typescript
- **Dla kogo:** JS/TS developerzy, Node.js

### anthropics/courses
Oficjalne kursy i tutoriale Anthropic.

- **URL:** github.com/anthropics/courses
- **Zawiera:**
  - Anthropic API Fundamentals
  - Prompt Engineering Interactive Tutorial
  - Tool Use Course
  - Real World Prompting

{: .highlight }
**Zacznij tutaj:** `anthropics/courses` – darmowe, oficjalne tutoriale w Jupyter Notebooks.

### anthropics/model-spec
Specyfikacja modelu Claude – zasady i wartości.

- **URL:** github.com/anthropics/model-spec
- **Ciekawe dla:** Osób chcących głębiej rozumieć jak działa i myśli Claude

### anthropics/claude-code
Claude Code – AI w terminalu.

- **URL:** github.com/anthropics/claude-code (dokumentacja)
- **Instalacja:** `npm install -g @anthropic-ai/claude-code`
