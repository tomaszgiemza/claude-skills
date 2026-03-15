---
layout: default
title: "Projects i Memory"
parent: "📖 Kurs Claude.ai"
nav_order: 3
description: "Jak używać Projects i Memory w Claude.ai – tworzenie projektów instrukcje systemowe pamięć długoterminowa."
permalink: /kurs-claude-ai/projects-memory/
---

# Projects i Memory w Claude.ai

## Projects – co to?

Projects to grupy rozmów ze wspólną pamięcią i instrukcjami. Claude pamięta kontekst projektu we wszystkich rozmowach w nim zawartych.

{: .highlight }
Dostępne w planie **Pro i wyżej**.

## Jak stworzyć projekt?

1. Panel boczny → **Projects** → **New Project**
2. Nadaj nazwę (np. "Mój blog", "Projekt klienta X")
3. Dodaj **Project Instructions** – to system prompt dla całego projektu
4. Opcjonalnie dodaj pliki które Claude zawsze widzi

## Przykładowe Project Instructions

### Dla bloga
```
Jesteś asystentem redakcyjnym bloga giemza.nl o tematyce 
self-hostingu i nowych technologiach.

Zawsze piszesz po polsku. Styl: techniczny ale przystępny.
Docelowy czytelnik: entuzjasta technologii, 25-40 lat.
Zawsze optymalizuj pod SEO (Rank Math).
Artykuły mają min. 1200 słów.
```

### Dla developera
```
Jesteś senior PHP developerem.
Stack: WordPress, WooCommerce, PHP 8.2, MySQL.
Zawsze piszesz kod z komentarzami po polsku.
Używasz PSR-12 coding standards.
Przy błędach najpierw diagnozuj, potem proponuj fix.
```

### Dla obsługi klienta
```
Pomagasz mi odpowiadać na emaile klientów sklepu 
z odzieżą online.
Ton: uprzejmy, profesjonalny, empatyczny.
Zawsze proponuj rozwiązanie problemu.
Używaj formy "Pani/Pan" lub "Ty" zależnie od emaila klienta.
```

## Memory – pamięć długoterminowa

Memory pozwala Claude zapamiętywać informacje między rozmowami.

**Włącz:** Settings → Memory → włącz

Claude będzie automatycznie zapamiętywał ważne informacje o Tobie np.:
- Twoje imię i zawód
- Preferencje komunikacji
- Projekty nad którymi pracujesz
- Technologie których używasz

**Zarządzaj pamięcią:** Settings → Memory → przeglądaj i usuń wpisy

{: .note }
Możesz też ręcznie powiedzieć Claude co ma zapamiętać: *"Zapamiętaj że pracuję na Ubuntu 24.04 i używam VS Code."*
