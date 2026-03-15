---
layout: default
title: "Skill – Docker Compose"
parent: "🛠️ Claude Code – skille"
nav_order: 4
description: "Publiczny skill do Claude Code dla Docker Compose – konfiguracje kontenerów sieci volumes i stack'ów produkcyjnych."
permalink: /claude-code-skille/docker/
---

# Skill – Docker Compose

Skill do tworzenia konfiguracji Docker i Docker Compose.

## Treść pliku SKILL.md

````markdown
---
name: docker-compose
description: "Tworzenie docker-compose.yml dla self-hosted aplikacji – sieci, volumes, zmienne środowiskowe, healthchecks"
---

# Docker Compose Skill

## Wzorzec – dobry docker-compose.yml

```yaml
version: '3.8'

services:
  app:
    image: app/image:latest
    container_name: app-name
    restart: unless-stopped
    
    # Porty: tylko gdy potrzebny zewnętrzny dostęp
    # Jeśli używasz reverse proxy – usuń ports!
    ports:
      - "8080:80"
    
    # Volumes – zawsze nazwane lub bind mount z ścieżką
    volumes:
      - app-data:/data
      - ./config:/config:ro  # :ro = read only
    
    # Zmienne środowiskowe – z pliku .env
    env_file:
      - .env
    environment:
      - TZ=Europe/Warsaw
    
    # Sieć – izolacja
    networks:
      - app-network
    
    # Healthcheck
    healthcheck:
      test: ["CMD", "curl", "-f", "http://localhost/health"]
      interval: 30s
      timeout: 10s
      retries: 3

volumes:
  app-data:
    driver: local

networks:
  app-network:
    driver: bridge
```

## Zasady bezpieczeństwa
- Nigdy nie umieszczaj haseł w docker-compose.yml – używaj .env
- Zawsze dodaj .env do .gitignore
- Używaj restart: unless-stopped (nie always)
- Ogranicz dostęp do portów: "127.0.0.1:8080:80" zamiast "8080:80"
- Używaj named volumes zamiast bind mountów dla danych

## Struktura projektu z Dockerem
```
projekt/
├── docker-compose.yml
├── docker-compose.prod.yml   ← nadpisania produkcyjne
├── .env                      ← zmienne (gitignore!)
├── .env.example              ← szablon (commit do repo)
└── data/                     ← persystentne dane (gitignore!)
```
````
