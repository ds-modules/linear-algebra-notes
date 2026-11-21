---
kernelspec:
  name: python3
  display_name: Python 3
---

# 4.2 LU and PLU

When elimination on $A$ needs no row swaps, one obtains $A = LU$ with $L$ unit lower-triangular and $U$ upper-triangular. With pivots, a permutation appears: $A = PLU$.

## Why factor once?

To solve $A\mathbf{x} = \mathbf{b}$ for many right-hand sides, factor $A$ once, then forward- and back-substitute for each $\mathbf{b}$.

```{code-cell} python
import numpy as np
from scipy.linalg import lu

A = np.array([[2.0, 1.0, 1.0],
              [4.0, -6.0, 0.0],
              [-2.0, 7.0, 2.0]])
P, L, U = lu(A)
print("P =\n", P)
print("L =\n", L)
print("U =\n", U)
print("PLU reconstructs A?", np.allclose(P @ L @ U, A))
```

Solving $A\mathbf{x}=\mathbf{b}$ with the factorization:

```{code-cell} python
b = np.array([5.0, -2.0, 9.0])
# P L U x = b  →  L (U x) = P.T b
y = np.linalg.solve(L, P.T @ b)
x = np.linalg.solve(U, y)
print("x =", x)
print("check:", A @ x)
```

Next: [5 Determinants](../ch05/index.md).
