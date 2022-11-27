
---

layout: post
title:  "Difference between numpy array shape R 1 and R"
categories: numpy
tag: [python, numpy, array]

---




# Difference between numpy.array shape (R, 1) and (R,) [1]

## Python numpy array 에서 shape (R, 1) 과 (R,) 의 차이점  

The meaning of shapes in NumPy

NumPy arrays consist of two parts.
- a data buffer : a block of raw elements
- a view : describes how to interpret the data buffer

For example, if we create an array of 12 integers:
```python
a = numpy.arange(12)

```

## An easy way to think of this is that numpy is working exactly as expected here, but Python's printing of tuples can be misleading.

- `(R,)`
  - $\rightarrow$ One Element Tuple  
  - the shape of the `ndarray` is a tuple with a single elements, so is printed by Python with a trailing comma. Without the extra comma, it would be [ambiguous with an expression in parenthesis](https://wiki.python.org/moin/TupleSyntax).
  - `ndarray` with a single dimension can be though of as a column vector of length `R`.

- `(R, 1)`
  - $\rightarrow$ Multiple Element Tuple  
  - the tuple has two elements, so can be thought of as a row vector (or a matrix with 1 row) of length `R`. ??????????


## Python's tuple syntax [3]

Zero Element Tuples  

- 괄호가 꼭 있어야 하고, `comma`가 없다.

  ```python
  ()
  ```


One Element Tuples  

- `comma`가 꼭 있어야 한다.

  ```python
  1,
  ```


- 다른 expression 들과 마찬가지로 괄호는 option  이다. 다시말해서 여기서 tuple을 define하는 것은 괄호가 아니고 `comma`이다.

  ```python
  (1,)
  ```

Multiple Element Tuples  

- 각 tuple element들 사이의 `comma`가 꼭 있어야 한다.  
  ```python
  1,2,3
  ```

- 맨 마지막 요소 뒤에 `comma`를 붙여서 쓸 수도 있다.  그러나 맨 뒤의 `comma`는 option 이다. (없어도 된다는 의미)
  ```python
  1,2,3,
  ```

- 다른 expression 들과 마찬가지로 괄호는 option 이다.  다시 말해서 여기서 tuple을 define하는 것은 괄호가 아니고 `comma`이다.

  ```python
  (1,2,3)
  or
  (1,2,3,)
  ```

  



## References
[1] [Difference between numpy.array shape (R, 1) and (R,)](https://stackoverflow.com/questions/22053050/difference-between-numpy-array-shape-r-1-and-r)
[2] [Internal organization of NumPy arrays](https://numpy.org/doc/stable/dev/internals.html#numpy-internals)
[3] [Python's tuple syntax](https://wiki.python.org/moin/TupleSyntax)
