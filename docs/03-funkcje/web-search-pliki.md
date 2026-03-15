---
layout: with-comments
title: "Web Search i analiza plików"
parent: "🔧 Funkcje Claude"
nav_order: 2
description: "Jak używać web search i uploadować pliki w Claude.ai – analiza PDF, zdjęcia OCR, CSV, kod i dokumenty Word."
permalink: /funkcje/web-search-pliki/
---

# Web Search i analiza plików

## Web Search – Claude z dostępem do internetu

Claude domyślnie nie ma dostępu do internetu – jego wiedza ma datę graniczną. Web search to zmienia.

### Jak włączyć

W polu wiadomości kliknij ikonę **globusa 🌐** przed wysłaniem. Lub po prostu zapytaj o coś aktualnego – Claude sam zapyta czy szukać.

### Kiedy tego używać

Dobre zastosowania:
- Aktualne ceny, kursy walut, dane giełdowe
- Najnowsze wiadomości i wydarzenia
- Weryfikacja faktów które mogły się zmienić
- Research konkurencji (aktualne informacje)
- Sprawdzenie statusu narzędzi (czy coś działa)

Czego unikam: nie klikam globusa do zadań które nie wymagają aktualności. Claude radzi sobie lepiej bez szukania przy zadaniach gdzie liczy się rozumowanie, nie dane.

## Analiza plików – co Claude potrafi

Kliknij spinacz 📎 i wgraj plik. Claude obsługuje:

| Typ pliku | Co Claude z tym zrobi |
|-----------|----------------------|
| **PDF** | Streszczenie, Q&A, wyciąganie danych, analiza |
| **Obraz** (JPG/PNG) | Opis zawartości, OCR tekstu, analiza grafik |
| **CSV** | Analiza danych, trendy, wnioski, obliczenia |
| **Kod** (py/js/php/inne) | Review, debugowanie, refaktoryzacja |
| **DOCX/TXT/MD** | Redakcja, tłumaczenie, analiza |
| **XLSX** | Analiza arkusza, formuły, wnioski |

### Praktyczne przykłady

**Analiza umowy PDF:**
Wrzuć plik i napisz: *"Przeczytaj tę umowę i wypisz: 1) moje główne zobowiązania, 2) terminy płatności, 3) klauzule które powinienem skonsultować z prawnikiem"*

**OCR ze zdjęcia wizytówki:**
Zrób zdjęcie wizytówki i napisz: *"Przepisz dane kontaktowe z tej wizytówki do formatu: Imię Nazwisko | stanowisko | email | telefon | firma"*

**Analiza danych sprzedażowych:**
Wrzuć CSV i napisz: *"Który produkt sprzedawał się najlepiej w Q3? Porównaj z Q2 i zasugeruj co powinniśmy zamówić więcej."*

{: .highlight }
**Wskazówka:** Możesz wrzucić kilka plików naraz. Claude przetwarza wszystkie i potrafi je ze sobą porównać.

{: .note }
Następna strona: [Artefakty](/funkcje/artefakty/)
