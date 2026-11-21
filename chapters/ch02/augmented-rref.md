---
kernelspec:
  name: python3
  display_name: Python 3
---

# 2.1 Augmented Matrices and RREF

## Allowed row operations

These operations do not change the solution set of a linear system:

1. Swap two rows  
2. Multiply a row by a nonzero scalar  
3. Add a multiple of one row to another row  

## Reduced row echelon form (RREF)

A matrix is in **RREF** when:

- leading entries (pivots) are $1$,
- each pivot is the only nonzero entry in its column,
- pivot columns move to the right as you go down,
- zero rows (if any) sit at the bottom.

```{code-cell} python
import numpy as np
import sympy as sp

A = np.array([[2.0, 1.0, 5.0],
              [3.0, -2.0, 4.0]])
print("augmented matrix:")
print(A)

rref_mat, pivots = sp.Matrix(A).rref()
print("RREF:")
print(np.array(rref_mat, dtype=float))
print("pivot columns:", pivots)
```

From this RREF one reads $x = 2$, $y = 1$ immediately.

Next: [2.2 Gauss–Jordan Elimination](gauss-jordan.md).
