---
layout: default
title: "Skill – Jekyll / Just the Docs"
parent: "🛠️ Claude Code – skille"
nav_order: 3
description: "Publiczny skill do Claude Code dla Jekyll i Just the Docs – tworzenie dokumentacji stron statycznych i GitHub Pages."
permalink: /claude-code-skille/jekyll/
---

# Skill – Jekyll / Just the Docs

Skill do tworzenia dokumentacji i stron statycznych z Jekyll i motywem Just the Docs.

## Treść pliku SKILL.md

````markdown
---
name: jekyll-just-the-docs
description: "Tworzenie dokumentacji i stron statycznych z Jekyll + Just the Docs na GitHub Pages"
---

# Jekyll / Just the Docs Skill

## Stack
- Jekyll 4.x
- Just the Docs theme ~0.10.0
- GitHub Pages
- Markdown + Liquid templates

## Front Matter – wymagane pola

### Strona nadrzędna (kategoria)
```yaml
---
layout: default
title: "Emoji Tytuł Kategorii"
nav_order: 2
has_children: true
description: "Opis dla SEO (150-160 znaków)"
permalink: /slug-kategorii/
---
```

### Strona podrzędna (lekcja/artykuł)
```yaml
---
layout: default
title: "Tytuł strony"
parent: "Emoji Tytuł Kategorii"  # musi być IDENTYCZNY z parent title
nav_order: 1
description: "Opis dla SEO"
permalink: /slug-kategorii/slug-strony/
---
```

## Callouts (bloki informacyjne)
```markdown
{: .highlight }
Ważna informacja lub wskazówka

{: .note }
Dodatkowa uwaga

{: .warning }
Ostrzeżenie – uważaj na to
```

## Tabele
```markdown
| Kolumna 1 | Kolumna 2 | Kolumna 3 |
|-----------|-----------|-----------|
| Wartość   | Wartość   | Wartość   |
```

## Zasady
- permalink zawsze kończy się `/`
- parent musi być identyczny z title strony nadrzędnej
- nav_order decyduje o kolejności w menu
- Nie używaj `layout: home` – tylko `layout: default`
- Sekcja `exclude:` w `_config.yml` musi zawierać `vendor/`
- baseurl: "" gdy custom domain, "/repo-name" gdy github.io
````
