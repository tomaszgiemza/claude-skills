---
layout: with-comments
title: "Lekcja 2 – Jak rozmawiać z Claude"
parent: "🎓 Kurs dla początkujących"
nav_order: 2
description: "Jak pisać skuteczne prompty dla Claude – kontekst, rola, format, iteracja. Kurs Claude dla początkujących – lekcja 2."
permalink: /kurs-poczatkujacy/lekcja-2/
---

# Lekcja 2 – Jak rozmawiać z Claude

Jakość odpowiedzi Claude zależy od jakości Twojego pytania. To brzmi banalnie, ale naprawdę robi ogromną różnicę.

## Zasada kontekstu

Claude nie zna Twojej sytuacji. Musisz mu ją opisać.

**Zły przykład:**
> Napisz email do klienta.

Claude nie wie: do kogo, w jakiej sprawie, jaki ton, co się stało.

**Dobry przykład:**
> Napisz email do klienta który złożył zamówienie 5 dni temu i pyta dlaczego jeszcze nie dostał paczki. Przesyłka opóźniła się przez kuriera. Chcę przeprosić, wyjaśnić sytuację i zaproponować 10% rabatu na kolejne zamówienie. Ton: uprzejmy i profesjonalny.

## Trzy elementy dobrego promptu

**1. Kim jest Claude w tej sytuacji?**
*"Jesteś doświadczonym copywriterem..."*
*"Jesteś moim asystentem do zarządzania emailami..."*

**2. Co ma zrobić?**
Konkretne zadanie z detalami.

**3. Jak ma wyglądać wynik?**
*"Odpowiedz w formie listy punktowanej"*
*"Napisz maksymalnie 3 zdania"*
*"Użyj formalnego języka"*

## Iteracja – poprawiaj kolejnymi wiadomościami

Nie musisz pisać idealnego promptu za pierwszym razem. Możesz poprawiać:

```
Ty: "Napisz opis produktu dla słuchawek bezprzewodowych"
Claude: [pisze opis]
Ty: "Dodaj informację o czasie działania baterii (30h) i skróć o połowę"
Claude: [poprawia]
Ty: "Zmień ton na bardziej entuzjastyczny"
Claude: [poprawia]
```

## Czego NIE robić

- Nie bój się być bardzo szczegółowy – Claude tego potrzebuje
- Nie zakładaj że Claude wie co masz na myśli – napisz wprost
- Nie pytaj o zbyt wiele rzeczy naraz – lepiej kilka osobnych rozmów

{: .highlight }
**Ćwiczenie:** Weź jakieś realne zadanie z Twojej pracy i napisz prompt według schematu: kontekst + zadanie + format oczekiwanej odpowiedzi.

{: .note }
Następna lekcja: [Projects i organizacja pracy](/kurs-poczatkujacy/lekcja-3/)
