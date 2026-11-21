---
kernelspec:
  name: python3
  display_name: Python 3
---

# 2.3 Consistency and Parametric Solutions

After RREF, reading the solution is mechanical.

## Inconsistent systems

If a row looks like $[0\ \cdots\ 0 \mid c]$ with $c \neq 0$, the system has **no solution**.

```{code-cell} python
import numpy as np
import sympy as sp

aug = sp.Matrix([
    [1, 1, 1],
    [2, 2, 3],  # implies 0 = 1 after elimination
])
print(np.array(aug.rref()[0], dtype=float))
```

## Unique solution

If every variable is basic (a pivot in every column of $A$), there is exactly one solution.

## Infinitely many solutions

If there is a free variable, the solution set is described **parametrically**.

**Example.** Suppose RREF yields

$$
\begin{cases}
x + 2z = 3 \\
y - z = 1,
\end{cases}
$$

with free variable $z = t$. Then

$$
x = 3 - 2t, \quad y = 1 + t, \quad z = t, \quad t \in \mathbb{R}.
$$

```{code-cell} python
# Sample a few solutions on that line
for t in [0, 1, -2]:
    x, y, z = 3 - 2*t, 1 + t, t
    print(f"t={t:2d} → (x,y,z)=({x}, {y}, {z})")
```

```{admonition} Preview
:class: tip
Later, the same pivot / free-variable bookkeeping describes bases for column space and null space.
```

Next: [3 Matrix Operations](../ch03/index.md).
