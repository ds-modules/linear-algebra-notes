---
kernelspec:
  name: python3
  display_name: Python 3
---

# 1.3 Matrix Form

A system can be packaged as a single matrix equation $A\mathbf{x} = \mathbf{b}$.

## From equations to arrays

The system

$$
\begin{cases}
2x + y = 5 \\
3x - 2y = 4
\end{cases}
$$

has coefficient matrix $A$, unknown vector $\mathbf{x}$, and right-hand side $\mathbf{b}$:

$$
A = \begin{bmatrix} 2 & 1 \\ 3 & -2 \end{bmatrix}, \quad
\mathbf{x} = \begin{bmatrix} x \\ y \end{bmatrix}, \quad
\mathbf{b} = \begin{bmatrix} 5 \\ 4 \end{bmatrix}.
$$

The product $A\mathbf{x}$ is defined so that $A\mathbf{x} = \mathbf{b}$ restates the original equations.

```{code-cell} python
import numpy as np

A = np.array([[2.0, 1.0], [3.0, -2.0]])
x = np.array([2.0, 1.0])
b = np.array([5.0, 4.0])

print("A @ x =", A @ x)
print("b     =", b)
print("match?", np.allclose(A @ x, b))
```

## The augmented matrix

Storing coefficients and the right-hand side side-by-side gives the **augmented matrix** $[A \mid \mathbf{b}]$:

```{code-cell} python
aug = np.column_stack([A, b])
print(aug)
```

Row operations on this array — without changing the solution set — are the subject of [2 Row Reduction](../ch02/index.md).

## Imaging / “why systems?” (optional motivation)

In applications, each equation can encode a measurement or constraint (for example, overlapping projections in a simplified tomography story). The unknown $\mathbf{x}$ is the object we want to recover; $A$ encodes how measurements mix those unknowns. The algebra is the same: solve $A\mathbf{x} = \mathbf{b}$ or decide that no exact solution exists.
