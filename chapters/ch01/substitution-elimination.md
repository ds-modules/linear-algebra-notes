---
kernelspec:
  name: python3
  display_name: Python 3
---

# 1.2 Substitution and Elimination

Two classical hand methods solve small systems. The same ideas reappear as row operations in the next section.

## Substitution

Solve one equation for one unknown, then substitute into the others.

**Example.** Solve

$$
\begin{cases}
2x + y = 5 \\
3x - 2y = 4.
\end{cases}
$$

From the first equation, $y = 5 - 2x$. Substitute into the second:

$$
3x - 2(5 - 2x) = 4 \implies 3x - 10 + 4x = 4 \implies 7x = 14 \implies x = 2,
$$

so $y = 5 - 4 = 1$. The solution is $(2, 1)$.

```{code-cell} python
import numpy as np

# Verify with NumPy (preview of later tooling)
A = np.array([[2.0, 1.0], [3.0, -2.0]])
b = np.array([5.0, 4.0])
print(np.linalg.solve(A, b))
```

## Elimination

Add a multiple of one equation to another to cancel an unknown.

**Example.** Solve

$$
\begin{cases}
4x - 3y = 5 \\
2x + 5y = 9.
\end{cases}
$$

Replace the second equation by $(\text{eq }2) - \tfrac12(\text{eq }1)$. This gives $\tfrac{13}{2}y=\tfrac{13}{2}$, so $y=1$. Back-substitution gives $x=2$.

```{code-cell} python
A = np.array([[4.0, -3.0], [2.0, 5.0]])
b = np.array([5.0, 9.0])
print(np.linalg.solve(A, b))
```

```{admonition} Why show `solve` here?
:class: note
`np.linalg.solve` is a calculator for square systems with a unique solution. The rest of Sections 1–2 explain *what* that calculator is doing geometrically and algebraically.
```

Next: [1.3 Matrix Form](matrix-form.md).
