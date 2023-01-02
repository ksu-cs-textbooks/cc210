---
title: "Instantiable Classes"
pre: "6. "
weight: 60
---

A class can serve many functions, the most basic of which is to serve as a blueprint for the data and methods used to access and manipulate that data.  We will refer to these as "object" or "instance" classes.  An object class is a class with the primary purpose of encapsulating and manipulating related data.

When you instantiate an object of a class, you create a variable of that type.  The class definition is only a only the _specification_ for each of those items. So, let's look at the next step, which is to create _objects_ based on the _classes_ we've defined.

## Objects

Once we've created a class, we can then use it to _instantiate_ an _object_ based on that class. Let's break that statement down a bit.

The word _instantiate_ comes from the word _instance_, which means "an example or single occurrence of something." So, we're creating a single example of a class, which we call an _object_. 

Most high level programming languages create an object by calling a special function generically called a constructor, which usually has the same name as the class from which you are trying to create an instance.  For example

```text
CLASS Ingredient { ... }

flour = Ingredient( ... )
sugar = Ingredient( ... )
```

Here `flour` and `sugar` are both variables of type `Ingredient`, but they represent different things and would each contain their own `name`, `amount` and `units`.

## Some Vocabulary

Object-oriented programming introduces a large number of new terms, each with very specific uses. Here is a quick overview of some of the new terms we've learned so far:

* **Object-Oriented Programming**: A programming paradigm that uses objects as the basis of the program's structure
* **Class**: A specification of a new data type in a program, including _fields_ and _methods_, that are used to describe a single part of a program
* **Object**: A unique _instance_ of a class, representing a single concrete item in the program
* **Instantiation**: The process of creating an _object_ based on a _class_
* **Attribute**: A single variable defined in a class or stored in an object; also called a _field_
* **Method**: An action that can be performed by a class or object; typically to access or change an Attribute; also called an _action_ 

{{% notice info "Class Descriptions" %}}

Classes are a versatile programming constructs.  Their combination of data and methods make them great containers for related information and procedures.  Some generic groupings would be:

* Object class  -- an instantiable class that contains data describing the object and methods to access and manipulate that data
* Driver class  -- normally not instantiable, generally only contains a `main()` method
* Utility class -- not instantiable, generally contains methods and related constants (like the math library)

You may hear the terms abstract and concrete.  Abstract classes are incomplete, in effect they are blueprints for blueprints.  Concrete classes are complete. We will introduce abstract classes, and why you might use them, in a few modules.

{{% /notice %}}