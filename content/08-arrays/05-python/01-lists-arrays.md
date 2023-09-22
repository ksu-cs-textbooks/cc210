---
title: "Lists & Arrays"
pre: "1. "
weight: 10
---

The array is very popular in compiled languages as the "first choice" for simple aggregate data--the compiler can make a lot of optimizations and speed up performance of the executable code.  Interpreted languages have much less opportunity for optimization, and the list is generally their first choice for aggregated data.

### Compare and Contrast List and Array

1. List have a variable length, you can change its number of elements. If you have a list of two items `[1,2]`, you and add another item, `[1,2,3]` or take one away `[1]`.  Arrays are a fixed length, once created the always have the exact same number of elements.
1. List and Arrays both have a length, they have 0 or more elements.
1. By convention, Python List hold a single data type^[the Python 'tuple' type is generally preferred when different types of data are used].  Arrays ALWAYS hold a single data type.
1. The valid range of indices in an array are fixed--arrays are of unchanging length, but may contain `None`s.  The valid ranges of a list depend on how many elements it currently holds.

## Lists

In Python most uses of arrays will actually be performed using a **List**[^1]

[^1]: Python has a numeric array module. It is very limited and not good for general purpose collections.

To create a list in Python, simply provide a **variable name** and the **items** to be stored in the list:
`<variable_name> = [<item1>, <item2>, <item3>, ... , <itemN>]` 
Here are some examples:

```python
#integer list
a = [1, 2, 3, 4, 5]

#boolean list
b = [True, False, True, False]

#float list
c = [1.2, 2.3, 3.4]

#empty list
d = []
```

Lists are objects of type "list", `print(type([1,2,3]))`  will display `<class 'list'>`.  List have a <b>special syntax</b> for instantiation, the `[<object>, <object>, ...]`[^2] notation.  The built-in function `list()`  converts other types of iterable aggregate data into a list. 

[^2]: Nearly everything in Python is an object: values, variables, classes, functions