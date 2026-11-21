---
kernelspec:
  name: python3
  display_name: Python 3
---

# 4.1 Elementary Matrices

An **elementary matrix** is the identity after one row operation. Multiplying on the left by that matrix performs the same operation on any matrix.

```{code-cell} python
import numpy as np

I = np.eye(3)
E = I.copy()
E[1, 0] = -2  # add -2 * row0 to row1
print("E =\n", E)

A = np.array([[1.0, 2.0, 0.0],
              [2.0, 3.0, 1.0],
              [0.0, 1.0, 4.0]])
print("E @ A =\n", E @ A)
```

Swaps and scalings work the same way:

```{code-cell} python
P = np.eye(3)
P[[0, 1]] = P[[1, 0]]  # swap rows 0 and 1
print("P @ A =\n", P @ A)
```

Elimination of a matrix $A$ is a product of such elementary matrices applied to $A$.

Next: [4.2 LU and PLU](lu.md).
