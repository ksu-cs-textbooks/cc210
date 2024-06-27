---
title: "Try-Except"
pre: "3. "
weight: 30
---

{{< youtube VRg7hkkY4iI  >}}

<!-- TODO Update Video? -->

[Video Materials]({{% relref "./video" %}})

Programs written in Python can have many exceptions occur on a regular basis. Thankfully, as we learned earlier, it is possible to detect and handle these exceptions in our code directly, in order to prevent our program crashing and causing the user more stress. Let's see how we can perform this step in Python.


Consider the following program, if provided a command-line argument, it treats that string as a file-name and opens it for reading.  If there is no command-lie argument, it defaults to keyboard entry.  It then attempts to get an input and convert that to an integer.

```python
import sys

class Try:
    
    @classmethod
    def main(cls, args):
        if len(args) > 1:
            reader = open(args[1])
        else:
            reader = sys.stdin
        x = int(reader.readline())
        print(x)
           
        
if __name__ == "__main__":
    Try.main(sys.argv)
```

## Try-Except

In Python, we use a **Try-Except** construct to detect and handle exceptions in our code. Let's look at a quick example, and then we can discuss how it works.

```python


try:
  if len(args) > 1:
    reader = open(args[1])
  else:
    reader = sys.stdin
  x = int(reader.readline())
  print(x)
    
except Exception as e:
  print("Error!")
```

First, we use the `try` keyword, followed by a colon `:` to begin a block of code. Below that, we indent any lines to be included in the `try` block. If any exceptions occur in the code indented below a `try` keyword, we can add `except` statements to handle that exception.

Directly following the `try` block, we must include at least one `except` statement. The `except` keyword is followed by the name of an exception that we'd like to catch. Optionally we can add the `as` keyword and the name of a variable to represent that exception. Finally, we include a colon `:` and indent a block of code below to act as the exception handler. 

In this example, we are just catching the generic `Exception` type, which will match any catchable exception. We'll see how we can detect specific exceptions in a later example. We can use the variable for the exception, in this case `e`, to access additional details about the exception we've detected. 

<p style="padding:10"><b>Note:</b> nearly every other language uses the syntax "try catch" instead of "try except". </p>

## Which Exceptions to Catch?

When writing code, it can sometimes be very difficult to even know which exceptions to expect from a particular piece of code. Thankfully, the [Python Documentation](https://docs.python.org/3/library/exceptions.html) includes quite a bit of information about the possible exceptions that could occur in a program.

Let's return to our earlier example. Here is the code contained in the `try` block:

```python
if len(args) > 1:
  reader = open(args[1])  
else:
  reader = sys.stdin

x = int(reader.readline())
print(x)
```

While this may look like a very simple few lines of code, there are actually several exceptions that could be produced here: 

* FileNotFoundError - if the file in `args[1]` is not valid
* NameError - if we forget to include `import sys` at the top of the file
* ValueError - if the input cannot be converted to an integer
* IndexError - `args[1]` could produce this exception, but we've already checked that the length is greater than 1, so it won't happen in practice.

When writing truly bulletproof code, it is a good idea to attempt to catch and handle all of these exceptions if possible. You can always refer to the official Python documentation for a list of exceptions that could occur. Unfortunately, Python does not do a great job of documenting which exceptions could be thrown by specific methods compared to Java. Later on in this chapter we'll discuss some best practices when it comes to detecting and handling exceptions in code. 

## Handling Multiple Exceptions

Of course, we can add multiple `except` statements after any `try` block to catch different types of exceptions. 

```python

try:
  # If an argument is present, we are reading from a file
  # specified in args[1]
  if len(args) > 1:
    reader = open(args[1])

  # If no argument, read from stdin  
  else:
    reader = sys.stdin

  x = int(reader.readline())
  print(x)

except FileNotFoundError as e:
  print("Error: File Not Found!")
except ValueError as e:
  print("Error: Input Does Not Match Expected Format!")
except OSError as e:
  print("Error: OS Exception!")
```

In the example code above, we see three different `except` statements, each of which will handle a different type of exception. When an exception occurs in the code contained in a `try` block, the Python interpreter will create the exception, and then it will search for the first handler that matches. So, it will begin with the first `except` statement, and see if the exception created matches the type of the exception in parenthesis. If so, it will execute the code inside of that `except` block. If not, it will continue to the next `except` statement. If none of the `except` statements match the exception, then it will be _thrown_ and cause the program to stop executing. 

## Exception Hierarchy

The exceptions in Python form a hierarchical structure, meaning that an exception may match multiple types. For example, all exceptions that programs can catch are based on the generic Exception type. So, FileNotFoundError and IndexError would both match the Exception type. 

In addition, many exceptions are descended from the OSError type. For example, FileNotFoundError is based on OSError, which itself is based on the Exception type. So, a FileNotFoundError would match any of those three types of exceptions. It can make things a bit tricky!

So, how can we know what types of exceptions we are dealing with, and what the hierarchy is? Thankfully, the [Python Documentation](https://docs.python.org/3/library/exceptions.html#exception-hierarchy) contains information about most possible exceptions, including the entire hierarchy of those exceptions. 

For example, here is a screenshot from the [Python Documentation](https://docs.python.org/3/library/exceptions.html#exception-hierarchy) page showing the hierarchy of OSError:

![OSError Hierarchy](/images/10-except/8.7.p.3.filenotfound.png)

Because of this, we must be careful about how we order the catch statements. In general, we want to place the more specific exceptions first (the ones further down the hierarchy), and the more generic exceptions later. 

Let's look at an example of poor ordering of exception handlers:

```python

try:
  # If an argument is present, we are reading from a file
  # specified in args[1]
  if len(args) > 1:
    reader = open(args[1])

  # If no argument, read from stdin  
  else:
    reader = sys.stdin

  x = int(reader.readline())
  print(x)

except OSError as e:
  print("Error: OS Exception!")
except FileNotFoundError as e:
  print("Error: File Not Found!")
except ValueError as e:
  print("Error: Input Does Not Match Expected Format!")
```

In the code above, we are catching the OSError first. So, if the code produces a FileNotFoundError, it will be caught and handled by the first `except` statement, since FileNotFoundError is also an OSError. Therefore, we wouldn't want to order our `except` statements in this way.

## Try It!

Let's see if we can write a very simple program to catch and handle a few common exceptions. Here's some starter code for `main`'s:

```python

if len(args) > 1:
  reader = open(args[1])
else:
  reader = sys.stdin

x = int(reader.readline())
y = int(reader.readline())
z = x / y

print(z)
```

For this example, place this starter code in `Try.py`, open to the left, and modify it to catch and handle the following exceptions by printing the given error messages:

* FileNotFoundError - print "Error: File Not Found!"
* ValueError - print "Error: Input Does Not Match Expected Format!"
* ZeroDivisionError - print "Error: Divide by Zero!"

Any other exceptions can be ignored.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}
