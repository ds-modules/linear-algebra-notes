---
kernelspec:
  name: python3
  display_name: Python 3
---

# 0 Getting Ready

Before the linear algebra begins, this short section reviews the algebra and coding ideas used in demonstrations throughout the book.

There is nothing to install or configure. Code examples are already executed, and interactive demonstrations run directly on the page.

## In this section

- [0.1 Mathematical Readiness](readiness.md) — arithmetic, equations, substitution, and coordinates
- [0.2 Python in the Textbook](jupyter-python.md) — variables, lists, loops, and functions
- [0.3 NumPy Arrays](numpy.md) — grids of numbers, indexing, and elementwise arithmetic
- [0.4 Plots](matplotlib.md) — drawing arrows from pairs of coordinates
- [0.5 Check Your Understanding](exercises.md)

Matrix multiplication, solving $Ax=b$, and inverses appear later, when those mathematical ideas are introduced.

```{code-cell} python
import numpy as np
import matplotlib.pyplot as plt

print("numpy", np.__version__)
```
