---
kernelspec:
  name: python3
  display_name: Python 3
---

# 0.5 Check Your Understanding

These are short reading checks, not cells to edit or work to submit. Think through each question, then expand its solution.

## Shapes and slicing

What are the middle row, last column, and upper-left $2\times 2$ block of the array with entries $1$ through $9$?

````{admonition} Solution
:class: dropdown

```python
import numpy as np
A = np.arange(1, 10).reshape(3, 3)
print(A)
print("middle row:", A[1, :])
print("last column:", A[:, -1])
print("upper-left 2×2:\n", A[:2, :2])
```
````

## Elementwise arithmetic

If `u = [1, 2, 3]` and `w = [10, 20, 30]` as NumPy arrays, what are `u + w`, `3 * u`, and `u * w`? How does `u * w` differ from matrix multiplication?

````{admonition} Solution
:class: dropdown

```python
import numpy as np
u = np.array([1.0, 2.0, 3.0])
w = np.array([10.0, 20.0, 30.0])
print(u + w)   # [11. 22. 33.]
print(3 * u)   # [3. 6. 9.]
print(u * w)   # [10. 40. 90.] — matching entries only
```

Matrix multiplication combines whole rows and columns; it is introduced with matrices later.
````

## Reshape

How can the length-4 array `[1, 2, 3, 4]` become a $2\times 2$ table?

````{admonition} Solution
:class: dropdown

```python
import numpy as np
v = np.array([1.0, 2.0, 3.0, 4.0])
M = v.reshape(2, 2)
print(M)
print(M.shape)
```
````

Next: [1 Systems of Linear Equations](../ch01/index.md).
