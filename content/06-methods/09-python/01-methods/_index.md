---
title: "Methods"
pre: "1. "
weight: 10
---

{{% youtube 4TFFHCkDi-c %}}

[Video Materials]({{<relref "./video">}})

<!-- TODO Update Video -->

Now that we've covered the basic ideas of adding methods to our programs, let's see how we can do that using the Python programming language.

## Defining Methods

In general, a method definition in Python needs a few elements. Let's start at the simplest case:

```python
class Example:
    
    @staticmethod
    def foo():
        print("Foo")
        return
```

Let's break this example method definition down to see how it works:

1. First we note that in object oriented programming, all methods go inside (belong to) a class definition.
1. Next we use the decorator `@staticmethod`--this tells the Python interpreter how we intend to access this method.  Static methods are not really a Pythonic or object oriented way of doing business.
1. Then, we use the keyword `def` at the beginning of this method definition. That keyword tells Python that we'd like to _define_ a new method. We'll need to include it at the beginning of each method definition.
1. Next, we have the name of the method, `foo`. We can name a method using any valid identifier in Python. In general, method names in Python always start with a lowercase letter, and use underscores between the words in the method name if it contains multiple words. Inside a class definition, each method name <b>must</b> be unique.
1. Following the method name, we see a set of parentheses `()` that list the parameters for this method. Since there is nothing included in this example, the method `foo` does not require any parameters.
1. We see a colon `:` indicating that the indented block of code below this definition is contained within the method. A method body (like every other statement body in Python) must be indented.  
1. In this case, the method will simply print `Foo` to the terminal and ends with the `return` keyword. Since we aren't returning a value, we aren't required to include a `return` keyword in the method. However, it is helpful to know that we may use that keyword to exit the method at any time.

We'll cover how to handle method parameters and return values later in this module. For now, we'll just look at creating simple methods that neither require parameters nor return values. 

**Reference**: [Python Style Guide: Function and Variable Names](https://peps.python.org/pep-0008/#function-and-variable-names)

## Calling methods

When used in a object oriented implementation, the general form for calling a method is

<p style = "font-size:150%; text-align: center">&lt;source&gt;.&lt;method()&gt;</p>

where source could be
| source| meaning|
|-------|--------|
|<br>blank| Look in built in functions or imported functions(not modules)<br>In this case the dot ('.') is omitted|
|Class name| Look in the class for a @staticmethod or @classmethod|
|object variable| Look in the object's class for an instance method|

Previously, and for this module, we have used 'blank', as when we call the built in function `print()` and &lt;class&gt;, as when we call `main()` from the main guard.


```python
Example.foo()
```

We simply use the name of the method, followed by parentheses, wherever we'd like to call that method. Again, we'll see how to pass arguments to the method and store the return value later in this module. 

{{% notice note "Static Methods" %}}

For simplicity, all methods in this module will be `@staticmethod`s.  The next module will discuss the differences between `@staticmethod`, `@classmethod`, instance and module methods.

{{% /notice %}}

## Example

Let's look at a complete sample program to see how this all fits together.

```python
import sys

class Function:
    
    @staticmethod
    def main(args):
        print("Main 1")
        Function.foo()
        print("Main 2")
        Function.foo()
        print("Main 3")
        
    @staticmethod
    def foo():
        print("Foo 1")
        
if __name__ == "__main__":
    Function.main(sys.argv)
```

When we run this program, we should see the following output:

```tex
Main 1
Foo 1
Main 2
Foo 1
Main 3
```

We can also look at a flowchart diagram of this program to help understand how it works:

![Method Call Flowchart Python](/images/06-method/10.10.p.1.functioncallpython.png)

As we can see in this diagram, the program starts in the main part of the script, which is any code not included inside of a class. So, it starts by calling Video's `main()` method.  This method prints `Main 1`, then calls the method `foo()`. Well technically it calls `Function.foo()`, but we will assume you can figure out the class name.

So, we can follow the dashed line over to `foo()`, where it will print `Foo 1` and return back to the main part along the same dashed line. Then, we'll print `Main 2` before calling `foo()` once again. This time, we'll follow the dotted line to `foo()`, where we'll once again print `Foo 1` before returning back to the main part of the script and printing `Main 3`. 

## Main Method and Main Guard

Unlike many other programming languages, Python does not require a method named `main()` by default. In languages such as Java, each program is required to include a method named `main()` to indicate where the program should begin. Instead, Python allows us to run code directly in a script without putting it inside a method. 

This is not Object Oriented(OO), and makes organizing a more complex program difficult^[the organizational difficulties of this type of procedural programming gave  rise to the invention and adoption of Objects].

In the _main guard_, we are using a special variable `__name__`, which stores the name of the current module being executed. As we'll see in a later chapter, we can import additional files into our programs, so the `__name__` variable inside of those modules will contain the name we used when importing the module. 

However, when a Python script is run directly in the interpreter, that topmost script is given the value `__main__` in the `__name__` variable. So, we can use a simple **If** statement to determine if that is the case. If so, we can then call our `main()` method. 

As an added bonus, this allows us to define a `main()` method in our class files, along with a _main guard_ to call the main method. By doing so, we can import that script as a module in other files, and Python will only "import" class, not run the program^[a typical OO project will have dozens of imported class files and usually only one class with a `main()` method]. 

{{% notice info "Why main()?" %}}

Technically, we can use any valid method in Python inside of our main guard, so we don't have to create a method named `main()` anywhere in our code. However, to maintain readability with other languages, most Python developers choose to use `main()` as the name of their main method. For this course, we'll follow the same standard.

{{% /notice %}}

## Try It!

Let's see if we can modify the program above, including `main()` and the main guard, to include a new method. For this exercise, create a new method named `bar()`, which should print `Bar 1` to the command line. Then, replace the second call to `foo()` in `main()` with a call to `bar()`. So, when put together, the program should print the following output:

```tex
Main 1
Foo 1
Main 2
Bar 1
Main 3
```

For this exercise, as well as many exercises later in this module and beyond, we'll use two grading tests to check our code. The first test will confirm that our code contains the correct methods. Then, we use the second test to confirm that the program itself works properly. So, we'll need to make sure we run the first test until everything is correct. Then, we can use the second test to check our output and make sure it works. 

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}