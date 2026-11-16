---
kernelspec:
  name: python3
  display_name: Python 3
---

# Simple plots

We will often draw an arrow from the origin to a pair of numbers $(x, y)$. You do not need the full theory of vectors yet — treat this as plotting two coordinates.

```{code-cell} python
%matplotlib inline
import numpy as np
import matplotlib.pyplot as plt
```

## One arrow

```{code-cell} python
origin = np.array([0.0, 0.0])
v = np.array([2.0, 1.0])

fig, ax = plt.subplots(figsize=(4, 4))
ax.quiver(*origin, *v, angles="xy", scale_units="xy", scale=1, color="C0")
ax.set_xlim(-1, 3)
ax.set_ylim(-1, 3)
ax.set_aspect("equal")
ax.grid(True, alpha=0.3)
ax.set_xlabel("$x$")
ax.set_ylabel("$y$")
ax.set_title("Arrow to $(2, 1)$")
plt.show()
```

## Adding coordinate pairs

Adding arrays adds each coordinate. The plot is a quick visual check.

```{code-cell} python
u = np.array([2.0, 0.5])
w = np.array([0.5, 1.5])
s = u + w

fig, ax = plt.subplots(figsize=(4, 4))
ax.quiver(*origin, *u, angles="xy", scale_units="xy", scale=1, color="C0", label="$u$")
ax.quiver(*origin, *w, angles="xy", scale_units="xy", scale=1, color="C1", label="$w$")
ax.quiver(*origin, *s, angles="xy", scale_units="xy", scale=1, color="C2", label="$u+w$")
ax.set_xlim(-1, 4)
ax.set_ylim(-1, 4)
ax.set_aspect("equal")
ax.grid(True, alpha=0.3)
ax.legend()
ax.set_title("Adding two pairs of coordinates")
plt.show()
```

## Mini-check

Plot the arrow to $(3, 1)$ and the arrow to $2\cdot(3, 1) = (6, 2)$. Check that scaling by a positive number lengthens the arrow without turning it.

Next: [Exercises](exercises.md).
