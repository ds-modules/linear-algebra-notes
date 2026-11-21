---
kernelspec:
  name: python3
  display_name: Python 3
---

# 7.2 Linear Independence

Vectors $\mathbf{v}_1,\ldots,\mathbf{v}_k$ are **linearly independent** if

$$
c_1\mathbf{v}_1 + \cdots + c_k\mathbf{v}_k = \mathbf{0}
\quad\text{implies}\quad
c_1 = \cdots = c_k = 0.
$$

Otherwise they are **dependent**: at least one vector is a combination of the others.

## Test via RREF

Form $A$ with those vectors as columns. Independence $\iff$ $A\mathbf{c}=\mathbf{0}$ has only the trivial solution $\iff$ every column of $A$ is a pivot column.

```{code-cell} python
import numpy as np
import sympy as sp

def independent(cols):
    A = np.column_stack(cols)
    rref, pivots = sp.Matrix(A).rref()
    return len(pivots) == A.shape[1], pivots, np.array(rref, dtype=float)

cols_ok = [np.array([1.0, 0.0, 0.0]),
           np.array([0.0, 1.0, 0.0]),
           np.array([0.0, 0.0, 1.0])]
ok, piv, R = independent(cols_ok)
print("independent?", ok, "pivots", piv)

cols_dep = [np.array([1.0, 2.0]),
            np.array([2.0, 4.0])]
ok, piv, R = independent(cols_dep)
print("independent?", ok, "pivots", piv)
print("RREF:\n", R)
```

## Determinant shortcut (square case)

For $n$ vectors in $\mathbb{R}^n$, independence $\iff$ the matrix they form has nonzero determinant.

```{code-cell} python
M = np.array([[1.0, 2.0],
              [3.0, 4.0]])
print("det =", np.linalg.det(M), "→ independent" if abs(np.linalg.det(M)) > 1e-10 else "→ dependent")
```

Next: [7.3 Basis and Dimension](basis.md).
