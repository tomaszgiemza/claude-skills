---
layout: with-comments
title: "Lekcja 5 – Claude w workflow firmy"
parent: "🚀 Kurs zaawansowany"
nav_order: 5
description: "Jak wdrożyć Claude w firmie – onboarding pracowników, projekty teamowe, procesy i mierzenie ROI."
permalink: /kurs-zaawansowany/lekcja-5/
---

# Lekcja 5 – Claude w workflow firmy

Używanie Claude samemu to jedno. Wdrożenie go w teamie to zupełnie inna gra.

## Gdzie zacząć w firmie?

Nie próbuj wdrożyć Claude wszędzie naraz. Zacznij od jednego, dobrze zdefiniowanego przypadku użycia gdzie efekt będzie widoczny.

**Dobre punkty startowe:**
- Obsługa klienta – draft odpowiedzi na emaile
- Marketing – pierwsze wersje postów i treści
- HR – drafty ogłoszeń o pracę i emaile rekrutacyjne
- Sprzedaż – przygotowanie ofert i follow-upów

## Team Plan i wspólne Projects

Na planie Team możesz tworzyć **wspólne Projects** – cały team ma dostęp do tego samego kontekstu i instrukcji.

**Przykład: Projekt "Komunikacja z klientami"**
```
Instrukcje projektu:
Firma: [nazwa], branża: [branża]
Ton komunikacji: profesjonalny ale ciepły
Zawsze podpisuj się imieniem i nazwiskiem
Nie obiecuj terminów bez konsultacji z managerem
Standardowe powitanie: "Dzień dobry, [imię klienta]"
```

Każdy pracownik otwiera rozmowę w tym projekcie i ma ten sam kontekst.

## Standaryzacja promptów

Stwórz firmową bibliotekę promptów do powtarzalnych zadań:

```markdown
# Firmowe prompty – [Nazwa Firmy]

## Email z ofertą handlową
Kontekst: [fill] | Produkt: [fill] | Klient: [fill] | Cena: [fill]
Prompt: "Jesteś senior handlowcem [firma]. Napisz email z ofertą..."

## Odpowiedź na reklamację  
Treść reklamacji: [paste] | Nasza wina: [tak/nie] | Propozycja: [fill]
Prompt: "Napisz profesjonalną odpowiedź na reklamację..."
```

## Mierzenie ROI

Jak uzasadnić $20/mies * liczba pracowników?

Prosta kalkulacja:
- Ile czasu tygodniowo pracownik oszczędza? (np. 3h)
- Ile kosztuje ta godzina? (np. 50 zł/h)
- Tygodniowa oszczędność: 150 zł
- Miesięczna oszczędność: ~600 zł
- Koszt Claude Pro: $20 ≈ 80 zł

ROI: 600 / 80 = **7.5x zwrot z inwestycji**

---

## Gratulacje – ukończyłeś kurs zaawansowany!

Wiesz już jak:
- ✅ Pisać prompty na poziomie eksperckim
- ✅ Używać Claude Code do programowania
- ✅ Budować automatyzacje przez API
- ✅ Projektować agenty AI
- ✅ Wdrażać Claude w teamie

**Co dalej?** Przejdź do [Promptów i Skilli](/prompty/) – gotowych szablonów do użycia od zaraz.
