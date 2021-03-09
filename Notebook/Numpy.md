## Numpy

## Create a Python numpy array

Use `np.arange()` to generate a numpy array


```python
import numpy as np

a1 = np.arange(1, 13)
print(a1)
```

    [ 1  2  3  4  5  6  7  8  9 10 11 12]


Use `reshape()` method to reshape `a1` array to a 3 by 4 dimensional array.


```python
a1_2d = a1.reshape(3, 4)
print(a1_2d)
```

    [[ 1  2  3  4]
     [ 5  6  7  8]
     [ 9 10 11 12]]


If you want numpy to automatically determine what size/length a particular dimension should be, specify the dimension as `-1` for that dimension.


```python
print(a1.reshape(-1, 4))
```

    [[ 1  2  3  4]
     [ 5  6  7  8]
     [ 9 10 11 12]]


By default, `reshape()` reshapes the array along the 0th dimension (row). This behavior can be changed via the `order` parameter.


```python
print(a1.reshape(3, 4, order='F'))
```

    [[ 1  4  7 10]
     [ 2  5  8 11]
     [ 3  6  9 12]]


The `ravel()` method lets you convert multi-dimensional arrays to 1D arrays.


```python
print(a1_2d.ravel())
```

    [ 1  2  3  4  5  6  7  8  9 10 11 12]


## Concatenate/stack arrays with `np.stack()` and `np.hstack()`

Create two 1D arrays


```python
a1 = np.arange(1, 13)
a2 = np.arange(13, 25)
```

Use `np.stack()` to concatenate/stack arrays.


```python
stack0 = np.stack((a1, a2))
print(stack0)
```

    [[ 1  2  3  4  5  6  7  8  9 10 11 12]
     [13 14 15 16 17 18 19 20 21 22 23 24]]



```python
stack1 = np.stack((a1, a2), axis=1)
print(stack1)
```

    [[ 1 13]
     [ 2 14]
     [ 3 15]
     [ 4 16]
     [ 5 17]
     [ 6 18]
     [ 7 19]
     [ 8 20]
     [ 9 21]
     [10 22]
     [11 23]
     [12 24]]


Concatenate as a long 1D array with `np.hstack()`


```python
stack_long = np.hstack((a1, a2))
print(stack_long)
```

    [ 1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24]
