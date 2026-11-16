# Chapter 0 exercises

No linear-algebra theory required — only Python, NumPy arrays, and a simple plot.

## Exercise 1 — Python warm-up

Write a function `sum_list(values)` that returns the sum of a list of numbers using a `for` loop (no NumPy, no built-in `sum`).

````{admonition} Solution
:class: dropdown

```python
def sum_list(values):
    total = 0.0
    for x in values:
        total += x
    return total

assert sum_list([1, 2, 3]) == 6
```
````

## Exercise 2 — Shapes and slicing

Create a $3\times 3$ NumPy array filled with `1` through `9`. Extract (a) the middle row, (b) the last column, (c) the upper-left $2\times 2$ block.

````{admonition} Solution
:class: dropdown

```python
import numpy as np
A = np.arange(1, 10).reshape(3, 3)
print(A[1, :])      # [4 5 6]
print(A[:, -1])     # [3 6 9]
print(A[:2, :2])    # [[1 2] [4 5]]
```
````

## Exercise 3 — Elementwise arithmetic

Let `u = np.array([1.0, 2.0, 3.0])` and `w = np.array([10.0, 20.0, 30.0])`. Compute and print `u + w`, `3 * u`, and `u * w`. In one sentence, say how `u * w` differs from what you might expect from “multiplying grids of numbers” in a linear algebra class (you will see that product later).

````{admonition} Solution
:class: dropdown

```python
import numpy as np
u = np.array([1.0, 2.0, 3.0])
w = np.array([10.0, 20.0, 30.0])
print(u + w)   # [11. 22. 33.]
print(3 * u)   # [3. 6. 9.]
print(u * w)   # [10. 40. 90.]  — entry by entry, not matrix multiplication
```

`u * w` multiplies matching entries. Linear-algebra matrix multiplication combines whole rows and columns and comes in a later chapter.
````

## Exercise 4 — Reshape

Start from `v = np.array([1.0, 2.0, 3.0, 4.0])`. Make a $2\times 2$ array with `reshape` and print its shape.

````{admonition} Solution
:class: dropdown

```python
import numpy as np
v = np.array([1.0, 2.0, 3.0, 4.0])
M = v.reshape(2, 2)
print(M)
print(M.shape)  # (2, 2)
```
````

## Exercise 5 — Plot

Plot an arrow from the origin to $(2, 1)$ and another to $(4, 2)$ (which is twice the first pair). Use equal aspect ratio.

````{admonition} Solution
:class: dropdown

```python
import numpy as np
import matplotlib.pyplot as plt

a = np.array([2.0, 1.0])
b = 2 * a

fig, ax = plt.subplots(figsize=(4, 4))
ax.quiver(0, 0, *a, angles="xy", scale_units="xy", scale=1, color="C0", label="$(2,1)$")
ax.quiver(0, 0, *b, angles="xy", scale_units="xy", scale=1, color="C1", label="$(4,2)$")
ax.set_xlim(-1, 5)
ax.set_ylim(-1, 3)
ax.set_aspect("equal")
ax.grid(True, alpha=0.3)
ax.legend()
plt.show()
```
````

## Done with Chapter 0?

Next up is **Chapter 1** (systems of linear equations). Tools like `@`, `np.linalg.solve`, and `inv` will appear when those topics are introduced — not before.
