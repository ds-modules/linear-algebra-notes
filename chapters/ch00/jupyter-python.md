---
kernelspec:
  name: python3
  display_name: Python 3
---

# 0.2 Python in the Textbook

Some textbook pages mix explanatory text with short Python examples. Their output appears underneath. These are worked demonstrations to read; you do not need to edit or run them.

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

Lists store ordered collections. Numeric work in this book mostly uses NumPy arrays, but lists show up in ordinary Python.

```{code-cell} python
coords = [1, 2, 3]
coords.append(4)
print(coords)
print(coords[0], coords[-1])
print(coords[1:3])  # start inclusive, end exclusive
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

Next: [0.3 NumPy Arrays](numpy.md).
