# Claude Skills – Giemza

> Kompletny przewodnik po Claude AI po polsku. Kursy, prompty, Claude Code, API i integracje.

**[→ claude.giemza.nl](https://claude.giemza.nl)**

---

## O projekcie

Publiczne repozytorium wiedzy o Claude AI prowadzone przez **Tomasz Giemza** ([giemza.nl](https://giemza.nl)).

Nie piszę teorii. Każda lekcja, prompt i skill to coś czego sam używam lub przetestowałem. Jeśli coś nie działa – poprawiam. Jeśli Anthropic wypuści nową funkcję – opisuję ją jako jeden z pierwszych po polsku.

---

## Co znajdziesz na stronie

| Sekcja | Opis |
|--------|------|
| 🧠 Co to jest Claude? | Jak działa, historia Anthropic, bez żargonu |
| ⚖️ Porównanie modeli | Opus / Sonnet / Haiku, Claude vs ChatGPT vs Gemini |
| 🔧 Funkcje Claude | Projects, Memory, Web Search, Artefakty |
| 💻 Claude i kodowanie | Claude Code – instalacja, CLAUDE.md, MCP |
| 🖥️ Claude na VPS | Instalacja, automatyzacja, agent na serwerze |
| 🏠 Claude lokalnie | Ollama, modele open source, chmura vs lokalnie |
| 🔌 Claude API | Pierwsze kroki, PHP/WordPress, JavaScript |
| 🔗 Integracje | Gmail, Notion, Slack, VS Code, n8n |
| 📰 Claude News | Nowości i aktualizacje 2025 |
| 🎓 Kurs dla początkujących | 5 lekcji – od zera do efektywnej pracy |
| 🚀 Kurs zaawansowany | Prompt engineering, Claude Code, agenty AI |
| ⚡ Prompty i skille | Copywriting, WordPress, SEO, Biznes, Dev, Marketing |

---

## Struktura repozytorium

```
claude-skills/
├── _config.yml                    # Konfiguracja Jekyll + Just the Docs
├── index.md                       # Strona główna
├── komentarze.md                  # Sekcja komentarzy Giscus
├── Gemfile                        # Zależności Ruby
├── _includes/
│   └── giscus.html                # Widget komentarzy GitHub Discussions
├── _layouts/
│   └── with-comments.html         # Layout ze zintegrowanym Giscus
├── .github/workflows/
│   └── deploy.yml                 # GitHub Actions – auto deploy
└── docs/
    ├── 01-co-to-jest-claude/
    ├── 02-porownanie-modeli/
    ├── 03-funkcje/
    ├── 04-kodowanie/
    ├── 05-vps/
    ├── 06-lokalna/
    ├── 07-api/
    ├── 08-integracje/
    ├── 09-news/
    ├── 10-kurs-poczatkujacy/
    ├── 11-kurs-zaawansowany/
    └── 12-prompty/
        ├── copywriting/
        ├── wordpress/
        ├── seo/
        ├── biznes/
        ├── development/
        └── marketing/
```

---

## Uruchomienie lokalne

```bash
# Wymagania: Ruby 3.x, Bundler
git clone https://github.com/tomaszgiemza/claude-skills
cd claude-skills
bundle install
bundle exec jekyll serve
# → http://localhost:4000
```

---

## Konfiguracja Giscus (komentarze)

1. Włącz **Discussions** w tym repozytorium:
   Settings → Features → Discussions ✅

2. Wejdź na [giscus.app](https://giscus.app) i skonfiguruj dla repo `tomaszgiemza/claude-skills`

3. Skopiuj `repo_id` i `category_id` do `_config.yml`:

```yaml
giscus:
  repo: "tomaszgiemza/claude-skills"
  repo_id: "WKLEJ_TUTAJ"
  category: "Comments"
  category_id: "WKLEJ_TUTAJ"
```

---

## Wdrożenie

Strona jest automatycznie budowana i wdrażana przez **GitHub Actions** po każdym pushu do gałęzi `main`.

Subdomena `claude.giemza.nl` wskazuje na GitHub Pages przez rekord CNAME w DNS.

---

## Zgłaszanie błędów i sugestii

- **Komentarze na stronie:** [claude.giemza.nl/komentarze](https://claude.giemza.nl/komentarze)
- **GitHub Issues:** zakładka Issues w tym repo
- **Kontakt:** [giemza.nl](https://giemza.nl)

---

## Licencja

Treści na tej stronie są udostępniane na licencji [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.pl) – możesz je swobodnie używać i udostępniać z podaniem autora.

Kod źródłowy (szablony, konfiguracja) – MIT.

---

*Prowadzone przez [Tomasz Giemza](https://giemza.nl) · Aktualizowane regularnie*
