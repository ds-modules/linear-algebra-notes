---
kernelspec:
  name: python3
  display_name: Python 3
---

# 3.3 Inverse

A square matrix $A$ is **invertible** if there exists $A^{-1}$ with $A A^{-1} = A^{-1} A = I$.

## Solving $A\mathbf{x}=\mathbf{b}$ with an inverse

If $A$ is invertible, then $\mathbf{x} = A^{-1}\mathbf{b}$. In practice, prefer a dedicated solver over forming $A^{-1}$ explicitly.

```{code-cell} python
import numpy as np

A = np.array([[2.0, 1.0],
              [1.0, 3.0]])
b = np.array([1.0, 0.0])

x_solve = np.linalg.solve(A, b)
x_inv = np.linalg.inv(A) @ b
print("solve:", x_solve)
print("via inv:", x_inv)
print("A @ A_inv =\n", A @ np.linalg.inv(A))
```

## When is there no inverse?

If rows (or columns) are linearly dependent, $A$ is singular: elimination produces a zero row and `inv` / `solve` fail.

```{code-cell} python
S = np.array([[1.0, 2.0],
              [2.0, 4.0]])
try:
    np.linalg.inv(S)
except np.linalg.LinAlgError as e:
    print("LinAlgError:", e)
```

Next: [4 Elementary Matrices and LU](../ch04/index.md).
