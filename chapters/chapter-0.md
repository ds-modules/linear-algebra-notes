# Chapter 0: Computing Foundations

Linear algebra describes objects such as vectors and matrices and the operations we perform on them. Python lets us carry out those operations, test conjectures, and work with examples too large to compute by hand.

This chapter is a pre-course bootcamp. It does not assume prior programming experience, and it introduces only the Python needed for the rest of this book.

## Learning objectives

By the end of this chapter, you will be able to:

1. work in a Jupyter notebook and restart a notebook safely;
2. use Python variables, expressions, functions, conditionals, and loops;
3. create NumPy arrays and inspect their shape and data type;
4. select and reshape array data with indexing, slicing, and masks;
5. explain and use vectorized operations and broadcasting;
6. distinguish elementwise multiplication from matrix multiplication;
7. use `numpy.linalg.solve` to solve a square linear system;
8. explain why explicitly computing an inverse is usually not the best way to solve a system; and
9. create labeled plots of scalar and vector data with Matplotlib.

## Chapter map

| Section | Main ideas | Suggested time |
|---|---|---:|
| [0.1 Getting started](chapter-0/getting-started.md) | Jupyter workflow, kernels, Markdown, imports | 30–45 min |
| [0.2 Python basics](chapter-0/python-basics.md) | Values, functions, control flow | 60–75 min |
| [0.3 NumPy arrays](chapter-0/numpy-arrays.md) | Shapes, indexing, slicing, broadcasting | 75–90 min |
| [0.4 Linear algebra tools](chapter-0/linear-algebra-tools.md) | Matrix multiplication, `solve`, inverse | 60–75 min |
| [0.5 Visualization](chapter-0/visualization.md) | Line, scatter, and vector plots | 45–60 min |
| [Lab 0](chapter-0/lab-0.md) | Integrated readiness practice | 90–120 min |

## Conventions used in this book

- `x`, `y`, and `v` usually name vectors.
- `A`, `B`, and `M` usually name matrices.
- Python uses zero-based indexing: the first item has index `0`.
- A code comment begins with `#`.
- The symbol `=` assigns a value in Python; it does not assert a mathematical equation.
- The operator `@` performs matrix multiplication for NumPy arrays.

:::{admonition} Readiness standard
:class: important
You are ready for Chapter 1 when you can complete Lab 0 without copying the worked examples. It is normal to consult documentation for function names and syntax.
:::
