---
layout: default
title: "Zaawansowane techniki"
parent: "📖 Kurs Claude.ai"
nav_order: 5
description: "Zaawansowane techniki promptowania Claude – chain of thought few-shot prompting format XML sterowanie długością i temperatura."
permalink: /kurs-claude-ai/zaawansowane/
---

# Zaawansowane techniki promptowania

## Chain of Thought (łańcuch myślenia)

Poproś Claude żeby myślał krok po kroku przed odpowiedzią.

```
Zanim odpowiesz, rozpisz swoje rozumowanie krok po kroku,
a dopiero na końcu podaj ostateczną odpowiedź.
```

Kiedy używać: zadania matematyczne, logiczne, decyzyjne, analizy.

## Few-Shot Prompting

Pokaż Claude przykłady oczekiwanych odpowiedzi.

```
Klasyfikuj opinie klientów jako: POZYTYWNA / NEGATYWNA / NEUTRALNA

Przykład 1:
Opinia: "Świetna obsługa, szybka dostawa!"
Klasyfikacja: POZYTYWNA

Przykład 2:
Opinia: "Produkt ok, ale dostawa trwała 2 tygodnie."
Klasyfikacja: NEUTRALNA

Teraz sklasyfikuj:
Opinia: "Nigdy więcej nie zamówię, totalna porażka."
Klasyfikacja:
```

## Format XML dla struktury

Claude świetnie radzi sobie z XML-em do organizacji złożonych promptów:

```xml
<zadanie>
  <rola>Jesteś ekspertem SEO</rola>
  <kontekst>
    Mam bloga o WordPress z 50 artykułami.
    Średni ruch: 2000 wizyt/miesiąc.
  </kontekst>
  <cel>Zwiększyć ruch do 5000 wizyt/miesiąc</cel>
  <format>
    Plan działań na 3 miesiące.
    Każdy miesiąc: 3-5 konkretnych zadań z priorytetem.
  </format>
</zadanie>
```

## Sterowanie długością i formatem

```
Odpowiedz w max 3 zdaniach.
Napisz szczegółową odpowiedź (min. 500 słów).
Użyj TYLKO listy punktowanej, bez wstępu.
Odpowiedz w JSON z polami: "wniosek", "ryzyko", "rekomendacja".
Pomiń oczywiste informacje, skup się na niuansach.
```

## Technika "Zagraj rolę krytyka"

```
Napisałem ten tekst marketingowy. 
Najpierw oceń go surowo jako sceptyczny klient,
potem jako doświadczony copywriter.
Na końcu podaj 3 konkretne ulepszenia.

[tekst]
```

## Prompt do iteracji

Gdy odpowiedź jest dobra ale nie idealna:
```
Prawie dobrze. Popraw:
- Skróć wstęp o połowę
- Dodaj konkretne przykłady do punktu 2
- Zakończ mocniejszym CTA
Zachowaj resztę bez zmian.
```

{: .highlight }
**Złota zasada:** Traktuj Claude jak bardzo inteligentnego nowego pracownika. Daj mu kontekst, cel i format – a dostarczy świetne wyniki.
