# linear-algebra-notes
Online JupyterBook for learning Linear Algebra

## Getting Started with Jupyterbook

# 1. Install CLI (if not already)
pip install "jupyter-book>=2.0.0"

# 2. Create myst.yml
jupyter book init

# 3. Add content (manually create files like intro.md, chapters/*.md, or .ipynb)
#    Then generate TOC:
jupyter book init --write-toc

# 4. Preview locally
jupyter book start

# 5. Add GitHub Pages CI
jupyter book init --gh-pages
