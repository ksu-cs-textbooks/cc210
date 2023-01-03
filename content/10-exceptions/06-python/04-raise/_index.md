---
title: "Raise"
pre: "4. "
weight: 40
---

{{% youtube WTo7Xdrg0Ec %}}

[Video Materials]({{<relref "./video">}})

Beyond catching exceptions, there are a few other important concepts to learn related to exceptions. Let's go over a couple of them.

## Raise

We can generate our own exceptions using the `raise` keyword. This allows us to create new exceptions whenever needed. Let's look at an example:

```python
import sys

class Raise:
    
    @classmethod
    def main(cls, args):       
        if len(args) > 1:
          reader = open(args[1])
        else:
          reader = sys.stdin
        x = float(reader.readline())
        y = float(reader.readline())
        if y == 0:
          raise ValueError("Cannot divide by zero")
        else:
          z = x / y
          print(z)
```

In this code, we are asking the user to input two floating point numbers. Then, we will output the first number divided by the second. However, we want to avoid the situation where the second number, the divisor, is $0$. Instead of causing a DivideByZeroError, we can use an **If-Then** statement and the `raise` keyword to send a ValueError instead. 

Following the `raise` keyword, we must create a new Exception. In this case, we are creating a new ValueError, but any of the exception types we've learned about so far will work the same way. Inside of the parentheses, we can provide a helpful error message to go along with this exception. 

## Try It!

Let's see if we can use these keywords in another example. We'll start with this code in `main()`:

```python

if len(args) > 1:
  reader = open(args[1])
else:
  reader = sys.stdin


```

Place this code in `Raise.py` and modify it to do the following:
1. If the user provides an invalid file name in the arguments array, it should throw a FileNotFoundError. 
2. It should read a single string of input from the user. To make this simple, don't forget to use the `strip()` method to remove any extra whitespace and trailing newline characters!
3. If the string does not begin with a capital letter, it should throw a new ValueError that contains the error message "Proper Capitalization Required!"
4. Of course, if the string is empty, it should throw an IndexError with the message "String is Empty!" when it tries to access the first character of the string. 
5. Otherwise, it should print the string to the terminal. 

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

### Passing Back Text

The construct `raise <exception>(<string>)` returns an `<class:ValueError>` object.  Like all objects it has a `__str__` method that is called when `print`ed or used with `str()`.  The value returned is by `str()` is `<string>`.

```python
try:
    raise ValueError("demo")
except ValueError as e:
   print(type(e)) # <class 'ValueError'>
   print(e)       # "demo"

```

This behavior is convenient when a single type of exception can be triggered by different causes.  Each `raise ..`  can have a different explanatory string or error message.
