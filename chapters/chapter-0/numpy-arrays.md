---
kernelspec:
  name: python3
  display_name: Python 3
  language: python
---

# 0.3 NumPy Arrays

NumPy arrays store numerical data in a rectangular structure. A one-dimensional array can represent a vector, and a two-dimensional array can represent a matrix.

```{code-cell} python
import numpy as np
```

## Creating arrays

Create arrays from Python lists:

```{code-cell} python
v = np.array([2.0, -1.0, 3.0])
A = np.array([
    [1.0, 2.0, 0.0],
    [3.0, -1.0, 4.0],
])

v, A
```

Every array has useful attributes:

```{code-cell} python
print("v shape:", v.shape)
print("A shape:", A.shape)
print("A dimensions:", A.ndim)
print("A data type:", A.dtype)
print("A entries:", A.size)
```

The matrix `A` has shape `(2, 3)`: 2 rows and 3 columns. Shape determines whether many operations are valid.

NumPy also provides constructors for common arrays:

```{code-cell} python
zeros = np.zeros((2, 3))
identity = np.eye(3)
integers = np.arange(0, 10, 2)
grid = np.linspace(0, 1, 5)

zeros, identity, integers, grid
```

## Indexing and slicing

For a matrix, write the row index first and the column index second.

```{code-cell} python
A[0, 1]
```

Use `:` to select a range or an entire axis:

```{code-cell} python
first_row = A[0, :]
second_column = A[:, 1]
block = A[:, 0:2]

first_row, second_column, block
```

Notice the shapes:

```{code-cell} python
first_row.shape, second_column.shape, block.shape
```

Both a selected row and a selected column are one-dimensional here. To preserve a two-dimensional column shape, select a one-column slice:

```{code-cell} python
column_matrix = A[:, 1:2]
column_matrix, column_matrix.shape
```

## Copies and views

Some slices share data with the original array. Changing a slice may therefore change the original.

```{code-cell} python
original = np.array([10, 20, 30, 40])
view = original[1:3]
view[0] = -20
original
```

Use `.copy()` when you need an independent array:

```{code-cell} python
independent = original[1:3].copy()
independent[0] = 999
original, independent
```

## Elementwise operations

Arithmetic operators act entry by entry when shapes are compatible.

```{code-cell} python
x = np.array([1.0, 2.0, 3.0])
y = np.array([4.0, 5.0, 6.0])

x + y, 3 * x, x * y, x ** 2
```

Here `x * y` is elementwise multiplication. It is not a dot product and not matrix multiplication.

Many NumPy functions are vectorized:

```{code-cell} python
angles = np.array([0, np.pi / 2, np.pi])
np.sin(angles)
```

Vectorized code expresses an array calculation directly:

```{code-cell} python
values = np.arange(1, 6)
squares = values ** 2
squares
```

## Aggregation and axis

An aggregation reduces several values to a summary.

```{code-cell} python
M = np.array([
    [1, 2, 3],
    [4, 5, 6],
])

M.sum(), M.mean(), M.max()
```

The `axis` argument specifies the axis that is collapsed:

```{code-cell} python
column_sums = M.sum(axis=0)
row_sums = M.sum(axis=1)
column_sums, row_sums
```

- `axis=0` collapses rows and leaves one result per column.
- `axis=1` collapses columns and leaves one result per row.

Always check the output shape when learning an axis-based operation.

## Boolean masks

A comparison with an array produces a Boolean array:

```{code-cell} python
data = np.array([3.2, -1.0, 0.0, 4.5, -2.3])
positive_mask = data > 0
positive_mask, data[positive_mask]
```

Masks support data filtering without a manual loop.

## Broadcasting

Broadcasting lets NumPy combine compatible shapes by treating a smaller array as if it were repeated.

```{code-cell} python
observations = np.array([
    [10.0, 100.0, 1.0],
    [12.0, 120.0, 2.0],
    [14.0, 140.0, 3.0],
])
column_means = observations.mean(axis=0)
centered = observations - column_means

column_means, centered
```

`observations` has shape `(3, 3)` and `column_means` has shape `(3,)`. NumPy subtracts the three means from each row.

Broadcasting compares dimensions from right to left. Two dimensions are compatible when they are equal or one of them is `1`.

:::{admonition} Shape before arithmetic
:class: warning
Broadcasting can produce a valid result that is not the result you intended. Write down the expected shape, inspect `.shape`, and test with a small example.
:::

## Reshaping and transposing

Reshape an array without changing its entries:

```{code-cell} python
numbers = np.arange(1, 7)
B = numbers.reshape(2, 3)
B
```

Transpose a matrix by exchanging rows and columns:

```{code-cell} python
B.T
```

For a one-dimensional array, `.T` does not change the shape:

```{code-cell} python
v = np.array([1, 2, 3])
v.shape, v.T.shape
```

Use `v.reshape(-1, 1)` when a genuine column-shaped array is required.

## Practice

### Exercise 1: standardize each column

For the array below, subtract each column's mean and divide by that column's standard deviation. The result should have column means near zero.

```{code-cell} python
X = np.array([
    [2.0, 20.0],
    [4.0, 30.0],
    [8.0, 40.0],
    [10.0, 50.0],
])
```

:::{dropdown} Solution
```{code-cell} python
means = X.mean(axis=0)
standard_deviations = X.std(axis=0)
Z = (X - means) / standard_deviations

Z, Z.mean(axis=0), Z.std(axis=0)
```
The standardized columns have means close to `0` and standard deviations close to `1`.
:::

### Exercise 2: select rows

Select every row of `X` whose first entry is at least 5.

:::{dropdown} Solution
```{code-cell} python
selected = X[X[:, 0] >= 5]
selected
```
:::

### Exercise 3: predict shapes

Predict each shape before running the code:

```python
C = np.zeros((4, 3))
C[1, :].shape
C[:, 1:2].shape
C.mean(axis=0).shape
C.mean(axis=1).shape
```

:::{dropdown} Solution
The shapes are `(3,)`, `(4, 1)`, `(3,)`, and `(4,)`, respectively.
:::
