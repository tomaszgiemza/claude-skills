---
layout: with-comments
title: "Ollama – lokalne modele AI"
parent: "🏠 Claude lokalnie"
nav_order: 2
description: "Jak zainstalować Ollama i uruchomić modele AI lokalnie – Llama 3, Mistral, Gemma. Instalacja na Linux, macOS i Windows."
permalink: /lokalna/ollama/
---

# Ollama – lokalne modele AI

Ollama to najprostszy sposób uruchomienia modeli AI lokalnie. Jedna komenda i masz działający model.

## Wymagania sprzętowe

| Rozmiar modelu | RAM | GPU (opcjonalne) |
|---------------|-----|-----------------|
| 7B parametrów | 8 GB | GPU 8 GB VRAM |
| 13B parametrów | 16 GB | GPU 12 GB VRAM |
| 70B parametrów | 64 GB | GPU 24 GB VRAM |

Bez GPU modele działają na CPU – wolniej ale działają.

## Instalacja Ollama

**Linux:**
```bash
curl -fsSL https://ollama.com/install.sh | sh
```

**macOS:**
Pobierz z [ollama.com/download](https://ollama.com/download) i zainstaluj jak normalną aplikację.

**Windows:**
Pobierz instalator `.exe` z tej samej strony.

## Uruchomienie modelu

```bash
# Pobierz i uruchom Llama 3.3 (70B – najlepszy ogólny)
ollama run llama3.3

# Lżejszy, szybszy (8B)
ollama run llama3.2

# Świetny do kodowania
ollama run qwen2.5-coder:7b

# DeepSeek R1 – najlepsze rozumowanie
ollama run deepseek-r1:7b
```

Przy pierwszym uruchomieniu model jest pobierany (kilka GB). Kolejne uruchomienia są natychmiastowe.

## Interfejs webowy – Open WebUI

Ollama samo w sobie to tylko terminal. Żeby mieć ładny interfejs jak Claude.ai:

```bash
# Zainstaluj Docker, potem:
docker run -d -p 3000:8080   --add-host=host.docker.internal:host-gateway   -v open-webui:/app/backend/data   --name open-webui   --restart always   ghcr.io/open-webui/open-webui:main
```

Wejdź na `http://localhost:3000` – masz lokalny interfejs AI.

{: .note }
Następna strona: [Chmura vs lokalnie – porównanie](/lokalna/chmura-vs-lokalnie/)
