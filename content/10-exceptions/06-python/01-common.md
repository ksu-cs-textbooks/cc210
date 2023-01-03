---
title: "Common Exceptions"
pre: "1. "
weight: 10
---

Before we learn about how to detect and handle exceptions in Python, let's review some of the common exceptions and errors we may see in our programs. Each of the headers below is the name of an exception in Python, which is represented by a particular class in the Python programming language. 

## Exception

Every exception that can be handled in Python is a subtype of the Exception class. So, when we aren't sure which type of exception to expect, we can always use the Exception class to make sure we catch all of them.

## ArithmeticError

An ArithmeticError can occur whenever our program attempts to perform a calculation that would result in an error. This is the base class for various other errors, such as OverflowError and ZeroDivisionError

## OverflowError

An OverflowError occurs when the result of a calculation cannot be represented correctly. Typically this exception is very rare, but can happen when working with older code or libraries.

## ZeroDivisionError

A ZeroDivisionError is thrown whenever the program is asked to either divide by $0$ or perform the modulo operation with $0$ as the second input. Here's an example:

```python
x = 5 / 0 # throws ZeroDivisionError
y = 3 % 0 # throws ZeroDivisionError
```

## IndexError

An IndexError happens when we try to access an array index that does not exist. Here's a great example:

```python
array = [1, 2, 3, 4, 5]
array[5] = 10 # throws IndexError
```

In this example, we are trying to access the 6th element in the array, which is at array index 5. However, since the size of the array is only 5, we'll get an IndexError when we try to execute this code since there is no 6th element.

## NameError

In Python, a NameError occurs when we try to use the name of a variable, class, or other item which Python can't find. For example:

```python
x = 5 + y # throws NameError
```

In this code, we are trying to use the variable `y` without first giving it a value. When we execute this code, it will throw a NameError. 

## FileNotFoundError

This exception occurs when the program is trying to open a file that does not exist. This is one of the more common errors that programmers must deal with when using files for input, and it is relatively simple to correct. In most cases, we can simply ask the user to provide another file. Here's an example of some code that may cause this exception:

```python
filename = ""
reader = open(filename) # throws FileNotFoundError
```

In this case, we are providing a blank filename, which causes the program to throw a FileNotFoundError. 

## TypeError

A TypeError occurs when we try to use a variable in a way that is not allowed based on the type of the variable. We've probably already seen this exception many times when working with string outputs. Here's an example:

```python
x = 5
print("Number: " + x) # throws TypeError
```

In this code, we are using the plus `+` operator to concatenate two strings together. However, the second variable, `x`, is an integer, so it is not the correct type for this operation. Therefore, the code will produce a TypeError when executed. 

## ValueError

A ValueError typically occurs when an input to a method is an acceptable type but has an incorrect value. Here are a couple of examples:

```python
x = int("12.3") # throws ValueError
y = float("abc") # throws ValueError
```

In both of these examples, the `int` and `float` methods are provided with the correct type of input, a string. However, neither of those strings can be converted to the corresponding type, so a ValueError is thrown. 

## AssertionError

[Python Assertions](https://docs.python.org/3/reference/simple_stmts.html#the-assert-statement)

An AssertionError happens when our code reaches an _assertion_ that fails. An assertion is a check added by the programmer to verify that a particular situation doesn't occur in the code, such as a variable being negative or an array being too large. Python supports the use of a special keyword `assert` that can be used to add these assertions to our code. By default, the Python interpreter enforces all `assert` statements, but they can easily be disabled by adding `-O` as an argument to the `python3` command when running a program. This is a helpful step when debugging a new application. We'll learn more about assertions and how they can be used effectively in a later chapter.

For now, here's a quick example of an assertion that would produce an AssertionError:

```python
x = 5
y = 3
assert x + y < 7 # throws AssertionError if enabled
```

## Errors

Beyond exceptions, there are a few unrecoverable errors that may occur in our Python code. Recall that errors are special types of exceptions that should not be handled by our programs, and should instead be allowed to cause our programs to crash. Some examples are:

* SyntaxError - occurs when the Python interpreter finds code with invalid syntax
* IndentationError - occurs when the Python interpreter  finds improperly indented code
* SystemError - occurs when the Python interpreter encounters an internal error

Since Python is an interpreted language, these errors will occur when code is running, sometimes even after most of the program is executed. In general, we should not try to catch or correct these errors in our code. Instead, we should allow our program to crash, knowing that we'll have to fix the underlying source code to solve the problem.

### References:

* [Built-in Exceptions](https://docs.python.org/3/library/exceptions.html)
* [Tutorial: Errors and Exceptions](https://docs.python.org/3/tutorial/errors.html)
