---
layout: default
title: "Sztuka promptowania"
parent: "📖 Kurs Claude.ai"
nav_order: 2
description: "Jak pisać skuteczne prompty dla Claude – struktura dobrego promptu rola kontekst format przykłady i anty-przykłady."
permalink: /kurs-claude-ai/promptowanie/
---

# Sztuka promptowania

Jakość odpowiedzi Claude zależy w 80% od jakości Twojego promptu.

## Anatomia dobrego promptu

```
[ROLA]     Kim ma być Claude?
[KONTEKST] Co musisz wiedzieć?
[ZADANIE]  Co dokładnie chcesz?
[FORMAT]   Jak ma wyglądać odpowiedź?
[PRZYKŁAD] (opcjonalnie) Przykład oczekiwanego wyniku
```

## Przykład – zły vs dobry prompt

**❌ Zły prompt:**
```
Napisz artykuł o marketingu.
```

**✅ Dobry prompt:**
```
Jesteś doświadczonym copywriterem B2B.

Napisz artykuł blogowy (1200 słów) na temat 
"Email marketing dla małych firm w 2025 roku".

Odbiorca: właściciele małych firm bez technicznej wiedzy
Ton: przystępny, praktyczny, bez żargonu
Struktura: wstęp, 4 sekcje H2, podsumowanie z CTA
Słowo kluczowe: "email marketing małe firmy"

Zacznij od zaskakującego faktu lub statystyki.
```

## Techniki promptowania

### Nadaj rolę
```
Jesteś ekspertem od SEO z 10-letnim doświadczeniem...
Jesteś prawnikiem specjalizującym się w RODO...
Jesteś senior developerem Python...
```

### Podaj kontekst
```
Prowadzę sklep z odzieżą damską w Polsce.
Mam 500 subskrybentów newslettera.
Używam WordPress z WooCommerce.
```

### Określ format
```
Odpowiedz w formie listy punktowanej.
Użyj tabeli porównawczej.
Napisz w max 3 zdaniach.
Podaj odpowiedź w JSON.
Użyj nagłówków H2 i H3.
```

### Poproś o przemyślenie
```
Zanim odpowiesz, przemyśl problem krok po kroku.
Najpierw wymień wszystkie możliwe podejścia, 
potem wybierz najlepsze i uzasadnij.
```

## Iteracja promptów

Nie musisz za pierwszym razem napisać idealnego promptu. Iteruj:

1. Wyślij wstępny prompt
2. Oceń odpowiedź
3. Doprecyzuj: *"Zrób to samo ale bardziej..."* / *"Skróć sekcję X"* / *"Dodaj przykłady"*
4. Powtarzaj aż do satysfakcji

{: .highlight }
**Zasada:** Im więcej kontekstu dajesz, tym lepsza odpowiedź. Claude nie czyta w myślach – musi wiedzieć co chcesz osiągnąć.
