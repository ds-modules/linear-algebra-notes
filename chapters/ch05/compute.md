---
kernelspec:
  name: python3
  display_name: Python 3
---

# 5.1 Computing Determinants

For $2\times 2$ matrices,

$$
\det\begin{bmatrix} a & b \\ c & d \end{bmatrix} = ad - bc.
$$

```{code-cell} python
import numpy as np

A = np.array([[3.0, 1.0],
              [2.0, 4.0]])
print(np.linalg.det(A), "vs hand", 3*4 - 1*2)
```

For larger matrices, determinants are computed via elimination (product of pivots, with sign changes from swaps) or related algorithms — use the library, understand the meaning.

```{code-cell} python
B = np.array([[1.0, 2.0, 0.0],
              [0.0, 1.0, 1.0],
              [2.0, 0.0, 1.0]])
print("det(B) =", np.linalg.det(B))
```

```{admonition} Invertibility test
:class: tip
$\det(A) = 0$ if and only if $A$ is singular (not invertible). Nonzero determinant $\iff$ unique solution to $A\mathbf{x}=\mathbf{b}$ for every $\mathbf{b}$.
```

```{code-cell} python
S = np.array([[1.0, 2.0],
              [2.0, 4.0]])
print("det(singular) =", np.linalg.det(S))
```

Next: [5.2 Properties](properties.md).
