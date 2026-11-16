# linear-algebra-notes

Online Jupyter Book for linear algebra (Math 279 spine, with Math 56 / EECS 16A enrichment).

## Local preview

```bash
pip install -r requirements-build.txt
pip install -r requirements.txt
# Live site + execute code cells so outputs appear
jupyter book start --execute
```

Build static HTML (outputs baked in via `--execute`):

```bash
jupyter book build --html --execute
```

On the published site, use the **power button** on a page (Binder / in-page Jupyter) to re-run cells interactively.

## Content layout

| Path | Role |
|---|---|
| `intro.md` | Book landing page |
| `chapters/ch00/` | Chapter 0 — coding readiness (Week 0) |
| `docs/` | Internal curriculum notes (not in book TOC) |
| `myst.yml` | MyST / Jupyter Book config + TOC |

## Chapter 0

Jupyter, Python basics, NumPy arrays (create / index / slice / reshape / elementwise ops), and simple plots. Matrix multiplication, `solve`, and `inv` come later with the math.
