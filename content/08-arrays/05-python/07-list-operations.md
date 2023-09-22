---
title: "List Operations"
pre: "7. "
weight: 70
---

We've already covered one of the operations we can perform on a list, `len`. Let's look at a few more.

### Concatenation

Lists in Python can be concatenated:

```python
a = [1, 2, 3]
b = [4, 5, 6]
c = a + b

print(c) # [1, 2, 3, 4, 5, 6]
```

### Slicing Lists (sub-list)

Python natively supports **slicing** of several data types, including lists. This allows us to easily obtain a copy of the list containing a subset of elements in the original list:

```python

a = [1, 2, 3, 4, 5]

b = a[2:4] # elements from index 2 (included) to index 4 (excluded)

print(b[0]) # 3
print(b[1]) # 4
print(b[2]) # error - list index out of range

b[0] = 1

print(a[2]) # 3 - the original list is unchanged
print(b[0]) # 1 - but the new list is
```

We can also omit either index in a slice to use the defaults. The first index will default to index 0, and the second will default to the length of the list. Negative indexes work as well:

```python
a = [1, 2, 3, 4, 5]

b = a[:3]  # [1, 2, 3]
c = a[2:]  # [3, 4, 5]
d = a[:]   # [1, 2, 3, 4, 5]
e = a[:-2] # [1, 2, 3]
```

We can even use indexes that are out of range, and the slice operation will still work with the data available:

```python
a = [1, 2, 3, 4, 5]

b = a[2:50]  # [3, 4, 5]
c = a[50:55] # []
```

Finally, we can even assign directly to a slice of a list. This may even change the size of the original list, and is a very powerful way to manipulate lists in Python:

```python
a = [1, 2, 3, 4, 5]

#assign a large list to a small slice
a[2:4] = [6, 7, 8, 9]
print(a) # [1, 2, 6, 7, 8, 9, 5]

#assign a small list to a large slice
a[1:] = [10]
print(a) # [1, 10]

#clear a list by assigning an empty list to the entire slice
a[:] = []
print(a) # []
```


## Cloning a list

Lists are objects, a list-variable's name refers to a specific place in memory.  This means you have to be deliberate about how you make variables that point to that space and how you clone a list.  A clone is exactly the same list elements, but in a different place in memory.

![Objects in Memory](/images/08-array/arrays_obj_memory_p.png)

In the figure above 
1. Line 1 creates a list in memory for the name `a`.
1. Line 2 creates a new variable `b`, but assigns it the list `a`. `b` has become an **alias** for a, but they are the same list in memory.
1. Line 3 changes the value of b[0],  since `b` is a alias of `a` it effectively changes a[0].
1. Line 4 reassigns `b` to a new list, located at a different place in memory.

This means to make a clone of a list you need to use the copy module's deepcopy() method, not the list classes copy().

```python
import copy
a = [ [1,2],[3,4]]
b = a.copy() # roughly the same as b = a
b[0][0] = 0
print(a) # [[0,2],[3,4]]
c = copy.deepcopy(a)
c[0][0] = 1
print(a) # [[0,2],[3,4]]
print(c) # [[1,2],[3,4]]
```

To learn more about these methods of manipulating lists and how to use them, consult the official Python documentation linked below. 

**Reference:** [An Informal Introduction to Python: Lists](https://docs.python.org/3/tutorial/introduction.html#lists) <br>
**Reference:** [Data Structures: More on Lists](https://docs.python.org/3/tutorial/datastructures.html#more-on-lists)