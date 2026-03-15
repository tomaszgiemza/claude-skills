---
layout: with-comments
title: "Lekcja 1 – Prompt Engineering głęboko"
parent: "🚀 Kurs zaawansowany"
nav_order: 1
description: "Zaawansowany prompt engineering dla Claude – chain of thought, few-shot, XML, system prompts i testowanie promptów."
permalink: /kurs-zaawansowany/lekcja-1/
---

# Lekcja 1 – Prompt Engineering głęboko

W kursie dla początkujących nauczyłeś się podstaw. Tu idziemy głębiej – techniki które naprawdę robią różnicę.

## Chain of Thought – zmuszaj Claude do myślenia

Standardowe pytanie daje standardową odpowiedź. Gdy każesz Claude myśleć krok po kroku, jakość skacze.

**Bez chain of thought:**
> Który hosting wybrać do WordPressa?

**Z chain of thought:**
> Analizuję wybór hostingu WordPress. Przemyśl to krok po kroku:
> 1. Najpierw zdefiniuj kluczowe wymagania dla typowego bloga firmowego
> 2. Oceń każde wymaganie dla hostingów: Cyber_Folks, LH.pl, SiteGround
> 3. Na podstawie tej analizy podaj rekomendację z uzasadnieniem

Drugi prompt da znacznie lepszą, bardziej przemyślaną odpowiedź.

## Few-Shot – ucz przez przykłady

Pokaż Claude przykłady oczekiwanego formatu zamiast go opisywać.

```
Kategoryzuj opinie klientów. Format: OPINIA | KATEGORIA | SENTYMENT

Przykłady:
"Dostawa bardzo szybka, produkt zgodny z opisem" | logistyka | pozytywny
"Produkt tani ale jakość mogłaby być lepsza" | jakość produktu | mieszany
"Obsługa klienta nie odpowiada na emaile" | obsługa klienta | negatywny

Teraz sklasyfikuj:
"Paczka przyszła po 2 dniach, wszystko zapakowane starannie" |
```

## XML dla złożonych promptów

Gdy prompt jest długi i złożony – XML pomaga Claude zrozumieć strukturę.

```xml
<kontekst>
  Prowadzę sklep z elektroniką online, 500 produktów w ofercie.
  Mamy problem z porzuconymi koszykami – 70% użytkowników nie finalizuje zakupu.
</kontekst>

<zadanie>
  Zaproponuj 5 konkretnych zmian na stronie checkout które mogą zmniejszyć 
  porzucone koszyki. Każda zmiana: opis + dlaczego działa + trudność wdrożenia.
</zadanie>

<format>
  Tabela: Zmiana | Opis (2 zdania) | Uzasadnienie | Trudność (1-5)
  Na końcu: TOP 3 do wdrożenia w pierwszej kolejności.
</format>
```

## Testowanie i iteracja promptów

Dobry prompt to rzadko pierwsza wersja. Mój process:

1. Napisz wstępny prompt
2. Oceń odpowiedź: co jest dobre, co nie
3. Zidentyfikuj słabe miejsca: *"Claude nie uwzględnił X"*
4. Popraw prompt dodając wymaganie X
5. Porównaj wyniki
6. Powtarzaj aż wynik jest konsekwentnie dobry

Dla ważnych promptów których używam regularnie – testuję na 3-5 różnych przykładach zanim uznam że prompt jest "gotowy".

{: .note }
Następna lekcja: [Claude Code w praktyce](/kurs-zaawansowany/lekcja-2/)
