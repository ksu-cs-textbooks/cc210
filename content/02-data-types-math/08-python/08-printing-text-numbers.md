---
title: "Printing Text & Numbers"
pre: "8. "
weight: 80
---

## Printing Text with Variables

Now that we've learned how to run our program and provide it some input, we must also learn how to provide output that includes our variables as well as text all on the same line. There are a few ways to accomplish this.

First, we can use `print("text", end="")` to print text without a newline character at the end, so that the next output will begin on the same line. So, we could use that to print text and variables on the same line. Here's an example:

```python
x = 1
y = 2
print("Variable x: ", end="")
print(x, end="")
print(", Variable y: ", end="")
print(y)
```

will produce this output:

```tex
Variable x: 1, Variable y: 2
```

In Python, we can also provide multiple arguments to the `print()` method, and it will print each one in order, separated by a space. So, we could produce similar output using this example:

```python
x = 1
y = 2
print("Variable x:", x, ", Variable y: ", y)
```

which should output:

```tex
Variable x: 1 , Variable y: 2
```

Notice that there is an extra space after `1` in the output. This is because Python automatically adds a space between each argument provided to the `print()` method. So, we must be careful about our formatting using this method. 

We can also use the `format()` method in Python to include many variables in a single piece of text. We'll cover more about the `format()` method in a later chapter, but here's an example of how it could be used to create the desired output:

```java
x = 1
y = 2
print("Variable x: {}, Variable y: {}".format(x, y))
```

Inside of the text, we use curly brackets `{}` to denote where to place the variables. Then, we place a `.format` directly after the text, and inside of that method call we provide the variables we'd like to include in the text. The variables are included in the respective order they are given, so, in this example, `x` will be placed where the first curly braces `{}` are, and `y` will be placed where the second curly braces are. 

When we run this program, it will output:

```tex
Variable x: 1, Variable y: 2
```

Other languages allow us to use the plus `+` operator to _concatenate_, or join, two pieces of text together. Python also includes this feature, but it is much more restrictive. Let's look at an example:

```python
x = 1
y = 2
print("Variable x: " + x + ", Variable y: " + y)
```

When we try to run this program, we will get the following error:

![Python Implicit Conversion Error](/images/02-data/implicit.py.png)

That seems strange, doesn't it? It turns out that the Python interpreter tries its best to interpret whether the plus symbol should be used for addition and concatenation. Since the first operand is text, it assumes we'd like to do concatenation. However, the second operand is `x`, which is an `int` variable. Python does not automatically convert numerical variables to text (denoted as type `str`, short for _String_), and it doesn't know how to concatenate text and a number together. So, it gives us an error. 

To resolve this problem, we must convert our numerical variables to text, using the `str()` method to _cast_ those variables to the `str` data type. So, we must modify the example above to resemble this one:

```python
x = 1
y = 2
print("Variable x: " + str(x) + ", Variable y: " + str(y))
```

which will now output:

```tex
Variable x: 1, Variable y: 2
```

There are many ways that we can use Python to output text and variables as desired. We'll use some of these methods to complete this project. 
