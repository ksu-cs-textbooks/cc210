---
title: "Instance Classes"
pre: "1. "
weight: 10
---

Now that we understand the basics of what classes and objects are in object-oriented programming, let's look at how to create these items in Python.

## Creating an Instance Class

Creating a class in Python is very similar to creating a function. We can simply use the `class` keyword, followed by an identifier for the class and a colon.  The class definition, like all Python definitions and code-bodies, is indented. 

While it is not required, it is recommended to place just a single class in each file, with the filename matching the name of the class, followed by the `.py` file extension. By convention, class names in Python are written in PascalCase, meaning that each word is capitalized and there are no spaces between the words. We'll follow these rules in our code. 

So, to create an empty class named `Ingredient`, we would place the following code in a file named `Ingredient.py`:

```python
class Ingredient:
  pass
```

As we've already learned, each class declaration in Python includes these parts:
1. `class` - this keyword says that we are declaring a new class.
1. `Ingredient` - this is an identifier that gives us the name of the class we are declaring.
1. a colon (`:`) following the the identifier
1. a body (indented)-- For the moment we'll use `pass`

At the end of the declaration, we see a colon `:` marking the start of a new block, inside of which will be all of the _attributes_ and _methods_ stored in this class. We'll need to indent all items inside of this class, just like we do with other blocks in Python.

In order for Python to allow this code to run, we cannot have an empty block inside of a class declaration. So, we can add the keyword `pass` to the block inside of the class so that it is not empty. `pass`  tells the compiler to do nothing.  It is also referred to as a "no-op", which has its roots in assembly, a very low level language.  High level languages typically use a no-op when their syntax rules require that a code-block exists, but the program requires that code block do nothing.

To the left, we should see a tab for `Ingredient.py`. Let's go ahead and add the class declaration to it. Once we've completed that, we can use the button below to check our code and confirm that it is working before moving ahead.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

