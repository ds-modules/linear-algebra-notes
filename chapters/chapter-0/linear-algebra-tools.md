---
kernelspec:
  name: python3
  display_name: Python 3
  language: python
---

# 0.4 Linear Algebra Tools in NumPy

NumPy provides concise operations for vector and matrix calculations. This section introduces the tools; later chapters develop their mathematical meaning.

```{code-cell} python
import numpy as np
```

## Elementwise multiplication versus matrix multiplication

Consider two matrices with the same shape:

```{code-cell} python
A = np.array([
    [1.0, 2.0],
    [3.0, 4.0],
])
B = np.array([
    [2.0, 0.0],
    [1.0, 2.0],
])
```

The `*` operator multiplies corresponding entries:

```{code-cell} python
A * B
```

The `@` operator performs matrix multiplication:

```{code-cell} python
A @ B
```

These results differ because matrix multiplication forms row-by-column dot products. For $A @ B$ to be defined, the number of columns of $A$ must equal the number of rows of $B$.

```{code-cell} python
A.shape, B.shape, (A @ B).shape
```

## Matrix-vector products

A matrix-vector product combines the columns of a matrix using the entries of the vector:

```{code-cell} python
x = np.array([5.0, -1.0])
b = A @ x
b
```

Check the calculation manually:

$$
\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}
\begin{bmatrix}
5 \\
-1
\end{bmatrix}
=
\begin{bmatrix}
1(5)+2(-1) \\
3(5)+4(-1)
\end{bmatrix}
=
\begin{bmatrix}
3 \\
11
\end{bmatrix}.
$$

## Dot products and norms

For one-dimensional arrays, `@` computes the dot product:

```{code-cell} python
u = np.array([1.0, 2.0, -1.0])
v = np.array([3.0, 0.0, 4.0])

u @ v
```

The Euclidean norm measures vector length:

```{code-cell} python
np.linalg.norm(u)
```

These operations return in the geometry chapter with definitions and applications.

## Solving a linear system

The system

$$
\begin{aligned}
2x + y &= 7, \\
x - y &= 2
\end{aligned}
$$

can be written as $Ax=b$. Define the coefficient matrix and right-hand side:

```{code-cell} python
A = np.array([
    [2.0, 1.0],
    [1.0, -1.0],
])
b = np.array([7.0, 2.0])
```

Use `np.linalg.solve(A, b)` for a square system with a unique solution:

```{code-cell} python
x = np.linalg.solve(A, b)
x
```

Never stop at the returned array. Check the residual $Ax-b$:

```{code-cell} python
residual = A @ x - b
residual, np.linalg.norm(residual)
```

The residual may contain tiny values such as `1e-16` because computers approximate most real-number arithmetic.

## Comparing floating-point results

Avoid exact equality for computed floating-point arrays:

```{code-cell} python
0.1 + 0.2 == 0.3
```

Use a tolerance-based comparison:

```{code-cell} python
np.isclose(0.1 + 0.2, 0.3), np.allclose(A @ x, b)
```

## Inverses

For an invertible matrix, NumPy can compute $A^{-1}$:

```{code-cell} python
A_inverse = np.linalg.inv(A)
A_inverse
```

The product is approximately the identity matrix:

```{code-cell} python
A @ A_inverse
```

The formula $x=A^{-1}b$ is mathematically valid:

```{code-cell} python
A_inverse @ b
```

However, when the goal is to solve $Ax=b$, prefer:

```python
x = np.linalg.solve(A, b)
```

Computing an inverse performs unnecessary work and can introduce more numerical error. Use `inv` when the inverse itself is the object being studied, not as the default system-solving method.

## Singular and nearly singular systems

A singular matrix does not have an inverse. `solve` reports this rather than inventing a unique solution:

```{code-cell} python
singular = np.array([
    [1.0, 2.0],
    [2.0, 4.0],
])
```

Running `np.linalg.solve(singular, np.array([3.0, 6.0]))` raises `LinAlgError: Singular matrix`.

Some invertible matrices are still numerically difficult. The condition number is one warning sign:

```{code-cell} python
np.linalg.cond(A), np.linalg.cond(singular)
```

We will interpret singularity and conditioning after developing elimination, invertibility, and vector spaces.

## A reliable computational workflow

When using a linear algebra routine:

1. state the mathematical problem;
2. construct arrays with intentional shapes;
3. inspect `.shape`;
4. call the appropriate routine;
5. verify the result with a residual or mathematical property; and
6. interpret the result in the problem's context.

## Practice

### Exercise 1: matrix-vector product

Compute $Mv$ for

$$
M=\begin{bmatrix}1&-2&0\\3&1&4\end{bmatrix},
\qquad
v=\begin{bmatrix}2\\-1\\3\end{bmatrix}.
$$

Predict the output shape before running the calculation.

:::{dropdown} Solution
```{code-cell} python
M = np.array([
    [1.0, -2.0, 0.0],
    [3.0, 1.0, 4.0],
])
v = np.array([2.0, -1.0, 3.0])
product = M @ v

product, product.shape
```
The result is `[4., 17.]` with shape `(2,)`.
:::

### Exercise 2: solve and verify

Solve the system

$$
\begin{aligned}
3x-2y&=4,\\
5x+y&=11.
\end{aligned}
$$

Verify the answer with `np.allclose`.

:::{dropdown} Solution
```{code-cell} python
A = np.array([
    [3.0, -2.0],
    [5.0, 1.0],
])
b = np.array([4.0, 11.0])
x = np.linalg.solve(A, b)

x, np.allclose(A @ x, b)
```
The solution is $x=2$ and $y=1$.
:::

### Exercise 3: diagnose the operation

Explain why `A * x` is not a replacement for `A @ x` when `A` is a matrix and `x` is a vector.

:::{dropdown} Solution
`A * x` uses broadcasting to multiply each row's entries elementwise by `x`; its result has the same matrix shape as `A`. `A @ x` forms one dot product per row and returns a vector. The operations answer different questions.
:::
