---
title: "Classes"
pre: "1. "
weight: 10
---

## Creating a Class

Creating a class in Python is very similar to creating a function. We can simply use the `class` keyword, followed by an identifier for the class. 

While it is not required, it is recommended to place just a single class in each file, with the filename matching the name of the class, followed by the `.py` file extension. By convention, class names in Python are written in CamelCase, meaning that each word is capitalized and there are no spaces between the words. We'll follow these rules in our code. 

So, to create an empty class named `Student`, we would place the following code in a file named `Student.py`:

```python
class Student:
  pass
```

As we've already learned, each class declaration in Python includes these parts:
1. `class` - this keyword says that we are declaring a new class.
1. `Student` - this is an identifier that gives us the name of the class we are declaring.

Following the declaration, we see a colon `:` marking the start of a new block, inside of which will be all of the _fields_ and _methods_ stored in this class. We'll need to indent all items inside of this class, just like we do with other blocks in Python.

In order for Python to allow this code to run, we cannot have an empty block inside of a class declaration. So, we can add the keyword `pass` to the block inside of the class so that it is not empty. `pass`  tells the compiler to do nothing.  It is also referred to as a "no-op", which has its roots in assembly, a very low level language.  High level languages typically use a no-op when their syntax rules require that a code-block exists, but the program requires that code block do nothing.

To the left, we should see three Python files open: `Student.py`, `Teacher.py`, and `Main.py`. Let's go ahead and add the class declaration code to each file. Once we've completed that, we can use the button below to check our code and confirm that it is working before moving ahead.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}