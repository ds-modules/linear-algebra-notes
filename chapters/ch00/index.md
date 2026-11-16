---
kernelspec:
  name: python3
  display_name: Python 3
---

# Chapter 0. Coding Readiness

This is **Week 0**: get comfortable running code before the math starts. We are **not** learning linear algebra yet — only the coding tools later labs will use.

## Learning objectives

By the end of this chapter you should be able to:

- Open and run a Jupyter notebook
- Write basic Python (variables, lists, loops, functions)
- Create **NumPy** arrays; index, slice, and reshape them
- Do elementwise arithmetic (`+`, `*`, scalar multiply) and check `.shape`
- Make a simple 2D plot with **matplotlib**

Matrix multiplication, solving $Ax=b$, inverses, and other linear-algebra operations show up in later chapters — when those ideas are taught.

## Why this comes first

Later notebooks store data in arrays (a row of numbers, a table of numbers). If array basics are shaky, every lab turns into debugging. Spend this week on fluency; the math can wait one week.

## Chapter guide

1. [Jupyter and Python basics](jupyter-python.md)
2. [NumPy arrays](numpy.md)
3. [Simple plots](matplotlib.md)
4. [Exercises](exercises.md)

## Packages

```{code-cell} python
import numpy as np
import matplotlib.pyplot as plt

print("numpy", np.__version__)
```

If imports fail locally:

```bash
pip install -r requirements.txt
```
