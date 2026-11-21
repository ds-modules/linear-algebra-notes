---
kernelspec:
  name: python3
  display_name: Python 3
---

# 8.1 Rank and Column / Row Space

For an $m\times n$ matrix $A$:

- **Column space** $\mathrm{Col}(A) \subseteq \mathbb{R}^m$: span of the columns  
- **Row space** $\mathrm{Row}(A) \subseteq \mathbb{R}^n$: span of the rows (equivalently $\mathrm{Col}(A^\top)$)

The **rank** of $A$ is $\dim\mathrm{Col}(A)$. It equals $\dim\mathrm{Row}(A)$ and equals the number of pivots in RREF.

```{code-cell} python
import numpy as np
import sympy as sp

A = np.array([[1.0, 2.0, 3.0],
              [2.0, 4.0, 6.0],
              [0.0, 1.0, 1.0]])
rref, pivots = sp.Matrix(A).rref()
print("RREF:\n", np.array(rref, dtype=float))
print("pivots:", pivots)
print("rank =", len(pivots))
print("numpy matrix_rank =", np.linalg.matrix_rank(A))
```

A basis for $\mathrm{Col}(A)$ is the set of **original** columns of $A$ in the pivot positions (not the RREF columns).

```{code-cell} python
col_basis = A[:, list(pivots)]
print("Col(A) basis:\n", col_basis)
```

$A\mathbf{x}=\mathbf{b}$ is consistent $\iff$ $\mathbf{b}\in\mathrm{Col}(A)$.

Next: [8.2 Null Space and Rank–Nullity](nullspace.md).
