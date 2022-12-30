---
title: "Variable Scope"
pre: "3. "
weight: 30
---

Now that we've learned how to create new code blocks in our programs using constructs such as the **If** and **If-Else** statements, we must take a minute to discuss one concept related to those code blocks.

The _scope_ of a variable refers to the possible areas in a program's code where that variable can be accessed and used. This is very important to understand once we begin introducing additional code blocks in our programs, because it can affect where we can access those variables. 

{{% notice info "Python Variable Initialization" %}}

When a variable in Python is created, we say that it is _initialized_. So, a line of code like this:

```python
x = 5
```

is a _variable initialization_ if that is the first time the value `x` has appeared in our code. Some other languages include _variable declarations_ that work in a similar way, so we may see that term used as well.

When discussing variable scope, it is important to know where the variable is _initialized_ in the code. So, we'll see this term used often in this section. 

{{% /notice %}}

## Variable Scope in Python

In general, Python follows these rules when determining if a global variable is accessible.

1. A variable in Python **may not** be accessed before it is first initialized. 
1. A variable in Python **may** be accessed outside of the code block in which it is initialized, provided that the code was executed.
1. A variable in Python **may** be accessed inside of any code blocks placed inside of the code block in which is initialized.

Later on in this course we'll learn about class member variables and local variables, which have some different rules that govern their scope. For now, we'll only worry about global variables, which are variables initialized outside of a class or method in Python. 

### Accessing Before Declaring

Let's look at a few examples for each rule. First, a variable may not be accessed before it is initialized. So, we cannot do the following:

```python
print(a)
a = 5
print(a)
```

If we do, the interpreter will output an error similar to the following:

```tex
NameError: name 'a' is not defined
```

Instead, we must make sure the variable is initialized before it is accessed, as in this correct example:

```python
a = 5
print(a)
```

### Accessing Outside Code Block

Next, here's an example where the code is trying to access a variable outside of the code block where it is initially initialized:

```python
x = 5
if x < 10:
    y = x + 5
print(y)
```

In this instance, the program will work correctly. Since `x < 10` is `True`, the program will set a value for `y`, and we can then print it later in our program, even outside of the code block where `y` was initialized. 

However, if we have not executed that code block, we cannot use the variable. Here's a second example:

```python
x = 15
if x < 10:
    y = x + 5
print(y)
```

When we try to run this program, the interpreter gives us the following error:

```tex
NameError: name 'y' is not defined
```

So, if we cannot predict the value of `x` beforehand, it is impossible for us to know if `y` will actually be available or not. To solve that problem, we can initialize our variable `y` outside of the **If** statement's code block and give it a reasonable default value, as in this corrected example:

```python
x = 15
y = 0
if x < 10:
  y = x + 5
print(y)
```

That example will execute properly for any value of `x`, because we made sure the `y` is initialized and has a value in all possible cases. 

Thankfully, if we know that all possible paths through the program will initialize `y` with a value, we can avoid declaring outside of the block entirely, as in this example. 

```python
x = 15
if x < 10:
  y = x + 5
else:
  y = x - 5 
print(y)
```

This example will run without any problems, since the variable `y` is defined in both blocks of the **If-Then-Else** statement. In short, there is no possible execution path that does not initialize `y`, so it cannot cause an error. 

### Accessing Inside a Code Block

We've already seen several examples of this already, but here's a clear example of accessing a variable from a code block within the block where the variable was initialized:

```python
x = -1
if x < 0:
  x = -1 * x
print(x)
```

In this example, the variable `x` is initialized first, and given the value {{< math >}}$ -1 ${{< /math >}}. Then, it is accessed inside of the body of the **If** statement. Since it was already initialized, the program can access that variable at any point in the code. Later in this chapter we'll see examples of chaining and nesting conditional constructs, which will give us more examples of how this works.