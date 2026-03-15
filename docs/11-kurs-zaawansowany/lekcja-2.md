---
layout: with-comments
title: "Lekcja 2 – Claude Code w codziennej pracy"
parent: "🚀 Kurs zaawansowany"
nav_order: 2
description: "Jak efektywnie używać Claude Code do programowania – workflow, CLAUDE.md, obsługa dużych projektów i debugowanie."
permalink: /kurs-zaawansowany/lekcja-2/
---

# Lekcja 2 – Claude Code w codziennej pracy

Mam Claude Code zainstalowanego od kiedy wyszedł z beta. Oto mój realny workflow i co faktycznie działa.

## Mój codzienny workflow

**Rano – przegląd zadań:**
```bash
cd /var/www/projekt
claude "Co mam do zrobienia wg CLAUDE.md i ostatnich commitów?"
```

**Nowe zadanie:**
```bash
claude "Muszę dodać [opis funkcji]. Zanim zaczniesz: 
1) Opisz jak to zaimplementujesz
2) Jakie pliki zmienisz  
3) Czy są ryzyka?
Zatwierdź plan zanim zaczniesz kodować."
```

Zawsze każę Claude najpierw opisać plan. Oszczędza to cofania gdy pójdzie w złym kierunku.

**Po zakończeniu:**
```bash
claude "Sprawdź wszystkie zmiany które zrobiłeś i napisz commit message według konwencji Conventional Commits"
```

## Jak pracować z dużymi projektami

Claude Code widzi wszystkie pliki ale ma ograniczone okno kontekstu. Dla dużych projektów:

**Ogranicz zakres:**
```bash
claude "Skup się tylko na plikach w /wp-content/themes/moj-motyw/. Nie modyfikuj nic poza tym katalogiem."
```

**Używaj CLAUDE.md agresywnie:**
Im więcej kontekstu w CLAUDE.md, tym mniej Claude musi "odkrywać" i tym mniej okna kontekstu marnuje.

## Debugowanie z Claude Code

```bash
# Pokaż błąd i poproś o diagnozę
claude "Dostaję ten błąd: [ERROR]. Oto stack trace: [PASTE]. 
Zdiagnozuj przyczynę bez wprowadzania zmian, najpierw."
```

Zawsze proszę o diagnozę PRZED naprawą. Claude czasem idzie w złym kierunku – lepiej zweryfikować plan.

## Czego unikam

- Nie daję Claude Code dostępu do całego serwera produkcyjnego
- Zawsze przeglądam co zrobił przed mergeowaniem
- Nie pozwalam na autonomiczne modyfikacje bazy danych bez zatwierdzenia

{: .highlight }
**Moje zdanie:** Claude Code to najbardziej produktywne narzędzie deweloperskie jakie używam. Ale wymaga myślenia – nie możesz go puścić bez nadzoru i liczyć że wszystko będzie dobrze.

{: .note }
Następna lekcja: [Automatyzacje przez API](/kurs-zaawansowany/lekcja-3/)
