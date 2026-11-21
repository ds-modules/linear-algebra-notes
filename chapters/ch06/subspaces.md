---
kernelspec:
  name: python3
  display_name: Python 3
---

# 6.3 Subspaces

A **subspace** of a vector space $V$ is a nonempty subset $W \subseteq V$ that is itself a vector space under the same operations. Equivalently: $W$ contains $\mathbf{0}$, and is closed under addition and scalar multiplication.

## Span

The **span** of vectors $\mathbf{v}_1,\ldots,\mathbf{v}_k$ is the set of all linear combinations $c_1\mathbf{v}_1 + \cdots + c_k\mathbf{v}_k$. Every span is a subspace.

```{code-cell} python
%matplotlib inline
import numpy as np
import matplotlib.pyplot as plt

v1 = np.array([1.0, 0.2])
v2 = np.array([0.3, 1.0])

fig, ax = plt.subplots(figsize=(4, 4))
ax.quiver(0, 0, *v1, angles="xy", scale_units="xy", scale=1, color="C0", label="$v_1$")
ax.quiver(0, 0, *v2, angles="xy", scale_units="xy", scale=1, color="C1", label="$v_2$")
# a few combinations
for c1, c2 in [(1, 1), (2, -0.5), (-1, 1.5)]:
    p = c1 * v1 + c2 * v2
    ax.plot(p[0], p[1], "o", color="C2", markersize=4)
ax.set_xlim(-3, 3)
ax.set_ylim(-3, 3)
ax.set_aspect("equal")
ax.grid(True, alpha=0.3)
ax.legend()
ax.set_title("Points in $\\mathrm{span}\\{v_1,v_2\\}$")
plt.show()
```

## Column space (preview)

The set of all $A\mathbf{x}$ as $\mathbf{x}$ varies is the **column space** of $A$ — the span of the columns. Solving $A\mathbf{x}=\mathbf{b}$ asks whether $\mathbf{b}$ lies in that subspace.

```{code-cell} python
A = np.array([[1.0, 0.3],
              [0.2, 1.0]])
b = np.array([1.3, 1.2])
print("b in col(A)? solve residual", A @ np.linalg.solve(A, b) - b)
```

Next: [7 Span, Independence, and Basis](../ch07/index.md).
