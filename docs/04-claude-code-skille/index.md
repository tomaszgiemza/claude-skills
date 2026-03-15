---
layout: default
title: "🛠️ Claude Code – skille"
nav_order: 5
has_children: true
description: "Publiczne skille do Claude Code – gotowe SKILL.md pliki do użycia w projektach. WordPress Python Docker i inne."
permalink: /claude-code-skille/
---

# 🛠️ Claude Code – skille

Publiczne skille (SKILL.md) gotowe do użycia w Claude Code.

## Czym są skille w Claude Code?

Skille to pliki `SKILL.md` które Claude Code czyta przed wykonaniem zadania. Zawierają instrukcje, najlepsze praktyki i wzorce dla konkretnych technologii.

{: .highlight }
Umieść plik `SKILL.md` w katalogu projektu lub w `/mnt/skills/` – Claude Code automatycznie go przeczyta.

## Dostępne skille

| Skill | Technologia | Opis |
|-------|-------------|------|
| [WordPress](/claude-code-skille/wordpress) | PHP/WP | Tworzenie motywów wtyczek i snippetów |
| [Python Scripts](/claude-code-skille/python) | Python | Skrypty automatyzacji i CLI tools |
| [Docker Compose](/claude-code-skille/docker) | Docker | Konfiguracje kontenerów i stack'ów |
| [Jekyll/Just the Docs](/claude-code-skille/jekyll) | Ruby/Jekyll | Tworzenie dokumentacji i stron statycznych |
| [SEO Content](/claude-code-skille/seo-content) | Markdown | Pisanie treści zoptymalizowanych pod SEO |

## Jak używać skilli?

### Opcja 1 – W projekcie
```bash
# Skopiuj SKILL.md do katalogu projektu
cp wordpress-skill.md /moj-projekt/SKILL.md

# Claude Code automatycznie przeczyta plik
claude "Dodaj nową funkcję do functions.php"
```

### Opcja 2 – Globalnie
```bash
# Umieść w /mnt/skills/
cp wordpress-skill.md /mnt/skills/wordpress/SKILL.md
```

### Opcja 3 – Przez CLAUDE.md
W pliku `CLAUDE.md` w katalogu projektu:
```markdown
Przed każdym zadaniem przeczytaj skill:
@/mnt/skills/wordpress/SKILL.md
```
