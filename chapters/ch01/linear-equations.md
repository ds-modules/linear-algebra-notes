---
kernelspec:
  name: python3
  display_name: Python 3
---

# 1.1 Linear Equations and Systems

A **linear equation** in unknowns $x_1,\ldots,x_n$ has the form

$$
a_1 x_1 + a_2 x_2 + \cdots + a_n x_n = b,
$$

where the coefficients $a_i$ and the constant $b$ are known numbers. There are no products of unknowns, no powers other than $1$, and no nonlinear functions of the unknowns.

A **system** of linear equations is a collection of one or more such equations in the same unknowns. A **solution** is a tuple $(x_1,\ldots,x_n)$ that makes every equation true at once.

## Geometry in two unknowns

With two unknowns, each equation describes a line in the plane. Solving the system means finding intersection points of those lines.

```{code-cell} python
%matplotlib inline
import numpy as np
import matplotlib.pyplot as plt

# x + y = 3  and  x - y = 1  → intersection (2, 1)
x = np.linspace(-1, 4, 200)
y1 = 3 - x
y2 = x - 1

fig, ax = plt.subplots(figsize=(4, 4))
ax.plot(x, y1, label="$x+y=3$")
ax.plot(x, y2, label="$x-y=1$")
ax.plot(2, 1, "o", color="C3")
ax.set_aspect("equal")
ax.grid(True, alpha=0.3)
ax.legend()
ax.set_title("Two lines, one intersection")
plt.show()
```

## How many solutions?

A linear system can have:

- **exactly one** solution (lines meet at a point),
- **infinitely many** solutions (the same line twice), or
- **no** solution (parallel distinct lines).

```{code-cell} python
# Parallel lines: x + y = 1 and x + y = 3 — no intersection
y_a = 1 - x
y_b = 3 - x

fig, ax = plt.subplots(figsize=(4, 4))
ax.plot(x, y_a, label="$x+y=1$")
ax.plot(x, y_b, label="$x+y=3$")
ax.set_aspect("equal")
ax.grid(True, alpha=0.3)
ax.legend()
ax.set_title("No solution")
plt.show()
```

Next: [1.2 Substitution and Elimination](substitution-elimination.md).
