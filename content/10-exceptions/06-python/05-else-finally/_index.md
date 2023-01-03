---
title: "Else & Finally"
pre: "5. "
weight: 50
---

{{% youtube L7hep4SmBpo %}}

[Video Materials]({{<relref "./video">}})

When dealing with exceptions in our code, sometimes we have an operation that must be executed, even if the earlier code throws an exception. In that case, we can use the `finally` keyword to make sure that the correct code is executed. In addition, we may have an operation that should only happen if there are no exceptions in the previous code. For that, we can use the `else` keyword.

## Finally

To understand how the `finally` keyword works, let's take a look at an example:

```python
import sys

reader = sys.stdin

try:
  x = int(reader.readline())
  if x < 0:
    raise ValueError("Input must be greater than 0!")
except ValueError as e:
  print("Value Error: {}".format(e))
finally:
  print("Finally Block")

print("After Try")
```

This program will read an integer from the terminal. If the integer is greater than or equal to 0, it will do nothing except print the "Finally Block" and "After Try" messages. However, if the input is less than 0, it will throw a ValueError. Finally, if the input is not a number, then a ValueError will also be thrown and handled. In each of those cases, it will also print the "Finally Block" message. 

Let's run this program a few times and see how it works. First, we'll provide the input "5":

```tex
$ python3 8p-except/Finally.py
5
Finally Block
After Try
```

Here, we can see that the code in the `finally` block always runs when the program is finished executing the statements in the `try` block.

Let's run it again, this time with "-5" as the input:

```tex
$ python3 8p-except/Finally.py
-5
Value Error: Input must be greater than 0!
Finally Block
After Try
```

Here, we can see that it prints the error message caused by the ValueError, then proceeds to the `finally` block. So, even if an exception is thrown while inside of the `try` block, the code in the `finally` block is **always** executed once the `try` block and any exception handlers are finished. 

Here's one more example, this time with "abc" as the input:

```tex
$ python3 8p-except/Finally.py
abc
Value Error: invalid literal for int() with base 10: 'abc\n'
Finally Block
After Try
```

Once again, we see that the code first handles the ValueError, and then it will execute the code in the `finally` block. 

In a later chapter, we'll learn more about how to use the `finally` block to perform important tasks such as closing open files and making sure we don't leave the system in an unstable state when we handle an exception. 

## Else

Python also allows the `else` keyword to be used with a **Try-Except** statement. It works similarly to the way Python handles the `else` keyword with loops. Let's look at an example:

```python
import sys

reader = sys.stdin

try:
  x = int(reader.readline())
  if x < 0:
    raise ValueError("Input must be greater than 0!")
except ValueError as e:
  print("Value Error: {}".format(e))
else:
  print("No Errors!")
finally:
  print("Finally Block")

print("After Try")
```

The code above is the same example used to demonstrate the `finally` keyword, but now there is an `else` block added. The code in the `else` block will be executed only if the entire code in the `try` block is able to execute without any errors or exceptions being raised. 

So, if we run this program with the input `5`, we'll get the following:

```tex
$ python3 8p-except/Finally.py
5
No Errors!
Finally Block
After Try
```

Since this program does not encounter any exceptions, the `else` block is executed immediately after the `try` block, but before the `finally` block. However, if we provide an invalid input, such as `-5`, the output will look like this instead:

```tex
$ python3 8p-except/Finally.py
-5
Value Error: Input must be greater than 0!
Finally Block
After Try
```

Since this program encountered an exception, the code in the `else` block is not executed. However, the code in the `finally` block is still executed, since it will happen regardless of the outcome of the `try` block.

Finally, it is possible to include an `else` block without a `finally` block if desired. The only rule is that the `else` block must come before the `finally` block, and both of them should be after any `except` blocks to handle exceptions. 