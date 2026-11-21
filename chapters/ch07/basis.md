---
kernelspec:
  name: python3
  display_name: Python 3
---

# 7.3 Basis and Dimension

A **basis** of a subspace $W$ is a list of vectors that

1. **spans** $W$, and  
2. is **linearly independent**.

Every vector in $W$ then has unique coordinates relative to that basis. The number of vectors in any basis of $W$ is the same; that number is $\dim W$.

## Extracting a basis from spanning vectors

Put the vectors as columns of $A$, compute RREF, and keep the original columns that correspond to pivot columns.

```{code-cell} python
import numpy as np
import sympy as sp

# Three vectors in R^3 that span only a 2D plane
cols = [
    np.array([1.0, 0.0, 1.0]),
    np.array([2.0, 1.0, 3.0]),
    np.array([3.0, 1.0, 4.0]),  # = col0 + col1
]
A = np.column_stack(cols)
rref, pivots = sp.Matrix(A).rref()
print("pivots:", pivots)
basis = A[:, list(pivots)]
print("basis matrix:\n", basis)
print("rank = dim(span) =", len(pivots))
```

## Standard basis

The standard basis of $\mathbb{R}^n$ is $\mathbf{e}_1,\ldots,\mathbf{e}_n$ (columns of $I_n$). Its dimension is $n$.

```{code-cell} python
print(np.eye(3))
```

```{admonition} Feature-space intuition
:class: tip
If each column of a data matrix is a feature, the dimension of the column space is the number of independent directions among those features — before any fancy dimensionality reduction.
```

Next: [8 Rank and Fundamental Subspaces](../ch08/index.md).
