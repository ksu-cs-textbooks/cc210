---
title: "String Formatting"
pre: "4. "
weight: 40
---

{{% youtube c2aaTbTUfY0 %}}

[Video Materials]({{<relref "./video">}})

There are also a couple of different approaches we can take to formatting output strings in Python. Let's take a minute to review both of those and see how they work.

## Concatenation

We've already seen this approach in several programs in this course. In effect, we can simply build an output string by concatenating strings and the variables we'd like to include in those strings. 

For example, if we'd like to create an output string that gives both the sum and the average of a set of numbers, we could do something like this:

```python
sum = 123
avg = 1.23

print("The sum is " + str(sum) + " and the average is " + str(avg) + ".")
```

In this code, we are using the plus symbol `+` to concatenate strings together into a single output string. In Python, we'll need to use the `str()` method to convert variables of any other data types into strings. In many cases, this may be the simplest way to create output in Python. 

## Formatted Strings

Python also includes a special string method, the `format()` method, which allows us to use _placeholders_ in our output string, and then replace those placeholders with the values stored in variables. 

Here's an example of how to use that method in Python:

```python
sum = 123
avg = 1.23
name = "Student"

output = "{}: Your score is {} with an average of {}."

print(output.format(name, sum, avg))
```

When we run this program, the output will be:

```tex
Student: Your score is 123 with an average of 1.23.
```

In the variable `output`, we are using curly braces `{}` as _placeholders_ in the string. Those curly braces will be replaced by the inputs to the `format()` method. So, for example, the first set of curly braces will be replaced by the first input, in this case the `name` variable. The same thing happens for the other two sets of curly braces and inputs.  

In addition, many of the placeholders can also specify the _width_ and _precision_ of each output. Here's an updated example using these formatting options:

```python
sum = 123
avg = 1.23
name = "Student"

output = "{}: Your score is {:5} with an average of {:8.4f}."

print(output.format(name, sum, avg))
```

When we run this program, we'll see the output is now this:

```tex
Student: Your score is   123 with an average of   1.2300.
```

So, what happened? First, we updated the second placedholder to `{:5}`. This means that we want the output of that variable to have a width of 5. Since the `sum` variable would only have 3 characters, the `format()` method adds two additional spaces in front of the number. 

Secondly, we updated the last placeholder to `:8.4f`. Once again, the number 8 is used to give the width of the output. In addition, we added a 4 after a decimal point to indicate how many characters we'd like to include after the decimal point in the output. Finally, we include the character `f` at the end, which tells Python that we want to convert whatever variable is provided to a floating point number. So, the total output is `  1.2300`, which includes four characters after the decimal place, and an additional two spaces in the front. All told, the output is 8 characters in length, including the decimal point.

There are many more ways that a formatted string can be used to create output that meets our needs. We can find more information on using the placeholders and associated settings by reading the official Python documentation linked below.

### Reference

[Python Format String Syntax](https://docs.python.org/3/library/string.html#format-string-syntax)
