# NumPy Complete Notes

## What is NumPy?

**NumPy (Numerical Python)** is a Python library used for:

* Fast numerical computations
* Working with arrays and matrices
* Mathematical operations
* Linear algebra
* Statistics
* Random number generation

---

# Installation

```bash
pip install numpy
```

# Import NumPy

```python
import numpy as np
```

---

# Why NumPy?

| Python List                     | NumPy Array                    |
| ------------------------------- | ------------------------------ |
| Slower                          | Faster                         |
| Uses more memory                | Uses less memory               |
| Limited mathematical operations | Supports vectorized operations |
| Good for general data           | Best for numerical data        |

---

# Creating Arrays

## 1D Array

```python
import numpy as np

a = np.array([1, 2, 3, 4, 5])
print(a)
```

Output

```text
[1 2 3 4 5]
```

---

## 2D Array

```python
a = np.array([
    [1, 2, 3],
    [4, 5, 6]
])

print(a)
```

Output

```text
[[1 2 3]
 [4 5 6]]
```

---

## 3D Array

```python
a = np.array([
    [[1, 2], [3, 4]],
    [[5, 6], [7, 8]]
])
```

---

# Array Properties

```python
a = np.array([[1, 2], [3, 4]])

print(a.ndim)
print(a.shape)
print(a.size)
print(a.dtype)
```

| Property | Description          |
| -------- | -------------------- |
| `ndim`   | Number of dimensions |
| `shape`  | Shape of array       |
| `size`   | Total elements       |
| `dtype`  | Data type            |

---

# Special Arrays

## Zeros

```python
np.zeros((2, 3))
```

## Ones

```python
np.ones((2, 3))
```

## Identity Matrix

```python
np.eye(3)
```

## Full

```python
np.full((2, 2), 5)
```

---

# Range Functions

## arange()

```python
np.arange(1, 10)
```

Output

```text
[1 2 3 4 5 6 7 8 9]
```

---

## linspace()

```python
np.linspace(1, 10, 5)
```

Output

```text
[1.00 3.25 5.50 7.75 10.00]
```

---

# Reshape

```python
a = np.arange(1, 10)
print(a.reshape(3, 3))
```

---

# Flatten

```python
a.flatten()
```

---

# Indexing

```python
a = np.array([10, 20, 30, 40])

print(a[0])
print(a[-1])
```

---

# Slicing

```python
print(a[1:3])
```

---

# Mathematical Operations

```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

print(a + b)
print(a - b)
print(a * b)
print(a / b)
```

---

# Aggregate Functions

```python
a = np.array([10, 20, 30, 40])

print(np.sum(a))
print(np.mean(a))
print(np.max(a))
print(np.min(a))
print(np.std(a))
```

---

# Sorting

```python
a = np.array([5, 2, 9, 1])

print(np.sort(a))
```

---

# Random Numbers

## Random Floats

```python
np.random.rand(3)
```

## Random Integers

```python
np.random.randint(1, 100, 5)
```

---

# Matrix Operations

```python
a = np.array([[1, 2], [3, 4]])
b = np.array([[5, 6], [7, 8]])

print(a + b)
print(a @ b)
```

`@` performs matrix multiplication.

---

# Transpose

```python
print(a.T)
```

---

# Broadcasting

```python
a = np.array([1, 2, 3])

print(a + 10)
```

Output

```text
[11 12 13]
```

---

# Boolean Indexing

```python
a = np.array([10, 20, 30, 40])

print(a[a > 20])
```

---

# Copy vs View

## Copy

```python
b = a.copy()
```

Creates an independent copy.

## View

```python
b = a.view()
```

Shares memory with the original array.

---

# Concatenate

```python
a = np.array([1, 2])
b = np.array([3, 4])

print(np.concatenate((a, b)))
```

---

# Split

```python
a = np.array([1, 2, 3, 4])

print(np.split(a, 2))
```

---

# Mathematical Functions

```python
np.sqrt(a)
np.exp(a)
np.log(a)
np.sin(a)
np.cos(a)
np.abs(a)
```

---

# Data Types

```python
a = np.array([1, 2, 3], dtype=float)
print(a)
```

---

# Save and Load Arrays

## Save

```python
np.save("data.npy", a)
```

## Load

```python
np.load("data.npy")
```

---

# Most Common NumPy Functions

| Function           | Purpose              |
| ------------------ | -------------------- |
| `np.array()`       | Create array         |
| `np.zeros()`       | Array of zeros       |
| `np.ones()`        | Array of ones        |
| `np.eye()`         | Identity matrix      |
| `np.full()`        | Fill array           |
| `np.arange()`      | Generate range       |
| `np.linspace()`    | Evenly spaced values |
| `reshape()`        | Change shape         |
| `flatten()`        | Convert to 1D        |
| `.T`               | Transpose            |
| `sum()`            | Sum                  |
| `mean()`           | Average              |
| `max()`            | Maximum              |
| `min()`            | Minimum              |
| `sort()`           | Sort                 |
| `sqrt()`           | Square root          |
| `random.rand()`    | Random floats        |
| `random.randint()` | Random integers      |
| `concatenate()`    | Join arrays          |
| `split()`          | Split arrays         |
| `copy()`           | Deep copy            |
| `view()`           | Shallow copy         |

---

# Advantages of NumPy

* Faster than Python lists
* Uses less memory
* Supports multidimensional arrays
* Powerful mathematical functions
* Widely used in Data Science, Machine Learning, AI, and Scientific Computing

---

# Interview Questions

1. What is NumPy?
2. Why is NumPy faster than Python lists?
3. Difference between Python list and NumPy array.
4. What is vectorization?
5. Difference between `copy()` and `view()`.
6. Difference between `arange()` and `linspace()`.
7. What is broadcasting?
8. Difference between `reshape()` and `flatten()`.
9. What are `ndim`, `shape`, `size`, and `dtype`?
10. Difference between element-wise multiplication (`*`) and matrix multiplication (`@`)?
