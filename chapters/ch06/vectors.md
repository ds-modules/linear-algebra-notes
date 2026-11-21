---
kernelspec:
  name: python3
  display_name: Python 3
---

# 6.1 Vectors in $\mathbb{R}^n$

A vector in $\mathbb{R}^n$ is an ordered list of $n$ real numbers. In code it is a length-$n$ NumPy array (or an $n\times 1$ column).

```{code-cell} python
%matplotlib inline
import numpy as np
import matplotlib.pyplot as plt

u = np.array([2.0, 1.0])
w = np.array([-0.5, 1.5])

fig, ax = plt.subplots(figsize=(4, 4))
ax.quiver(0, 0, *u, angles="xy", scale_units="xy", scale=1, color="C0", label="$u$")
ax.quiver(0, 0, *w, angles="xy", scale_units="xy", scale=1, color="C1", label="$w$")
ax.quiver(0, 0, *(u+w), angles="xy", scale_units="xy", scale=1, color="C2", label="$u+w$")
ax.set_xlim(-2, 4)
ax.set_ylim(-1, 4)
ax.set_aspect("equal")
ax.grid(True, alpha=0.3)
ax.legend()
ax.set_title("Vector addition in $\\mathbb{R}^2$")
plt.show()
```

## Data as vectors

A spreadsheet row (prices, measurements, word counts) is naturally a vector. Adding and scaling then become the same algebra as geometric arrows.

```{code-cell} python
# Toy "features" for two days of a stock-like series
day1 = np.array([100.0, 0.5, 1.2e6])  # price, return, volume
day2 = np.array([101.0, 0.01, 0.9e6])
print("average day:", 0.5 * (day1 + day2))
```

Next: [6.2 Vector Spaces](vector-spaces.md).
