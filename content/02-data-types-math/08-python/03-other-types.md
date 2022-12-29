---
title: "Other Types"
pre: "3. "
weight: 30
---

There are a few other built in data classes in Python. Let's take a quick look at them and see how they can be used in our programs.

## Complex Numbers

A complex number is used to store both a _real_ and an _imaginary_ part of a number. These are not typically used in most programs, but they are supported in Python. To create a complex number, use the following syntax:

```tex
<identifier> = <real>+<imaginary>j
```

So, to represent the complex number {{< math >}}$ 1 + 2i ${{< /math >}}, we would create a variable using this code:

```python
x = 1+2j
print(type(x))
```

This program would tell us that `x` is of type `complex`. We won't use complex numbers in this course, but it may be useful to know that they are available in Python.

## Boolean

Python supports a primitive data type named `bool` that can only store two values: `True` and `False`. As we might expect, we can use these boolean variables to store answers to questions in our program, such as "Is `x` greater than `y`?" At this point, we won't use boolean variables for much in our programs, but in a later module we'll cover the basics of boolean logic and learn how to use these variables to control how our program runs. 

To create a boolean variable, we can do the following:

```python
t = True
f = False
```

Notice that both `True` and `False` are _keywords_ in Python, which means that we won't have to put them in quotation marks to use them. These values can be used to directly represent the boolean values True and False, respectively. Some programming languages, most notably C, do not support boolean values in this way, but Python includes them as keywords.
