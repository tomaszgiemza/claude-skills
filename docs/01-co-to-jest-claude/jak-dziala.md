---
layout: with-comments
title: "Jak Claude działa – bez żargonu"
parent: "🧠 Co to jest Claude?"
nav_order: 2
description: "Jak działa Claude AI od środka – LLM, tokeny, okno kontekstu i Constitutional AI wyjaśnione po ludzku bez technicznego żargonu."
permalink: /co-to-jest-claude/jak-dziala/
---

# Jak Claude działa – bez żargonu

Nie musisz znać się na AI żeby skutecznie używać Claude. Ale kilka rzeczy warto rozumieć, bo bezpośrednio wpływają na to jak z nim pracujesz.

## Wyobraź sobie tak...

Claude przeczytał setki miliardów słów – artykuły, książki, kod, dokumentacje, rozmowy z internetu. Na tej podstawie nauczył się jak wygląda dobra odpowiedź na praktycznie każde pytanie.

Gdy piszesz do Claude, on nie "szuka odpowiedzi w bazie" – generuje ją słowo po słowie, przewidując co powinno pojawić się dalej, na podstawie wszystkiego czego się nauczył i Twojego pytania.

{: .highlight }
**Ważne:** Claude nie wie co dzieje się w świecie po dacie jego treningu. Nie ma dostępu do internetu chyba że włączysz web search. Może się mylić – zawsze weryfikuj ważne fakty.

## Okno kontekstu – dlaczego to ważne

Okno kontekstu to ilość tekstu którą Claude "widzi" naraz w jednej rozmowie.

```
Claude Sonnet 4.5: ~200 000 tokenów
≈ 150 000 słów
≈ 500 stron A4
```

**Co to oznacza w praktyce?**

Możesz wrzucić całą dokumentację projektu, długi kontrakt, kilkanaście plików kodu – Claude przeczyta to wszystko i odpowie z pełnym kontekstem. To ogromna przewaga nad innymi narzędziami.

Ale uwaga: gdy rozmowa jest bardzo długa, Claude zaczyna "zapominać" najstarsze wiadomości. Jeśli pracujesz nad czymś długo – warto co jakiś czas zacząć nową rozmowę z podsumowaniem kontekstu.

## Tokeny – co to jest?

Claude nie przetwarza słów, przetwarza **tokeny**. Token to fragment słowa (mniej więcej 0.6 słowa w języku polskim).

Nie musisz tego rozumieć do codziennego użytkowania. Ma znaczenie przy API, gdzie płacisz za tokeny.

## Constitutional AI – dlaczego Claude jest inny

To co wyróżnia Claude to metoda treningu. Anthropic opracował **Constitutional AI** – zamiast tylko uczyć Claude co mówić, uczyli go rozumieć zasady etyczne.

Efekt praktyczny: Claude potrafi odmówić i wytłumaczyć dlaczego. Nie robi tego mechanicznie – naprawdę "rozumie" (w pewnym sensie) co jest problematyczne a co nie.

Moim zdaniem to widać w codziennym użytkowaniu – Claude jest bardziej przewidywalny i rzadziej robi rzeczy które potem żałujesz.

{: .note }
Następna lekcja: [Historia i wartości Anthropic](/co-to-jest-claude/historia/)
