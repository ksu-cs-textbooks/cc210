---
title: "Best Practices"
pre: "7. "
weight: 70
---

Now that we've seen lots of information about how to throw, catch, and handle exceptions in Python, it is a great time to discuss some of the best practices we can apply in our code to make it as readable and bulletproof as possible. While these aren't strict rules that must be followed all the time, they are great things to keep in mind as we write code that deals with exceptions.

## Leave No Exception Unhandled

As much as possible, we should write our code to handle any exception we can reasonably expect our users to run into when using our programs. We cannot assume that users will always provide the correct input in the correct format, and a single typo by a user should not cause our entire program to crash.

Instead, we should always use **Try-Except** statements whenever possible to detect and handle those errors as simply as possible. In addition, if the program is interactive, we can combine that approach with the use of loops to prompt the user to provide new input to resolve the error. 

{{% notice info "Don't Substitute Unchecked Exception Handling for Value Checking" %}}

You can go "try except" crazy.  Exception handling is powerful, but also slow, really really slow. 

You can write something like 

```
try:
    ratio = x / y
except ZeroDivisionError as e:
    print("Cannot divide by zero")
```
but 
```
if y !=0:
    ratio = x / y;
else:
    print("Cannot divide by zero")
``` 
executes a lot more efficiently.

Many exceptions can be avoided through value checking.  In this course, we may direct you to throw and catch exceptions of this type for practice in exception coding.

{{% /notice %}}

The [Python Documentation](https://docs.python.org/3/) is an okay resource to determine which exceptions could be thrown by any methods used in our code.  However Python does not provide a standard or comprehensive list of the Exceptions and conditions which cause them for all methods in all modules--nor is their enumeration in the Python Docs in a standard place or format.

## Dp Not Use Exception Handling for Control Flow

You might be tempted to do something like this

```python
try:
    reader = open(sys.argv[1])
except Exception:
    reader = sys.stdin 

```

Where if there is any problem accessing sys.argv[1] as a file, such as it was not provided or it does not exist, you just use the keyboard.  Here you are letting an exception control what is happening without telling the user there was a problem.   Better would be

```python

if len(sys.argv) > 1:
    try:
        reader= open(sys.arv[1])
    except OSError:
        print ("there was a problem accessing {}, please check the file and try again".format(sys.argv[1]))
        return # here we assume this will exit the program
else:
    reader = sys.stdin
```

Programmers do not expect control flow decisions to be made <b>in</b> exception-handlers.  It makes analysis of the program very difficult.

## Be Specific

We should also always strive to use specific exceptions in our `except` statements whenever we can. So, if we are opening a file, we should include an `except` statement for a FileNotFoundError, and not just a single generic `Exception`. Even though this means we may have to include several `except` statements, it is much better in the long run because it allows us to know exactly what happened when our code has a problem.

In addition, we should always make sure we catch the most specific exceptions first, before any more generic exceptions. As we saw earlier, if we try to catch an OSError before a FileNotFoundError, we won't be able to tell when we've reached a FileNotFoundError at all, since it is a subtype of the OSError.  

## Use Messages and Stack Traces

The Python Exception class includes some very helpful methods we can use to get additional information when we encounter an exception. 

Here's an example to show what we can learn:

```python
import sys
import traceback

try:
  x = 5 / 0
except ZeroDivisionError as e:
  print("Error! Trying to Divide by Zero!")
  traceback.print_exc(file=sys.stdout)
```

When this code is executed, it will produce the following output:

```tex
$ python3 8p-except/StackTrace.py
Error! Trying to Divide by Zero!
Traceback (most recent call last):
  File "8p-except/StackTrace.py", line 5, in <module>
    x = 5 / 0
ZeroDivisionError: division by zero
```

On the first line, we are printing our own error message. Below that, we are using `traceback.print_exc(file=sys.stdout)` to print a full stack trace showing the location of the error in code. In this example, we included `file=sys.stdout` because the method will print to `sys.stderr` by default, a different output stream. This just makes it easier to see all of our output on the terminal for now. 

In general, it is best to only show a short error message to users, but in some cases it may be better to add our own message. The text "division by zero" isn't very clear, even to developers. Instead, we could say "Error: divisor cannot be zero" to make the error message clearer.

The information contained in the stack trace is very helpful to developers when trying to debug and fix problems in the code, but that information is very confusing to users. As we learn how to build more advanced programs, we'll see how to record and log those error messages and stack traces for debugging, but hide them from our users. 

To see what other methods are available, refer to the [Traceback](https://docs.python.org/3/library/traceback.html) library in the Python documentation. 

## Don't Ignore Exceptions

Another big problem is that many developers tend to catch exceptions, only to ignore them so their program doesn't crash. Here's a quick example:

```python
import sys

x = 0
reader = sys.stdin
try:
  x = int(reader.readline())
except Exception as e:
  pass
  # do nothing
```

In this code, if the user inputs something that can't be converted to an integer, the code just silently ignores the exception and proceeds with `x` still storing the value $0$. While that may not cause issues, it can also make it very frustrating to debug later issues or changes in this program. So, it is always best to output an error message when an exception occurs, even if it can be easily ignored without additional input from the user. This will make it easier to debug additional issues later on in development. 

## Bulletproof Code

Here's a simple program that asks the user for input, and will repeat the question until a valid input is received. This code is designed to handle many common situations and exceptions:

```python
import sys
import traceback

x = 0

try:
  with open(sys.argv[1]) as reader:
    while x <= 0:
      try:
        x = int(reader.readline())
        if x <= 0:
          print("Error: Negative Integer Detected!")
      except ValueError as e:
        print("Error: Integer Not Found!")
      except Exception as e:
        print("Error: Unknown Input Error")
        sys.exit() # probably can't recover, so stop executing

  print("the file contained {}".format(x))

except FileNotFoundError as e:
  print("Error: Unable to File Open Reader!")
except Exception as e:
  print("Error: Unable to File Open Reader!")

```

There are several items in this code that help make it very bulletproof:

1. First, the program uses a **Try-Except** statement containing a **With** statement to make sure that the file will be properly closed when we are done with it. As we've discussed, this is a good practice when handling input via files, but really any input object can be handled in this way.
2. The outer **Try-Except** statement has a two `except` blocks.  The first handles not finding the file (the most likely exception).  The second captures anything else that might go wrong with the reader . 
3. Inside of the **While** loop, there is a second **Try-Except** statement to handle errors that come from reading an individual input, such as a ValueError. 
4. In addition, that inner **Try-Except** statement will also catch any generic Exceptions that might occur when reading input. In that case, we use the `sys.exit()` method to stop executing the program, since it may be difficult to continue to read input in that case. Thankfully, since we are using a **With** block, the reader will be correctly closed for us automatically. In addition, any `finally` blocks would be executed before the program stops. 

{{% notice warning "Don't Exit Early!" %}}

We have not discussed the `sys.exit()` method yet, but you may have come across it while reading code online. In Python, the `sys.exit()` method is used to exit the Python interpreter safely from within a program

For now, if we find that we need to exit our program when handling an error, we can safely use the `sys.exit()` method as shown in the example above. It will make sure that any `finally` blocks and **With** statements are executed properly. 

There are some other ways to exit the Python interpreter that you can find online, but they may do so without properly closing any resources or executing `finally` blocks. They can also make your code much more difficult to maintain and test. This can be very dangerous!

{{% /notice %}}

Of course, there are many things that can be done differently in this code, depending on our preferences and how we'd like our program to function. This is just one possible way to build useful code that handles several exceptions.