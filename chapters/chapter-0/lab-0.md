---
kernelspec:
  name: python3
  display_name: Python 3
  language: python
---

# Lab 0: Python and NumPy Bootcamp

This lab checks the computing skills needed in Chapter 1. Complete it in a fresh notebook. You may consult the chapter and official documentation, but write and explain your own code.

**Estimated time:** 90–120 minutes

## Learning objectives

In this lab, you will:

- organize a reproducible notebook;
- write a small Python function;
- inspect, select, and transform array data;
- use broadcasting and matrix multiplication intentionally;
- solve and verify a linear system; and
- create and interpret a labeled visualization.

## Submission standard

Your notebook must:

1. include your name, date, and a descriptive title in a Markdown cell;
2. import packages once near the beginning;
3. run from top to bottom after a kernel restart;
4. show requested output;
5. include a written response wherever interpretation is requested; and
6. avoid unexplained errors and unused code.

## Setup

```{code-cell} python
import numpy as np
import matplotlib.pyplot as plt
```

## Part A: Python function

### A1. Weighted score

Write a function named `weighted_score(homework, exams, project)` that returns a final score using these weights:

- homework: 25%;
- exams: 55%; and
- project: 20%.

Include a one-line docstring. Test the function with homework score 88, exam score 79, and project score 94.

```{code-cell} python
# Write weighted_score here.
```

**Self-check:** The result for the supplied values is `84.25`.

### A2. Letter category

Extend the task by writing `score_category(score)`, which returns:

- `"A"` for a score at least 90;
- `"B"` for a score at least 80 but below 90;
- `"C"` for a score at least 70 but below 80; and
- `"Not yet passing"` otherwise.

Test the function at the boundary values 70, 80, and 90.

```{code-cell} python
# Write score_category here.
```

## Part B: Arrays and data selection

The rows of `student_data` represent students. The columns contain hours studied, homework average, and exam average.

```{code-cell} python
student_data = np.array([
    [4.0, 78.0, 72.0],
    [7.5, 85.0, 88.0],
    [2.0, 69.0, 65.0],
    [6.0, 92.0, 90.0],
    [5.5, 81.0, 84.0],
    [8.0, 94.0, 96.0],
])
```

### B1. Inspect the array

Display:

1. the shape of `student_data`;
2. the number of dimensions;
3. the data type; and
4. the total number of entries.

Then explain in one sentence what each row and column represents.

```{code-cell} python
# Inspect student_data here.
```

### B2. Select columns

Create one-dimensional arrays named `hours`, `homework`, and `exams` by selecting the corresponding columns. Display each array and its shape.

```{code-cell} python
# Select the three columns here.
```

### B3. Filter rows

Use a Boolean mask to select students who studied at least 6 hours. Store all three columns for those students in `selected_students`.

```{code-cell} python
# Build the mask and select rows here.
```

**Self-check:** `selected_students` should have shape `(3, 3)`.

### B4. Center the score columns

Select the homework and exam columns together as a two-dimensional array named `scores`. Subtract each column's mean using broadcasting and store the result in `centered_scores`.

Verify numerically that each centered column has mean zero, allowing for floating-point rounding.

```{code-cell} python
# Center the score columns and verify the result here.
```

In a Markdown cell, explain which shapes participate in the broadcasting operation.

## Part C: Matrix calculations

The matrix below assigns weights to homework and exams for two different grading plans:

```{code-cell} python
weights = np.array([
    [0.40, 0.60],
    [0.25, 0.75],
])
```

Each row is one plan, and the columns correspond to homework and exams.

### C1. All plan scores

Use matrix multiplication to compute both plan scores for all students. Your result should have one row per student and one column per grading plan.

```{code-cell} python
# Compute all plan scores here.
```

State the shapes of the two input arrays and the output array. Explain why the inner dimensions are compatible.

### C2. Compare operations

Explain why `scores * weights` does not answer the same question as your matrix multiplication in C1. Mention both meaning and shape.

## Part D: Solve a system

A small shop sells notebooks and pens. Three notebooks and two pens cost $13. Two notebooks and five pens cost $16. Let $n$ be the price of one notebook and $p$ be the price of one pen.

### D1. Model

Write the two equations in a Markdown cell. Then define a coefficient matrix `A` and right-hand side `b` so the system is $Ax=b$.

```{code-cell} python
# Define A and b here.
```

### D2. Solve and verify

Solve the system with `np.linalg.solve`. Verify it with both:

1. `np.allclose(A @ x, b)`; and
2. the norm of the residual.

```{code-cell} python
# Solve and verify the system here.
```

Interpret both entries of the solution in a complete sentence with units.

## Part E: Visualization

Create a scatter plot of study hours on the horizontal axis and exam average on the vertical axis.

Your plot must include:

- a descriptive title;
- labels on both axes;
- visible points;
- a light grid; and
- a different color for students whose exam average is at least 90.

```{code-cell} python
# Create the scatter plot here.
```

Below the figure, write two or three sentences describing the relationship visible in this small dataset. Do not claim that study time causes the scores.

## Part F: Reflection

Answer each question in complete sentences:

1. What is one difference between a Python list and a NumPy array?
2. What is one difference between `*` and `@` for arrays?
3. Why do we check a linear-system solution with a residual?
4. Which Chapter 0 skill needs more practice before Chapter 1?

## Readiness checklist

Before submitting, confirm:

- [ ] Restarting the kernel and running all cells succeeds.
- [ ] Every requested variable uses the requested name.
- [ ] Every array operation has the intended shape.
- [ ] The system solution is verified and interpreted.
- [ ] The plot is labeled and followed by an interpretation.
- [ ] All reflection questions are answered.

## Optional challenge

Write a function `standardize_columns(X)` that returns a new array whose columns have mean 0 and standard deviation 1. Raise a `ValueError` if any column has standard deviation 0. Test the function on `scores` and verify its output.
