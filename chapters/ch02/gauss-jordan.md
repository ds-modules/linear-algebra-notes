---
kernelspec:
  name: python3
  display_name: Python 3
---

# 2.2 Gauss–Jordan Elimination

**Gauss–Jordan elimination** is the systematic use of row operations to reach RREF.

## Demo: three equations

```{code-cell} python
import numpy as np
import sympy as sp

aug = sp.Matrix([
    [1, 2, -1, 3],
    [2, 1,  1, 4],
    [1, 1,  1, 3],
])
print("Start:")
print(np.array(aug, dtype=float))

rref_mat, pivots = aug.rref()
print("RREF:")
print(np.array(rref_mat, dtype=float))
print("pivot columns:", pivots)
```

Each pivot column corresponds to a **basic** variable; any non-pivot column corresponds to a **free** variable (see the next page).

```{code-cell} python
# Same system via NumPy when square and uniquely solvable
A = np.array([[1.0, 2.0, -1.0],
              [2.0, 1.0,  1.0],
              [1.0, 1.0,  1.0]])
b = np.array([3.0, 4.0, 3.0])
print("np.linalg.solve →", np.linalg.solve(A, b))
```

Next: [2.3 Consistency and Parametric Solutions](consistency.md).
