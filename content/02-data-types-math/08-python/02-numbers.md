---
title: "Numbers"
pre: "2. "
weight: 20
---

Most of the computer programs we'll write must deal with numbers in some way. So, it makes perfect sense to start working with the numerical data types, since we'll use them very often. Let's dive in and see how we can use these numerical data types in Python!

Python has several built-in classes for representing numbers, text and logical values.  All Python variables thus refer to full fledged objects.

## Integers

The first data type we'll learn about in Python is the one for storing whole numbers, called `int` class. In Python, any whole number without a decimal point is considered to be an `int` by default, and the only limit on the size of the number is the amount of memory available on our system. So, Python is great at storing even very large numbers!

## Floating Points

To store a floating point number in Python, we'll use the `float` type. Python uses a 64-bit "double-precision" format to store this number, which is very similar to the `double` data type in many other languages such as Java. Any literal followed by a decimal, or in scientific notation is interpreted as a `float`.  The table below shows different inferred types for various ways to write one hundred.

|literal| inferred Type|
|-------|--------------|
|100| int|
|100.| float |
|1E2| float |

It is difficult to discuss the minimum and maximum value for this data types, as it requires a thorough understanding of how it is stored in binary and interpreted by the processor in a computer. In general, a `float` in Python can handle values in the range of {{< math >}}$  \pm 10^{\pm 308}  ${{< /math >}}. 

However, just like scientific notation, the numbers it stores can at best be only as accurate as the number of digits it holds. So, when storing an extremely large number, there will be some rounding error.

## Using Numbers in Code

Now that we've discussed the various data types available in Python, let's look at how we can actually create variables that can store data in our programs. 

### Creating a Variable

To create a variable in Python, we must simply give it a name and assign it a value, using a syntax similar to this:

```tex
<identifier> = <expression>
```

In that example, `<identifier>` is any valid identifier that can be used as a variable name in Python, and `<expression>` is any valid Python expression that produces a value. It could be a number, another variable, a mathematical operation, or even a method call, which we'll learn about in a later chapter. The variable we are storing the value in must always be on the left side of the equals `=` sign. 

{{% notice info "Identifier Rules & Conventions" %}}

Python has rules about the allowable names with can be used as identifiers.  Basically an identifier can start with any upper or lower case letter, or the underscore `_`.  You may use any combination of uppercase letters, lowercase letters, underscores and numbers after the first position.  The actual rule is located [here](https://docs.python.org/3/reference/lexical_analysis.html), but may be a bit too technical at this point.

By convention, variable names should be descriptive and use snake_case to aid in reading.  Variables starting with the underscore character convey special meanings.  Avoid starting with `_` for now.

{{% /notice %}}

For example, if we want to store the integer value {{< math >}}$ 5 ${{< /math >}} in a variable named `x`, we could write the following:

```python
x = 5
```

The same syntax applies to floating point numbers:

```python
y = 1.2
```

When assigning values from one variable to another using primitive data types, the value is _copied_ in memory. So, changing the value of the first variable would not affect the others, as in this example:

```python
x = 5
y = x
x = 6
```

At the end of that code, the value of `x` is {{< math >}}$ 6 ${{< /math >}}, but `y` still contains {{< math >}}$ 5 ${{< /math >}}. This is important to remember.

{{% notice tip "Try It!" %}}

See if you can create a variable using each of the data types listed above in `Types.py`! Can you find any values that cause errors? 

{{% /notice %}}

### Printing

We can also use the `print` method we learned earlier to output the current value of a variable to the screen. Here's an example: 

```python
x = 5
print(x)
```

Notice that the variable `x` is not in quotation marks. This way, we'll be able to print the _value_ stored in the variable `x` to the screen. If we place it in quotation marks, we'll just print the letter `x` instead. 

Later, in the project for this chapter, we'll learn how to combine multiple variables into a single output. 

### Determining Type

Python includes a special method, `type()`, that can be used to determine the type of a variable. Here's an example of how it could be used:

```python
x = 5
y = 1.2
print(type(x))
print(type(y))
```

{{% notice tip "Follow Along" %}}

Try to run these examples by placing each one in `Types.py` and seeing what happens. Does it work? Try it before reading the answers below. 

{{% /notice %}}

When we run that program, we should see the following output:

![Python Type Method](/images/02-data/2.6.p.2.type.png)

In the output, we can see that variable `x` is of type `int`, and variable `y` is of type `float`. This is exactly as we'd expect, since `x` is a whole number and `y` is a rational, or floating point, number. 

### Casting

When writing our programs, sometimes we need to change the data type that a particular value is stored as, especially when we want to store it in a new variable. Ideally, we would construct our programs to avoid this issue, but in the real world we aren't always so lucky.

To change the data type of a value, we can _cast_ that value to a different data type. To cast a value to a different data type, we can use special methods that are named after each data type. 

Let's look at the example below:

```python
x = 1.7
y = int(x)
print(y)
print(type(y))
```

In this example, we've created a `float` variable `x`, and stored {{< math >}}$ 1.7 ${{< /math >}} in that variable. We then create a new variable `y`, and convert the value in `x` to an `int` before storing it in `y`, using the `int()` method. When we run this program, we'll see the following output:

![Python Cast Method](/images/02-data/2.6.p.2.cast.png)

As expected, `y` is a variable of type `int`. However, we notice that the value stored in `y` is {{< math >}}$ 1 ${{< /math >}}. This is because the `int()` conversion method will _truncate_, or remove, the decimal portion of the number. 

In general, we should write our programs carefully so that we avoid ever needing to convert the type of a variable. However, in practice, it is sometimes necessary to do so. 


{{% notice info "Cast vs. Convert" %}}

Technically `float()`, `int()` and later `str()` **convert** their argument (the value in the parentheses) into the appropriate type.  Where necessary the binary representation of the is changed.  Conversion preserves the semantics (meaning) but over writes the binary.

**Casting** using the `.cast()` method preserves the original binary but may result in gibberish; you lose the meaning.  

However, "casting" is nearly always used to mean "convert".  It comes from the origins of programming, where languages supported fewer types and the binary had the same semantic meaning across multiple data types.

<table>
    <tr><th>type</th><th>bytes</th><th>binary for the value of 2</th></tr>
    <tr><td>byte</td><td>1</td><td>00000010<td></tr>
    <tr><td>short</td><td>2</td><td>0000000000000010<td></tr>
    <tr><td>int</td><td>4</td><td>00000000000000000000000000000010<td></tr>
</table>

From the above table we can see how casting might work for various sized integer values. Leading "bits" were ignored when casting to a byte-wise smaller type.  Leading 0s were adding when casting to larger type.

We will use cast and convert interchangeably in this course to mean convert to the desired data type.

{{% /notice %}}