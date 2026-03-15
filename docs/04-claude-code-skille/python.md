---
layout: default
title: "Skill – Python Scripts"
parent: "🛠️ Claude Code – skille"
nav_order: 2
description: "Publiczny skill do Claude Code dla Python – skrypty automatyzacji CLI tools obsługa błędów i dobre praktyki."
permalink: /claude-code-skille/python/
---

# Skill – Python Scripts

Skill do tworzenia skryptów automatyzacji i narzędzi CLI w Python.

## Treść pliku SKILL.md

````markdown
---
name: python-scripts
description: "Tworzenie skryptów Python – automatyzacja, CLI tools, web scraping, API clients"
---

# Python Scripts Skill

## Środowisko
- Python 3.11+
- Virtual environment: zawsze używaj venv
- Zależności: requirements.txt lub pyproject.toml

## Struktura projektu
```
my-script/
├── main.py              ← punkt wejścia
├── src/
│   ├── __init__.py
│   ├── config.py        ← konfiguracja
│   └── utils.py         ← funkcje pomocnicze
├── tests/
│   └── test_main.py
├── requirements.txt
├── .env.example
└── README.md
```

## Wzorce kodu

### Obsługa błędów
```python
import logging
import sys

logging.basicConfig(level=logging.INFO, format='%(asctime)s - %(levelname)s - %(message)s')
logger = logging.getLogger(__name__)

def main():
    try:
        result = process_data()
        logger.info(f"Sukces: {result}")
    except FileNotFoundError as e:
        logger.error(f"Brak pliku: {e}")
        sys.exit(1)
    except Exception as e:
        logger.exception(f"Nieoczekiwany błąd: {e}")
        sys.exit(1)
```

### CLI z argparse
```python
import argparse

def parse_args():
    parser = argparse.ArgumentParser(description='Opis skryptu')
    parser.add_argument('input', help='Plik wejściowy')
    parser.add_argument('-o', '--output', default='output.txt', help='Plik wyjściowy')
    parser.add_argument('-v', '--verbose', action='store_true', help='Tryb szczegółowy')
    return parser.parse_args()
```

### Zmienne środowiskowe
```python
from dotenv import load_dotenv
import os

load_dotenv()

API_KEY = os.getenv('API_KEY')
if not API_KEY:
    raise ValueError("Brak API_KEY w zmiennych środowiskowych")
```

## Zasady
- Komentarze w języku polskim
- Type hints dla wszystkich funkcji
- Docstrings dla klas i funkcji publicznych
- Obsługa wyjątków zawsze explicitna (nie `except:`)
- Logowanie zamiast print() dla skryptów produkcyjnych
````
