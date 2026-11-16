---
kernelspec:
  name: python3
  display_name: Python 3
  language: python
---

# 0.2 Python Basics

This section introduces the small part of Python needed to express calculations clearly. Focus on reading code, predicting its result, and checking whether the result is reasonable.

## Values, variables, and expressions

Python distinguishes several basic types:

```{code-cell} python
count = 4                 # integer
temperature = 21.5        # floating-point number
label = "experiment A"    # string
is_complete = False       # Boolean

type(temperature)
```

A variable name refers to a value. Assignment evaluates the right side first and then stores the result under the name on the left.

```{code-cell} python
x = 3
x = x + 2
x
```

Here `x = x + 2` means “replace `x` by its old value plus 2.” It is assignment, not a mathematical equation.

Common arithmetic operators are:

| Operation | Python | Example result |
|---|---|---:|
| Addition | `+` | `7 + 2` gives `9` |
| Subtraction | `-` | `7 - 2` gives `5` |
| Multiplication | `*` | `7 * 2` gives `14` |
| Division | `/` | `7 / 2` gives `3.5` |
| Integer quotient | `//` | `7 // 2` gives `3` |
| Remainder | `%` | `7 % 2` gives `1` |
| Power | `**` | `7 ** 2` gives `49` |

Use parentheses when they make the intended order clear.

```{code-cell} python
distance = 120
time = 2.5
speed = distance / time
speed
```

## Comparisons and Booleans

Comparisons produce `True` or `False`.

```{code-cell} python
speed > 40, speed == 48, speed != 50
```

Use `==` to compare values and `=` to assign a value. Combine conditions with `and`, `or`, and `not`.

## Collections and indexing

A list stores an ordered collection of Python objects.

```{code-cell} python
measurements = [2.1, 2.4, 2.2, 2.8]
first = measurements[0]
last = measurements[-1]
first, last, len(measurements)
```

Python uses half-open slices: `start` is included and `stop` is excluded.

```{code-cell} python
measurements[1:3]
```

Lists are useful for general Python data. Numerical linear algebra uses NumPy arrays, introduced in the next section.

## Functions

A function packages a calculation under a name. Parameters are inputs, and `return` sends a result back to the caller.

```{code-cell} python
def average(a, b):
    """Return the arithmetic mean of two numbers."""
    return (a + b) / 2

average(8, 12)
```

Indentation defines the function body. Use four spaces for each indentation level.

Functions make assumptions easier to state and test:

```{code-cell} python
def percent_error(observed, expected):
    """Return absolute percent error when expected is nonzero."""
    if expected == 0:
        raise ValueError("expected must be nonzero")
    return 100 * abs(observed - expected) / abs(expected)

percent_error(9.8, 10)
```

## Conditionals

A conditional selects code based on a Boolean condition.

```{code-cell} python
determinant = -0.25

if determinant == 0:
    message = "singular"
elif determinant > 0:
    message = "positive determinant"
else:
    message = "negative determinant"

message
```

Later, we will avoid exact equality tests for most floating-point calculations because rounding can produce tiny nonzero values.

## Loops

A `for` loop repeats an action for each item in a collection.

```{code-cell} python
values = [1, 2, 3, 4]
squares = []

for value in values:
    squares.append(value ** 2)

squares
```

Loops are important for learning Python and for tasks that genuinely proceed one item at a time. For array arithmetic, NumPy operations are usually shorter and faster.

## Writing readable code

- Choose names that describe meaning: `height` is better than `h1`.
- Put spaces around operators.
- Break a calculation into named intermediate steps.
- Add comments that explain *why*, not comments that merely repeat the code.
- Write small functions when a calculation is reused.

## Practice

### Exercise 1: temperature conversion

Write a function `celsius_to_fahrenheit(celsius)` that implements

$$
F = \frac{9}{5}C + 32.
$$

Test it with $C=0$ and $C=100$.

:::{dropdown} Solution
```{code-cell} python
def celsius_to_fahrenheit(celsius):
    return (9 / 5) * celsius + 32

celsius_to_fahrenheit(0), celsius_to_fahrenheit(100)
```
The results should be `32.0` and `212.0`.
:::

### Exercise 2: classify a number

Write a function that returns `"negative"`, `"zero"`, or `"positive"` for a given number.

:::{dropdown} Solution
```{code-cell} python
def classify_number(value):
    if value < 0:
        return "negative"
    if value == 0:
        return "zero"
    return "positive"

classify_number(-3), classify_number(0), classify_number(2.5)
```
:::

### Exercise 3: accumulate a sum

Use a loop to find the sum of the numbers from 1 through 10. Then compare your result with `sum(range(1, 11))`.

:::{dropdown} Solution
```{code-cell} python
total = 0
for number in range(1, 11):
    total = total + number

total, sum(range(1, 11))
```
Both results should be `55`.
:::
