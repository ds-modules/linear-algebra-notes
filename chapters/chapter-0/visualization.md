---
kernelspec:
  name: python3
  display_name: Python 3
  language: python
---

# 0.5 Visualization with Matplotlib

A plot can reveal structure that is difficult to see in a table. A useful plot has a clear purpose, labeled axes, readable scales, and enough context to interpret it.

```{code-cell} python
import numpy as np
import matplotlib.pyplot as plt
```

## Line plots

Use a line plot when horizontal position represents an ordered quantity and connecting adjacent points is meaningful.

```{code-cell} python
t = np.linspace(0, 2 * np.pi, 200)
y = np.sin(t)

fig, ax = plt.subplots()
ax.plot(t, y, color="teal", linewidth=2, label=r"$\sin(t)$")
ax.axhline(0, color="black", linewidth=0.8)
ax.set(
    title="A sine wave",
    xlabel="t (radians)",
    ylabel="amplitude",
)
ax.legend()
ax.grid(alpha=0.25)
plt.show()
```

The `fig, ax = plt.subplots()` pattern gives explicit control over the figure and its axes. Prefer it over relying on hidden plotting state.

## Scatter plots

Use a scatter plot to examine the relationship between two measured variables.

```{code-cell} python
hours_studied = np.array([1, 2, 2.5, 3, 4, 5, 6])
quiz_score = np.array([58, 63, 68, 72, 78, 86, 91])

fig, ax = plt.subplots()
ax.scatter(hours_studied, quiz_score, color="darkorange", s=55)
ax.set(
    title="Study time and quiz score",
    xlabel="hours studied",
    ylabel="quiz score",
)
ax.grid(alpha=0.25)
plt.show()
```

The plot suggests a positive association, but the plot alone does not establish causation.

## Plotting vectors in the plane

A two-dimensional vector can be drawn as an arrow from the origin.

```{code-cell} python
u = np.array([2.0, 1.0])
v = np.array([-1.0, 2.0])

fig, ax = plt.subplots()
ax.quiver(
    [0, 0],
    [0, 0],
    [u[0], v[0]],
    [u[1], v[1]],
    angles="xy",
    scale_units="xy",
    scale=1,
    color=["teal", "darkorange"],
)
ax.set(
    xlim=(-2.5, 3),
    ylim=(-1, 3),
    xlabel="x",
    ylabel="y",
    title="Two vectors",
)
ax.set_aspect("equal")
ax.axhline(0, color="black", linewidth=0.8)
ax.axvline(0, color="black", linewidth=0.8)
ax.grid(alpha=0.25)
plt.show()
```

Setting equal aspect ratio is important: one unit in the horizontal direction should occupy the same visual distance as one unit vertically.

## Multiple panels

Subplots make comparisons easier when panels share a structure.

```{code-cell} python
x = np.linspace(-2, 2, 200)

fig, axes = plt.subplots(1, 2, figsize=(9, 3.5))
axes[0].plot(x, x, color="teal")
axes[0].set_title(r"$y=x$")
axes[1].plot(x, x ** 2, color="darkorange")
axes[1].set_title(r"$y=x^2$")

for ax in axes:
    ax.set_xlabel("x")
    ax.grid(alpha=0.25)

axes[0].set_ylabel("y")
fig.tight_layout()
plt.show()
```

## A plotting checklist

Before accepting a figure, ask:

- Does the plot type match the question?
- Are the axes labeled, including units when available?
- Is the title specific?
- Is a legend present only when needed?
- Could the scale distort the comparison?
- Are color and marker choices readable without relying on color alone?
- Does the surrounding text state what the figure shows?

## Practice

### Exercise 1: plot two functions

On one set of axes, plot $y=x$ and $y=x^2$ for $-2\leq x\leq2$. Add labels and a legend.

:::{dropdown} Solution
```{code-cell} python
x = np.linspace(-2, 2, 200)

fig, ax = plt.subplots()
ax.plot(x, x, label=r"$y=x$")
ax.plot(x, x ** 2, label=r"$y=x^2$")
ax.set(title="A line and a parabola", xlabel="x", ylabel="y")
ax.legend()
ax.grid(alpha=0.25)
plt.show()
```
:::

### Exercise 2: visualize vector addition

Let $u=(2,1)$ and $v=(1,2)$. Draw $u$, $v$, and $u+v$ from the origin. Use three distinguishable colors and an equal aspect ratio.

:::{dropdown} Solution
```{code-cell} python
u = np.array([2.0, 1.0])
v = np.array([1.0, 2.0])
w = u + v
vectors = np.vstack([u, v, w])

fig, ax = plt.subplots()
ax.quiver(
    np.zeros(3),
    np.zeros(3),
    vectors[:, 0],
    vectors[:, 1],
    angles="xy",
    scale_units="xy",
    scale=1,
    color=["teal", "darkorange", "purple"],
)
ax.set(xlim=(0, 4), ylim=(0, 4), xlabel="x", ylabel="y",
       title=r"Vectors $u$, $v$, and $u+v$")
ax.set_aspect("equal")
ax.grid(alpha=0.25)
plt.show()
```
:::
