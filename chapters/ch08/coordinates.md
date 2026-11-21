---
kernelspec:
  name: python3
  display_name: Python 3
---

# 8.3 Coordinates and Change of Basis

If $\mathcal{B} = \{\mathbf{b}_1,\ldots,\mathbf{b}_n\}$ is a basis of $\mathbb{R}^n$, every $\mathbf{x}$ has unique **coordinates** $[\mathbf{x}]_{\mathcal{B}} = (c_1,\ldots,c_n)$ with

$$
\mathbf{x} = c_1\mathbf{b}_1 + \cdots + c_n\mathbf{b}_n = P_{\mathcal{B}}\,[\mathbf{x}]_{\mathcal{B}},
$$

where $P_{\mathcal{B}}$ has columns $\mathbf{b}_i$.

## From coordinates to the standard basis

```{code-cell} python
import numpy as np

# Basis B: columns of P
P = np.array([[1.0, 1.0],
              [0.0, 1.0]])
c = np.array([2.0, -1.0])  # [x]_B
x = P @ c
print("x in standard coordinates:", x)
```

## From standard coordinates to $\mathcal{B}$

$$
[\mathbf{x}]_{\mathcal{B}} = P_{\mathcal{B}}^{-1}\mathbf{x}.
$$

```{code-cell} python
x = np.array([3.0, 1.0])
c = np.linalg.solve(P, x)  # better than inv
print("[x]_B =", c)
print("reconstruct:", P @ c)
```

## Change of basis

If $\mathcal{B}$ and $\mathcal{C}$ are two bases,

$$
[\mathbf{x}]_{\mathcal{C}} = P_{\mathcal{C}}^{-1} P_{\mathcal{B}}\,[\mathbf{x}]_{\mathcal{B}}.
$$

The matrix $P_{\mathcal{C}}^{-1} P_{\mathcal{B}}$ converts $\mathcal{B}$-coordinates into $\mathcal{C}$-coordinates.

```{code-cell} python
P_B = np.array([[1.0, 1.0],
                [0.0, 1.0]])
P_C = np.array([[1.0, 0.0],
                [1.0, 1.0]])
c_B = np.array([2.0, -1.0])
x = P_B @ c_B
c_C = np.linalg.solve(P_C, x)
print("[x]_C =", c_C)

T = np.linalg.solve(P_C, P_B)  # C←B change of basis
print("T @ c_B =", T @ c_B)
```

```{admonition} Looking ahead
:class: note
PCA and “new coordinates for data” are change-of-basis stories: pick an orthonormal basis aligned with variance, then read data in those coordinates. The geometry for that begins in the next sections on dot products and orthogonality.
```
