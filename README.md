# Numpy: From Basics to Advanced

---

## Topics

1. [Introduction to Numpy](#introduction-to-numpy)
2. [Basic Usage](#basic-usage)
3. [Intermediate Usage](#intermediate-usage)
4. [Advanced Usage](#advanced-usage)
5. [Specialized Topics](#specialized-topics)
6. [Performance Optimization](#performance-optimization)

---

## Introduction to Numpy

Numpy is a fundamental library for numerical computing in Python. It provides powerful tools for creating, manipulating, and analyzing numerical data, ranging from simple arrays to complex multidimensional operations.

### Key Features:
- Fast numerical computations.
- Support for multidimensional arrays.
- Comprehensive mathematical functions.
- Linear algebra, Fourier transforms, and random number capabilities.

---

## Basic Usage

### Creating Arrays
- **1D, 2D, and 3D Arrays:**
```python
array_1d = np.array([1, 2, 3])
array_2d = np.array([[1, 2], [3, 4]])
array_3d = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]]])
```
- **Predefined Arrays**
```python
zeros = np.zeros((2, 3))
identity = np.eye(3)
```

### Array Operations
- **Basic math:**
```python
array + 2
array * 3
```
- **Statistics:**
```python
mean = np.mean(array)
std_dev = np.std(array)
```
---
## Intermediate Usage

### Reshaping and Stacking
```python
reshaped = np.reshape(array, (3, 2))
vstacked = np.vstack((array1, array2))
hstacked = np.hstack((array1, array2))
```
### Boolean and Masking Operations
```python
bool_array = array > 2
masked_array = array[bool_array]
```
---
## Advanced Usage

### Linear Algebra
```python
matrix = np.array([[1, 2], [3, 4]])
transpose = np.transpose(matrix)
inverse = np.linalg.inv(matrix)
det = np.linalg.det(matrix)
```
### Broadcasting
```python
x = np.array([1, 2, 3])
y = np.array([[1], [2], [3]])
broadcasted_sum = x + y
```
### Custom Universal Functions (ufuncs)
```python
def custom_func(x, y):
    return x ** 2 + y ** 2

custom_ufunc = np.frompyfunc(custom_func, 2, 1)
result = custom_ufunc(array1, array2)
```
---

## Specialized Topics

### Fourier Transforms
```python
from numpy.fft import fft, ifft
signal_fft = fft(signal)
signal_reconstructed = ifft(signal_fft)
```
### Advanced Random Sampling
```python
random_sample = np.random.choice(array, size=5, replace=False)

```
### Structured Arrays
```python
structured_array = np.array([(1, 'Alice', 25), (2, 'Bob', 30)],
                             dtype=[('id', 'i4'), ('name', 'U10'), ('age', 'i4')])

```
---

## Performance Optimization

### Using Numba
```python
from numba import jit

@jit
def fast_function(x):
    return np.sum(x ** 2)

```
### Memory Mapping
```python
mmap_array = np.memmap('file.dat', dtype='float32', mode='w+', shape=(1000, 1000))
mmap_array[:] = np.random.rand(1000, 1000)
mmap_array.flush()

```
---












