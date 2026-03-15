---
layout: default
title: "Web Search i upload plików"
parent: "📖 Kurs Claude.ai"
nav_order: 4
description: "Jak używać web search i uploadować pliki w Claude.ai – analiza PDF dokumentów obrazów CSV i kodu."
permalink: /kurs-claude-ai/web-search-pliki/
---

# Web Search i upload plików

## Web Search

Claude może przeszukiwać internet w czasie rzeczywistym.

**Jak włączyć:** W polu wiadomości kliknij ikonę 🌐 lub napisz prompt zawierający prośbę o aktualne informacje.

**Kiedy używać:**
- Aktualne ceny, kursy walut
- Najnowsze wiadomości
- Sprawdzanie dostępności produktów
- Research na aktualne tematy

```
Przykłady promptów z web search:

"Wyszukaj i porównaj aktualne ceny hostingu 
w Cyber_Folks i LH.pl"

"Jakie są najnowsze zmiany w algorytmie Google 
w 2025 roku?"

"Znajdź 5 najlepiej ocenianych wtyczek cache 
dla WordPress w 2025"
```

## Upload plików

Kliknij 📎 i załącz plik. Claude obsługuje:

| Typ pliku | Co Claude może zrobić |
|-----------|----------------------|
| **PDF** | Streszczenie, analiza, wyciąganie danych, Q&A |
| **Obraz** (JPG/PNG) | Opis, analiza, OCR tekstu ze zdjęcia |
| **CSV/Excel** | Analiza danych, wykresy, wnioski |
| **Kod** (py/js/php) | Review, debugowanie, refaktoryzacja |
| **TXT/MD** | Redakcja, tłumaczenie, analiza |
| **DOCX** | Analiza, podsumowanie, edycja |

## Przykłady użycia z plikami

### Analiza umowy PDF
```
[załącz umowę.pdf]

Przeanalizuj tę umowę i:
1. Wymień kluczowe zobowiązania obu stron
2. Wskaż potencjalnie niekorzystne zapisy dla mnie (jako najemcy)
3. Zasugeruj pytania do zadania prawnikowi
```

### Analiza danych CSV
```
[załącz sprzedaz.csv]

Przeanalizuj dane sprzedażowe i:
1. Wskaż 3 najlepiej sprzedające się produkty
2. Porównaj sprzedaż miesiąc do miesiąca
3. Zaproponuj wnioski i rekomendacje
```

### OCR ze zdjęcia
```
[załącz zdjęcie paragonu]
Przepisz tekst z tego paragonu do tabeli: 
produkt | cena jednostkowa | ilość | suma
```
