---
kernelspec:
  name: python3
  display_name: Python 3
---

# Jupyter and Python basics

## Jupyter notebooks

A notebook is a sequence of **cells**:

- **Markdown cells** — notes and math (like this page)
- **Code cells** — Python that you run; output appears below

Typical workflow: change a cell → run it → read the output → fix → re-run. Restarting the kernel clears all variables.

```{tip}
Run cells **in order** the first time through. Later cells often depend on earlier ones.
```

## Variables and types

```{code-cell} python
x = 3
y = 2.5
name = "linear algebra"
flag = True

print(type(x), type(y), type(name), type(flag))
print(x + y)
```

## Lists

Lists are ordered and mutable. For serious numeric work we will prefer NumPy arrays, but lists appear in everyday Python.

```{code-cell} python
coords = [1, 2, 3]
coords.append(4)
print(coords)
print(coords[0], coords[-1])
print(coords[1:3])  # slicing: start inclusive, end exclusive
```

## Loops and comprehensions

```{code-cell} python
squares = []
for i in range(5):
    squares.append(i**2)
print(squares)

squares2 = [i**2 for i in range(5)]
print(squares2)
```

## Functions

```{code-cell} python
def average(values):
    """Return the arithmetic mean of a non-empty list of numbers."""
    return sum(values) / len(values)

print(average([2, 4, 6]))
```

## Control flow

```{code-cell} python
def describe_n(n):
    if n > 0:
        return "positive"
    elif n < 0:
        return "negative"
    else:
        return "zero"

print(describe_n(3), describe_n(-1), describe_n(0))
```

## Mini-check

Before moving on, make sure you can:

1. Assign variables and print their types  
2. Index and slice a list  
3. Write a short `for` loop and a list comprehension  
4. Define a function with a docstring and return value  

Next: [NumPy for linear algebra](numpy.md).
