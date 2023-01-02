---
title: "Parameters"
pre: "2. "
weight: 20
---

{{% youtube imqklu8DFR8 %}}

[Video Materials]({{<relref "./video">}})

<!-- TODO Update Video -->

<p style="font-size:120%;color:red;padding:25">Note this video uses Python in a procedural style, and thus omits the class name from function calls.</p>

Methods are a very useful way to divide our code into smaller chunks. However, many times we need to provide input to our methods. This allows us to reuse the same code, but with different values each time we call the method. So, let's review how to add _parameters_ to our methods in Python.

## Method Parameters

In Python, we can add parameters to a method definition by placing them in the parentheses `()` at the end of the definition. Each parameter is similar to a variable definition, requiring just a new identifier. We can also define multiple parameters, separated by commas `,`. 

For example, let's extend our definition of `foo()` from the previous page by adding a parameter named `message`:

```python
class Parameters:
    @staticmethod
    def foo(message):
      print("Message: {}".format(message))
```

Then, when we call that method, we must provide an argument by writing it within the parentheses in the method call:

```python
Parameters.foo("Hello World!")
```

## Another Example

Here's another example. In this case, we are writing two methods, `foo()` and `bar()`. They accept multiple parameters, and in `main()` we call each method using arguments for each parameter.

```python
class Parameters:
    def main():
        x = 5
        y = 10
        z = 8
        Parameters.bar(x, y, z)
        Parameters.foo(y, True)
      
    def foo(output, long_message):
        if long_message:
              print("The value was {}".format(output))
        else:
              print("Val: {}".format(output))
        
    def bar(a, b, c):
        print("{}, {}, {}".format(a, b, c))
      
# main guard
if __name__ == "__main__":
    Parameters.main(sys.argv)
```

First, let's look at `bar()`. When we call this method from `main()`, we are using `x`, `y`, and `z` as arguments. So, inside of `bar()`, the value stored in `x` will be stored in `a`, `y` will be stored in `b`, and `z` will be stored in `c`. The parameters and arguments are matched up based on the order they are provided to the method call. So, `bar()` will output `5, 10, 8` when it is called with those parameters.

However, since Python is not a statically typed language, we may not know which data type is expected to be provided for each parameter of a method. So, as developers, we'll have to be careful and either make sure we are using the correct types.

{{% notice note "Writing Reader Friendly Code" %}}

Python is an implicitly and dynamically typed language.  As such it is not necessary (or for that matter possible) to specify what types of parameters must be passed to your method.  However, it is possible to provide hints.  

The method `foo` above could alternately have been defined by the line `def foo(output: str, long_message: bool):`.  This is a form of documentation, that like comments, can assist readers in understanding your intention without altering how the program runs.

The syntax is
```
def <method_name> (<parameter_name>:<parameter_type>, ...) : 
```
Sometimes the name will be omitted, `def foo(: str, : bool):`.

{{% /notice %}}

{{% notice warning "Don't Type Check in Python" %}}

<b>IT IS EXTREMELY NOT PYTHONIC</b> to "type check" you parameters.  The following code would be considered bad form.  The built in function `isinstance(a,b)` returns `True` if a is the "same" type as b.

```
def foo(output, long_message):
    if not (isinstance(output,str)) or not (isinstance(long_message, bool)):
         raise ValueError()
    if long_message:
        print("The value was {}".format(output))
    else:
        print("Val: {}".format(output))
```

Python takes a "user beware" approach to calling methods.   If a programmer passes the wrong kinds of arguments, they get what they get.

{{% /notice %}}

## Try It!

Let's see if we can write our own methods with parameters. For this exercise, we want to write a program that contains the following three methods:

Write a class `Parameters` in Parameters.py.  Include in `Parameters` the following static methods (@staticmethod):
1. `main(args: list)` - a main method, just like we saw on the previous page. It should include method calls to `foo()` with `5` as a parameter, and `bar()` with `"Hello"` and `2` as parameters. 
2. `foo(: int)` - this method should accept a single integer parameter. Then, it should print that number of periods `.` to the terminal, all on the same line, adding a newline at the very end. If the parameter is 0 or negative, don't print anything.
3. `bar(: str, :int)` - this method should accept two parameters, a string and then an integer. It should print the string the number of times indicated by the integer parameter, once per line. Again, if the integer parameter is 0 or negative, don't print anything. 

You'll also need to include a _main guard_ at the bottom of our file, passing in the command line inputs. 

Once again, we'll use two grading tests to check our code. The first test will confirm that our code contains the correct methods. Then, we can use the second test to confirm that the program itself works properly.

{{% notice info "Debugging" %}}

Recall, to continue printing on one line the command is `print("string", end ="")`. To move to the next line `print()`.  Thus:

```python
print("a", end = "")
print("a", end = "")
print("a", end = "")
print()
print("b", end = "")
print("b", end = "")
print("ac", end = "")
print()
```

prints 

```tex
aaa
bbac
```
and leaves the terminal prepared to start printing on the next line.

{{% /notice %}}

<p style="font-size:120%;color:red;padding:25"><b>Note:</b> From this point forward, we may test your methods individually and in concert (together).  It is necessary but not sufficient for your programs to "print the right thing".  Your classes and methods must be structured and work as specified.</p>

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}