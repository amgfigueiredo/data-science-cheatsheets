# NumPy Cheat Sheet

## Introduction

NumPy is a fundamental Python library for numerical computing, providing support for large, multi-dimensional arrays and matrices, along with mathematical functions to operate on them.

## Installation

```

pip install numpy

```

## Importing NumPy

```

import numpy as np

```

## Creating Arrays

#### Create an array from a list
```
arr = np.array([1, 2, 3])
arr2d = np.array([[1, 2, 3], [4, 5, 6]])
```

#### Create an array of zeros and ones
```
np.zeros((2, 3))  # 2x3 array of zeros
np.ones((2, 3))   # 2x3 array of ones
```

#### Create an empty array
```

np.empty((2, 2))

```

#### Create an array with a range of values
```
np.arange(0, 10, 2)  # From 0 to 10 with step 2
np.linspace(0, 1, 5) # 5 equally spaced values between 0 and 1
```

#### Create an array with random values
```
np.random.rand(2, 3)  # Random float values
np.random.randint(0, 10, (2, 3))  # Random integers
```

#### Set seed for reproducibility
```

np.random.seed(42)

```

## Array Properties

```
arr.shape  # Shape of array
arr.size   # Number of elements
arr.dtype  # Data type
arr.ndim   # Number of dimensions
```

## Reshaping and Flattening

```
arr.reshape(3, 2)  # Reshape array
arr.flatten()  # Flatten multi-dimensional array
```

## Indexing and Slicing

```
arr[0]       # First element
arr[:, 1]    # First column, all rows
arr[1:3]     # Slice from index 1 to 2
```

## Mathematical Operations

#### Element-wise operations
```
np.add(arr1, arr2)
np.subtract(arr1, arr2)
np.multiply(arr1, arr2)
np.divide(arr1, arr2)
```

#### Matrix multiplication
```

np.dot(arr1, arr2)

```

#### Statistical functions
```
np.sum(arr)
np.mean(arr)
np.min(arr)
np.max(arr)
np.std(arr)
np.sqrt(arr)
np.exp(arr)
np.log(arr)
```

#### Linear Algebra
```
np.linalg.inv(arr)  # Matrix inverse
np.linalg.det(arr)  # Determinant
np.linalg.eig(arr)  # Eigenvalues and eigenvectors
```

#### Boolean Operations
```
arr1 > arr2  # Compare arrays
arr[arr > 5]  # Select elements greater than 5
```

## Saving and Loading Arrays

```
np.save('file.npy', arr)
np.savetxt('array.txt', arr)
np.load('file.npy')
np.loadtxt('array.txt')
```

## Aggregation Functions

```
arr.sum(axis=0)  # Sum along rows
arr.sum(axis=1)  # Sum along columns
```

## Stacking and Splitting

```
np.vstack((arr1, arr2))  # Vertical stack
np.hstack((arr1, arr2))  # Horizontal stack
np.split(arr, 2)  # Split array into 2 parts
```

## Sorting
```
np.sort(arr)  # Sort array
arr.sort(axis=0)  # Sort along rows
```

## Rounding

```
df[['Screen_Size_cm']] = np.round(df[['Screen_Size_cm']], 2)
```
