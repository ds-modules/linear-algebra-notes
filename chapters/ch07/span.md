---
kernelspec:
  name: python3
  display_name: Python 3
---

# 7.1 Span

The **span** of $\mathbf{v}_1,\ldots,\mathbf{v}_k$ is

$$
\mathrm{span}\{\mathbf{v}_1,\ldots,\mathbf{v}_k\}
= \{ c_1\mathbf{v}_1 + \cdots + c_k\mathbf{v}_k : c_i \in \mathbb{R} \}.
$$

Every span is a subspace. Asking whether $\mathbf{b}$ lies in the span is the same as asking whether $A\mathbf{c} = \mathbf{b}$ is consistent, where the columns of $A$ are the $\mathbf{v}_i$.

```{code-cell} python
import numpy as np
import sympy as sp

v1 = np.array([1.0, 2.0, 0.0])
v2 = np.array([0.0, 1.0, 1.0])
A = np.column_stack([v1, v2])

b_in = np.array([1.0, 3.0, 1.0])   # 1*v1 + 1*v2
b_out = np.array([1.0, 0.0, 0.0])

def in_span(A, b):
    aug = sp.Matrix(np.column_stack([A, b]))
    rref, _ = aug.rref()
    # inconsistent if a row [0 ... 0 | c] with c ≠ 0
    R = np.array(rref, dtype=float)
    for row in R:
        if np.allclose(row[:-1], 0) and not np.isclose(row[-1], 0):
            return False
    return True

print("b_in in span?", in_span(A, b_in))
print("b_out in span?", in_span(A, b_out))
```

```{code-cell} python
%matplotlib inline
import matplotlib.pyplot as plt

# In R^2, span of one nonzero vector is a line
v = np.array([2.0, 1.0])
fig, ax = plt.subplots(figsize=(4, 4))
ax.quiver(0, 0, *v, angles="xy", scale_units="xy", scale=1, color="C0")
t = np.linspace(-2, 2, 50)
ax.plot(t * v[0], t * v[1], "--", color="C0", alpha=0.5)
ax.set_xlim(-5, 5)
ax.set_ylim(-3, 3)
ax.set_aspect("equal")
ax.grid(True, alpha=0.3)
ax.set_title(r"$\mathrm{span}\{v\}$ as a line")
plt.show()
```

Next: [7.2 Linear Independence](independence.md).
