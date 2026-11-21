---
kernelspec:
  name: python3
  display_name: Python 3
---

# 8.2 Null Space and Rank–Nullity

The **null space** (kernel) of $A$ is

$$
\mathrm{Nul}(A) = \{ \mathbf{x} : A\mathbf{x} = \mathbf{0} \}.
$$

It is a subspace of $\mathbb{R}^n$. Free variables in RREF parametrize a basis for $\mathrm{Nul}(A)$.

## Rank–nullity

$$
\mathrm{rank}(A) + \dim\mathrm{Nul}(A) = n
$$

(number of columns). Pivots plus free variables account for every column.

```{code-cell} python
import numpy as np
import sympy as sp

A = sp.Matrix([[1, 2, 3],
               [2, 4, 6],
               [0, 1, 1]])
print("nullspace basis vectors:")
for v in A.nullspace():
    print(np.array(v, dtype=float).reshape(-1))

rank = A.rank()
nullity = len(A.nullspace())
n = A.shape[1]
print(f"rank={rank}, nullity={nullity}, rank+nullity={rank+nullity} (n={n})")
```

```{code-cell} python
# Same idea with NumPy SVD nullspace (numerical)
A_np = np.array(A, dtype=float)
u, s, vh = np.linalg.svd(A_np)
tol = 1e-10
null_mask = s < tol
# For a full SVD of a non-square matrix, use complete_svd / righthand vectors with small singular values
u, s, vh = np.linalg.svd(A_np, full_matrices=True)
null_dim = A_np.shape[1] - np.linalg.matrix_rank(A_np)
print("null dim from rank-nullity:", null_dim)
print("last right singular vectors span Nul(A) approx:\n", vh[-null_dim:].T if null_dim else "(trivial nullspace)")
```

```{admonition} Why null space matters
:class: tip
Solutions of $A\mathbf{x}=\mathbf{b}$, when they exist, are one particular solution plus anything in $\mathrm{Nul}(A)$. That is the algebraic form of “infinitely many solutions.”
```

Next: [8.3 Coordinates and Change of Basis](coordinates.md).
