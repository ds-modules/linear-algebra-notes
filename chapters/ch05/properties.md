---
kernelspec:
  name: python3
  display_name: Python 3
---

# 5.2 Properties

Useful rules (square matrices of equal size where needed):

- $\det(I) = 1$
- $\det(AB) = \det(A)\det(B)$
- $\det(A^\top) = \det(A)$
- $\det(cA) = c^n \det(A)$ for $n\times n$
- Swapping two rows multiplies the determinant by $-1$
- A zero row (or duplicate rows) forces determinant $0$

```{code-cell} python
import numpy as np

A = np.array([[2.0, 1.0],
              [0.0, 3.0]])
B = np.array([[1.0, 1.0],
              [0.0, 2.0]])
print("det(A) det(B) =", np.linalg.det(A) * np.linalg.det(B))
print("det(AB)       =", np.linalg.det(A @ B))
print("det(A.T)      =", np.linalg.det(A.T))
```

Geometrically in $\mathbb{R}^2$ or $\mathbb{R}^3$, $|\det(A)|$ is the area or volume scaling factor of the linear map $\mathbf{x} \mapsto A\mathbf{x}$; the sign records orientation.

Next: [6 Vectors and Spaces](../ch06/index.md).
