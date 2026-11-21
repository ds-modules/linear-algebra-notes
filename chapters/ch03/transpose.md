---
kernelspec:
  name: python3
  display_name: Python 3
---

# 3.2 Transpose

The **transpose** $A^\top$ flips rows and columns: $(A^\top)_{ji} = A_{ij}$.

```{code-cell} python
import numpy as np

A = np.array([[1.0, 2.0, 3.0],
              [4.0, 5.0, 6.0]])
print("A shape", A.shape)
print(A)
print("A.T shape", A.T.shape)
print(A.T)
```

Useful identities (for compatible sizes):

- $(A + B)^\top = A^\top + B^\top$
- $(cA)^\top = c A^\top$
- $(AB)^\top = B^\top A^\top$

```{code-cell} python
B = np.array([[0.0, 1.0],
              [1.0, 0.0],
              [1.0, 1.0]])
print((A @ B).T)
print(B.T @ A.T)
print(np.allclose((A @ B).T, B.T @ A.T))
```

Next: [3.3 Inverse](inverse.md).
