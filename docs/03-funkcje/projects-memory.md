---
layout: with-comments
title: "Projects i Memory – jak to działa naprawdę"
parent: "🔧 Funkcje Claude"
nav_order: 1
description: "Jak używać Projects i Memory w Claude.ai – tworzenie projektu, instrukcje systemowe, pamięć długoterminowa i praktyczne przykłady."
permalink: /funkcje/projects-memory/
---

# Projects i Memory – jak to działa naprawdę

To jedna z najbardziej niedocenianych funkcji Claude. Większość ludzi nie wie że istnieje, a ci którzy wiedzą – nie wiedzą jak dobrze skonfigurować.

## Memory – pamięć między rozmowami

Domyślnie Claude nie pamięta poprzednich rozmów. Każda nowa rozmowa to czysta karta.

**Memory** to funkcja która pozwala Claude zapamiętywać informacje o Tobie między sesjami.

### Jak włączyć

Ustawienia (Settings) → **Memory** → włącz przełącznik.

### Co Claude zapamiętuje?

Automatycznie zapamiętuje rzeczy które wspominasz naturalnie:
- Twoje imię i zawód
- Projekty nad którymi pracujesz
- Technologie których używasz
- Preferencje komunikacji (np. "wolę krótkie odpowiedzi")
- Ważne konteksty osobiste lub zawodowe

### Zarządzanie pamięcią

Settings → Memory → zobaczysz listę zapamiętanych faktów. Możesz każdy usunąć.

Możesz też ręcznie nakazać zapamiętanie: *"Zapamiętaj że pracuję na Ubuntu 24.04 i używam VS Code z motywem One Dark."*

## Projects – projekty z pamięcią

Projects to grupy rozmów ze **wspólnym kontekstem i instrukcjami**. Claude pamięta wszystko z projektu we wszystkich rozmowach w nim zawartych.

{: .highlight }
**Dostępne w planie Pro i wyżej.** To jedna z głównych zalet płatnego planu.

### Jak stworzyć projekt

1. Panel boczny → **Projects** → **New Project**
2. Nadaj nazwę
3. Kliknij **Project Instructions** i wpisz instrukcje
4. Opcjonalnie – dodaj pliki które Claude zawsze widzi (np. brief projektu, styl guide)

### Przykładowe instrukcje projektowe

**Projekt: Mój blog**
```
Jesteś moim asystentem redakcyjnym. Blog prowadzę na giemza.nl 
i piszę o technologiach self-hosted oraz AI.

Styl pisania: techniczny ale przystępny, pierwsza osoba,
bez nadmiernego formalizmu. Czytelnicy to entuzjaści 
technologii, 25-40 lat.

Przy artykułach: zawsze optymalizuj pod SEO (Rank Math),
minimum 1200 słów, dodawaj praktyczne przykłady.
Nie używaj słowa "przełomowy" ani "rewolucyjny".
```

**Projekt: Klient X – sklep WooCommerce**
```
Pracuję nad sklepem WooCommerce dla firmy [NAZWA].
Branża: [BRANŻA]. 
Stack: WordPress 6.5, WooCommerce 9, PHP 8.2.
Motyw: GeneratePress Premium.

Przy kodowaniu: komentarze po polsku, PSR-12,
zawsze sprawdzaj bezpieczeństwo (sanitize/escape).
Klient nie ma wiedzy technicznej – tłumaczenia piszę prostym językiem.
```

### Dodawanie plików do projektu

Możesz dodać pliki które Claude zawsze widzi w tym projekcie:
- Brief klienta
- Style guide marki
- Wcześniejsze materiały
- Dokumentację techniczną

Kliknij ikonę pliku w projekcie i wgraj.

{: .note }
Następna strona: [Web Search i pliki](/funkcje/web-search-pliki/)
