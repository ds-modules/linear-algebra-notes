---
kernelspec:
  name: python3
  display_name: Python 3
---

# 6.2 Vector Spaces

A **vector space** is a set $V$ with addition and scalar multiplication satisfying the usual axioms (associativity, distributivity, zero vector, additive inverses, and so on). The prototype is $\mathbb{R}^n$.

## Checking a set in $\mathbb{R}^2$

Is $V = \{(x,y) : y = 2x\}$ a vector space under the usual operations?

```{code-cell} python
import numpy as np

def on_line(v, tol=1e-12):
    return abs(v[1] - 2 * v[0]) < tol

u = np.array([1.0, 2.0])
w = np.array([-3.0, -6.0])
print("u in V?", on_line(u))
print("u+w in V?", on_line(u + w))
print("3u in V?", on_line(3 * u))
print("zero in V?", on_line(np.zeros(2)))
```

Closure under addition and scaling holds here; $V$ is a line through the origin — a classic subspace of $\mathbb{R}^2$.

## A set that fails

The line $y = 2x + 1$ does **not** contain the zero vector, so it is not a subspace.

```{code-cell} python
p = np.array([0.0, 1.0])
print("zero on affine line?", abs(0 - (2*0 + 1)) < 1e-12)
print("p looks like y=2x+1?", abs(p[1] - (2*p[0] + 1)) < 1e-12)
```

Next: [6.3 Subspaces](subspaces.md).
