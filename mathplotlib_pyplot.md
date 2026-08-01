# Complete Matplotlib Notes (Python)

Matplotlib is the most popular Python library used for **data visualization**. It helps create graphs, charts, and plots from data.

---

# 1. Installation

```bash
pip install matplotlib
```

Import the library:

```python
import matplotlib.pyplot as plt
```

---

# 2. Basic Line Plot

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [10, 20, 15, 25, 30]

plt.plot(x, y)
plt.show()
```

---

# 3. Labels

### X-axis Label

```python
plt.xlabel("X Axis")
```

### Y-axis Label

```python
plt.ylabel("Y Axis")
```

### Title

```python
plt.title("Sales Report")
```

Example

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4]
y = [5, 10, 15, 20]

plt.plot(x, y)
plt.xlabel("Months")
plt.ylabel("Sales")
plt.title("Monthly Sales")
plt.show()
```

---

# 4. Line Color

```python
plt.plot(x, y, color="red")
```

or

```python
plt.plot(x, y, c="blue")
```

Common colors:

- red
- blue
- green
- yellow
- black
- orange
- purple
- pink
- cyan
- magenta

---

# 5. Line Style

```python
plt.plot(x, y, linestyle="--")
```

Styles:

| Style | Meaning |
|-------|---------|
| `-` | Solid |
| `--` | Dashed |
| `-.` | Dash-dot |
| `:` | Dotted |

Example

```python
plt.plot(x, y, linestyle=":")
```

---

# 6. Line Width

```python
plt.plot(x, y, linewidth=3)
```

---

# 7. Markers

```python
plt.plot(x, y, marker="o")
```

Common markers:

| Marker | Shape |
|---------|-------|
| `o` | Circle |
| `*` | Star |
| `+` | Plus |
| `x` | Cross |
| `s` | Square |
| `D` | Diamond |
| `^` | Triangle Up |
| `v` | Triangle Down |

Example

```python
plt.plot(x, y, marker="*", markersize=15)
```

---

# 8. Marker Colors

```python
plt.plot(
    x,
    y,
    marker="o",
    markerfacecolor="red",
    markeredgecolor="black"
)
```

---

# 9. Marker Size

```python
plt.plot(x, y, markersize=12)
```

---

# 10. Multiple Lines

```python
x = [1, 2, 3, 4]

y1 = [2, 4, 6, 8]
y2 = [1, 3, 5, 7]

plt.plot(x, y1)
plt.plot(x, y2)

plt.show()
```

---

# 11. Legend

```python
plt.plot(x, y1, label="Python")
plt.plot(x, y2, label="Java")

plt.legend()
plt.show()
```

Legend positions:

- upper right
- upper left
- lower right
- lower left
- center

Example

```python
plt.legend(loc="upper left")
```

---

# 12. Grid

```python
plt.grid()
```

Customize

```python
plt.grid(color="red", linestyle="--", linewidth=1)
```

---

# 13. Figure Size

```python
plt.figure(figsize=(8, 5))
```

---

# 14. Axis Limits

```python
plt.xlim(0, 10)
plt.ylim(0, 50)
```

---

# 15. Axis Ticks

```python
plt.xticks([1, 2, 3, 4])
plt.yticks([10, 20, 30, 40])
```

---

# 16. Scatter Plot

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4]
y = [5, 8, 2, 9]

plt.scatter(x, y)
plt.show()
```

Customize

```python
plt.scatter(
    x,
    y,
    color="red",
    s=200,
    marker="*"
)
```

---

# 17. Bar Chart

```python
students = ["A", "B", "C", "D"]
marks = [80, 75, 90, 85]

plt.bar(students, marks)
plt.show()
```

Horizontal Bar Chart

```python
plt.barh(students, marks)
```

---

# 18. Histogram

```python
data = [20, 25, 30, 35, 40, 20, 30, 35]

plt.hist(data)
plt.show()
```

With bins

```python
plt.hist(data, bins=5)
```

---

# 19. Pie Chart

```python
subjects = ["Python", "Java", "C"]
students = [40, 30, 30]

plt.pie(students, labels=subjects)
plt.show()
```

Percentage

```python
plt.pie(
    students,
    labels=subjects,
    autopct="%1.1f%%"
)
```

Explode

```python
explode = (0.1, 0, 0)

plt.pie(
    students,
    labels=subjects,
    explode=explode,
    autopct="%1.1f%%"
)
```

---

# 20. Box Plot

```python
data = [1, 2, 3, 4, 5, 6, 8, 10]

plt.boxplot(data)
plt.show()
```

---

# 21. Area Plot

```python
x = [1, 2, 3, 4]
y = [2, 4, 6, 8]

plt.fill_between(x, y)
plt.show()
```

---

# 22. Subplots

```python
import matplotlib.pyplot as plt

x = [1, 2, 3]
y = [2, 4, 6]

plt.subplot(1, 2, 1)
plt.plot(x, y)

plt.subplot(1, 2, 2)
plt.bar(x, y)

plt.show()
```

---

# 23. Save Figure

```python
plt.savefig("graph.png")
```

Save as PDF

```python
plt.savefig("graph.pdf")
```

---

# 24. Close Figure

```python
plt.close()
```

---

# 25. Display Plot

```python
plt.show()
```

Always call `plt.show()` after plotting.

---

# 26. Plot Parameters

```python
plt.plot(
    x,
    y,
    color="red",
    linestyle="--",
    linewidth=3,
    marker="o",
    markersize=10,
    label="Sales"
)
```

---

# 27. Styles

```python
plt.style.use("ggplot")
```

Other styles:

```python
plt.style.use("classic")
plt.style.use("dark_background")
plt.style.use("bmh")
plt.style.use("fivethirtyeight")
```

---

# 28. Common Errors

Wrong:

```python
plt.xlable("X")
```

Correct:

```python
plt.xlabel("X")
```

Wrong:

```python
plt.ylable("Y")
```

Correct:

```python
plt.ylabel("Y")
```

Wrong:

```python
plt.titel("Graph")
```

Correct:

```python
plt.title("Graph")
```

---

# 29. Important Functions

| Function | Purpose |
|----------|---------|
| `plot()` | Line Chart |
| `scatter()` | Scatter Plot |
| `bar()` | Vertical Bar Chart |
| `barh()` | Horizontal Bar Chart |
| `hist()` | Histogram |
| `pie()` | Pie Chart |
| `boxplot()` | Box Plot |
| `fill_between()` | Area Plot |
| `subplot()` | Multiple Graphs |
| `xlabel()` | X-axis Label |
| `ylabel()` | Y-axis Label |
| `title()` | Graph Title |
| `legend()` | Display Legend |
| `grid()` | Display Grid |
| `figure()` | Figure Size |
| `xlim()` | X-axis Range |
| `ylim()` | Y-axis Range |
| `xticks()` | X-axis Ticks |
| `yticks()` | Y-axis Ticks |
| `savefig()` | Save Graph |
| `show()` | Display Graph |
| `close()` | Close Figure |

---

# 30. Complete Example

```python
import matplotlib.pyplot as plt

months = ["Jan", "Feb", "Mar", "Apr", "May"]
sales = [100, 150, 120, 180, 200]

plt.figure(figsize=(8, 5))

plt.plot(
    months,
    sales,
    color="blue",
    linestyle="-",
    linewidth=2,
    marker="o",
    markersize=8,
    label="Sales"
)

plt.xlabel("Months")
plt.ylabel("Sales")
plt.title("Monthly Sales Report")

plt.grid(True)
plt.legend()

plt.show()
```

---

# Interview Questions

1. What is Matplotlib?
2. What is `pyplot`?
3. Difference between `plot()` and `scatter()`?
4. Difference between `bar()` and `barh()`?
5. What is a histogram?
6. What is a pie chart?
7. Why is `plt.show()` used?
8. Difference between `xlabel()` and `ylabel()`?
9. How do you add a legend?
10. How do you save a graph?
11. What is `subplot()`?
12. What is the purpose of `grid()`?
13. How do you change line color and style?
14. What are markers?
15. Difference between `figure()` and `subplot()`?