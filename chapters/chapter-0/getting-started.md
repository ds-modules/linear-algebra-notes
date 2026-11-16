---
kernelspec:
  name: python3
  display_name: Python 3
  language: python
---

# 0.1 Getting Started with Jupyter

Jupyter notebooks combine explanatory text, mathematical notation, executable code, and output in one document. A notebook is useful only when its code can be rerun from top to bottom and produce the intended results.

## Choose a way to run the notebooks

You may use a course-provided JupyterHub or another hosted notebook service. To work locally, install Python 3.11 or newer and create an isolated environment:

```bash
python -m venv .venv
```

Activate it on Windows:

```powershell
.\.venv\Scripts\Activate.ps1
```

Activate it on macOS or Linux:

```bash
source .venv/bin/activate
```

Then install the course packages and start Jupyter:

```bash
python -m pip install -r requirements.txt
jupyter lab
```

:::{admonition} Why use an environment?
:class: note
An environment keeps this course's package versions separate from other Python projects. Activate it again whenever you return to the course.
:::

## Cells and the kernel

A notebook has two cell types that we use often:

- **Markdown cells** contain prose, headings, links, and mathematics.
- **Code cells** send Python instructions to the **kernel**, the process that stores variables and performs calculations.

Run the next cell. The value below the cell is its output.

```{code-cell} python
course = "Linear Algebra"
chapter = 0
f"{course}, Chapter {chapter}"
```

The kernel remembers values created by earlier cells:

```{code-cell} python
chapter + 1
```

This memory can cause a common notebook error: code may appear to work only because an old variable remains in the kernel. Before submitting work, use **Restart Kernel and Run All Cells**. If the notebook fails, fix the first failing cell and run all cells again.

## Errors are information

Read a traceback from its final line upward. The final line names the error and usually gives the most useful clue.

For example, this code would produce a `NameError` because `chaptr` was never defined:

```python
chaptr + 1
```

Useful first checks are:

1. Is every name spelled consistently?
2. Did the cell that defines the name run?
3. Are parentheses and brackets balanced?
4. Does the object have the shape and type you expected?

## Imports

An import makes a package available. We use standard aliases so that course code is easy to read.

```{code-cell} python
import numpy as np
import matplotlib.pyplot as plt
```

Import packages near the beginning of a notebook. Avoid `from numpy import *`; it hides where names come from and can overwrite other names.

## Markdown and mathematics

Use Markdown cells to explain the goal, method, and conclusion of a calculation. Write inline mathematics between dollar signs, such as `$Ax=b$`, and displayed mathematics between double dollar signs:

```markdown
$$
A =
\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}.
$$
```

This renders as

$$
A =
\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}.
$$

## Quick check

1. What is the difference between a code cell and a Markdown cell?
2. Why should you restart the kernel and run all cells before submitting?
3. What does `import numpy as np` make `np` mean?

:::{dropdown} Check your answers
1. A code cell is executed by the Python kernel; a Markdown cell presents formatted text and mathematics.
2. Restarting removes hidden state and confirms that the notebook works in order from a clean session.
3. `np` is the conventional local alias for the imported `numpy` package.
:::
