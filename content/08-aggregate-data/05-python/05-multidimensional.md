---
title: "Multidimensional Lists"
pre: "5. "
weight: 50
---

To create a multidimensional list in Python, simply provide additional square brackets `[]` as part of the list declaration. 

```python
#2d integer list
a = [[1, 2], [3, 4], [5, 6]]

#3d boolean list
b = [[[True, False], [False, True]], [[True, False], [True, False]], [[True, False], [False, True]], [[True, False], [True, False]]]
```

As you can see, a multidimensional lists is a list of lists. Typically, multidimensional lists will only have 2 or 3 dimensions, but there is no functional limit on the number of dimensions in Python.

Each of the examples above will create a multidimensional list with each dimension consisting of lists of the same length. However, it is possible to have lists of different length within the same dimension, though it can be much more difficult to manage that scenario. We won't deal with that in this course, but it may be useful in some situations.

Of course, at times we may want to create an empty multidimensional list as well. In Python, we can do the following:

```python
a = []
a.append([])
a.append([])
```

The example above creates an empty list named `a`, then appends two empty lists as the first two elements in `a`. This will make `a` a multidimensional list, as each element of `a` is itself a list. On a later page, we'll see how to do this same operation using a loop.

To get the size of each dimension, we can use the `len` function on an element at that dimension:

```python
#2d integer list
a = [[1, 2], [3, 4], [5, 6]]

print(len(a)) # 3
print(len(a[0])) # 2
```

Of course, we'll need to make sure that `a[0]` exists before trying to find its length. If not, it will cause an error.

To access or assign elements in a multidimensional list, add additional square brackets `[]` for each dimension:

```python
#2d integer list
a = [[1, 2], [3, 4], [5, 6]]

a[0][1] = 10

print(a[0][1]) # 10
print(a[1][1]) # 4
print(a[2][0]) # 5
```

Again, remember that the indexes in each list dimension begin at 0. So, `a[1][1]` is actually accessing the second element in the first dimension of `a`, which is a list containing `[3, 4]`, and then the second element in that list, which is `4`.