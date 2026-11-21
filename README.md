# linear-algebra-notes

Interactive Jupyter Book for linear algebra (Math 279 spine, Math 56 / EECS 16A enrichment).

Code examples illustrate ideas with outputs already included; interactive demonstrations run in the page. Readers do not need to install anything or create an environment.

## Contributor preview

These commands are only for contributors building the site locally:

```bash
pip install -r requirements-build.txt
jupyter book start --execute
```

Static HTML:

```bash
jupyter book build --html --execute
```

## Layout

| Path | Role |
|---|---|
| `intro.md` | Landing page |
| `chapters/ch00`–`ch08` | Sections 0–8 (through calendar week 8) |
| `docs/` | Internal curriculum notes (not in book TOC) |
| `myst.yml` | TOC + site config |

Naming follows Inferential Thinking style: `1 Systems…`, `1.1 …` (no “Chapter” prefix).
