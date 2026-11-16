# Linear Algebra Notes

An applied Jupyter Book for an introductory linear algebra course aligned with C-ID MATH 250. The book combines mathematical reasoning, executable Python examples, quick checks, and labs.

## Local setup

Python 3.11 or newer is recommended.

```bash
python -m venv .venv
```

Activate the environment on Windows:

```powershell
.\.venv\Scripts\Activate.ps1
```

Or activate it on macOS/Linux:

```bash
source .venv/bin/activate
```

Install the authoring and course dependencies:

```bash
python -m pip install -r requirements-build.txt -r requirements.txt
```

## Preview and build

Start the live authoring server:

```bash
jupyter book start
```

Build the static site:

```bash
jupyter book build --execute --html
```

The `--execute` flag runs the MyST code cells so that the published book contains current outputs. The generated site is written under `_build/`. GitHub Actions executes, builds, and deploys the book when changes reach `main`.

## Content structure

- `intro.md` — book landing page
- `chapters/` — published chapters and labs
- `docs/` — internal curriculum planning documents
- `myst.yml` — book metadata, navigation, and site configuration
- `_static/` — styles and site assets

Chapter content uses MyST Markdown. Executable examples use the ```` ```{code-cell} python ```` directive.

## Authoring checks

Before opening a pull request:

1. restart and run any modified notebook content from a clean kernel;
2. run `jupyter book build --execute --html`;
3. inspect warnings and test internal links; and
4. preview the affected pages at desktop and narrow widths.
