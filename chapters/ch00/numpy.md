---
kernelspec:
  name: python3
  display_name: Python 3
---

# 0.3 NumPy Arrays

A NumPy array is a **grid of numbers**: 1D for a sequence of values, 2D for a table. Later chapters call some of these vectors and matrices; here the goal is only to create arrays and read values out.

```{code-cell} python
import numpy as np

np.set_printoptions(precision=4, suppress=True, floatmode="fixed")
```

## Creating arrays

```{code-cell} python
v = np.array([1.0, 2.0, 3.0])          # 1D, shape (3,)
A = np.array([[1.0, 2.0],
              [3.0, 4.0]])            # 2D, shape (2, 2)
print("v:", v, "  shape", v.shape)
print("A:\n", A, "\nshape", A.shape)
```

Common constructors:

```{code-cell} python
print("zeros(3):")
print(np.zeros(3))
print("ones((2, 3)):")
print(np.ones((2, 3)))
print("eye(3)  (1s on the diagonal):")
print(np.eye(3))
print("arange(0, 1, 0.25):")
print(np.arange(0.0, 1.0, 0.25))
print("linspace(0, 1, 5):")
print(np.linspace(0.0, 1.0, 5))
```

## Indexing and slicing

For a 2D array, the first index is the row and the second is the column.

```{code-cell} python
A = np.array([[10, 11, 12],
              [20, 21, 22],
              [30, 31, 32]])
print(A[0, 1])      # row 0, col 1 → 11
print(A[:, 0])      # first column
print(A[1, :])      # second row
print(A[:2, 1:])    # top-right block
```

```{caution}
A length-$n$ 1D array has shape `(n,)`, not `(n, 1)`. Use `reshape` when an explicit column or row layout is needed.
```

```{code-cell} python
v = np.array([1.0, 2.0, 3.0])
col = v.reshape(3, 1)
row = v.reshape(1, 3)
print("v shape:", v.shape)
print("col shape:", col.shape)
print("row shape:", row.shape)
```

## Elementwise operations

These act **entry by entry** (or with a scalar). That is different from matrix multiplication, which appears later.

```{code-cell} python
u = np.array([1.0, 2.0, 3.0])
w = np.array([10.0, 20.0, 30.0])
print("u + w =", u + w)
print("2 * u =", 2 * u)
print("u * w =", u * w)   # entry by entry
print("u + 1 =", u + 1)
```

```{tip}
In NumPy, `*` is elementwise. The linear-algebra product uses a different operator and will be introduced with matrices.
```

Next: [0.4 Plots](matplotlib.md).
