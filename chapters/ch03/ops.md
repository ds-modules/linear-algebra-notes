---
kernelspec:
  name: python3
  display_name: Python 3
---

# 3.1 Addition, Scaling, and Multiplication

```{code-cell} python
import numpy as np
np.set_printoptions(precision=4, suppress=True, floatmode="fixed")
```

## Addition and scaling

Arrays of the same shape add entrywise; scaling multiplies every entry.

```{code-cell} python
A = np.array([[1.0, 2.0], [3.0, 4.0]])
B = np.array([[5.0, 0.0], [1.0, 1.0]])
print("A + B =\n", A + B)
print("3A =\n", 3 * A)
```

## Matrix multiplication

The product $AB$ is defined when the number of columns of $A$ equals the number of rows of $B$. Entry $(i,j)$ of $AB$ is the dot product of row $i$ of $A$ with column $j$ of $B$.

```{code-cell} python
A = np.array([[1.0, 2.0],
              [0.0, 1.0]])
C = np.array([[1.0, 0.0],
              [3.0, 1.0]])
print("A @ C =\n", A @ C)
print("C @ A =\n", C @ A)  # generally different
```

```{caution}
`A * C` is still **elementwise**. Linear-algebra multiplication is `A @ C` (or `np.matmul`).
```

```{code-cell} python
print("elementwise A * C =\n", A * C)
```

Matrix–vector products recover the “linear combination of columns” view of $A\mathbf{x}$:

```{code-cell} python
x = np.array([2.0, -1.0])
print("A @ x =", A @ x)
print("2*(col0) + (-1)*(col1) =", 2*A[:, 0] + (-1)*A[:, 1])
```

Next: [3.2 Transpose](transpose.md).
