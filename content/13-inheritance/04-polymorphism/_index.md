---
title: "Polymorphism"
pre: "4. "
weight: 40
---

{{< youtube ZIIMC9LNvZY  >}}

[Video Materials]({{% relref "./video" %}})

Allowing a class to inherit attributes and methods from another class allows us to use those classes in very unique ways. 

One way we can use those classes is through the application of _polymorphism_. Polymorphism can be loosely defined as "the condition of occurring in several different forms"^[https://www.lexico.com/en/definition/polymorphism], but in programming we use the term to describe the fact that an object instantiated from a class that inherits from another class can take on multiple forms, depending on how it is used.

Let's go back to basics for just a minute and talk about what this means in the simplest sense. In most programming languages, such as Java or C, a variable must be declared with a data type that tells us what type of data we can store in that variable. It could be an integer, a floating point number, or even a particular type of object such as a `Student` object. Other languages, such as Python, don't require us to declare the data type of a variable in advance, but internally it keeps track of exactly the type of data stored in that variable when it is assigned.

![UML Diagram showing Relationship between Student, Person, and Teacher Classes](/images/13-inherit/12.3.uml.png)

For example, let's assume that we've instantiated an object using the `Teacher` class. So, initially, we know that the data type of that variable is `Teacher`, since it was created from that class. 

However, what if we try to store that object in a variable with the `Person` data type? Will that work? Put another way, will the program consider an object of the `Teacher` data type to _also_ be an object of the `Person` data type?

Indeed it will! This is because an object instantiated from a class that inherits from other classes can exhibit _polymorphism_, existing as many different data types at the same time. Depending on how we use it, an object created using the `Teacher` class can also be thought of as a `Person`. 

However, if we create an object from the `Person` class, we can't say whether it is a `Teacher` or not. So, we aren't allowed to go in that direction---a `Person` object cannot be stored in a variable of the `Teacher` data type.

A great way to think of this would be the logical statement:

```tex
All Teachers are Persons
But Not All Persons are Teachers
```

{{% notice info "Inheritance is Transitive" %}}

Consider the following

![UML](/images/13-inherit/transitive.png)

We say that inheritance is **transitive**.  A `Border Collie` **is a** `Dog` **is a** `Pet`.  Thus a `Border Collie` **is a** `Pet`.

This relationship is one-way, sub-classes have all their sub-class-specific  features, as well as those of all their super-classes. 

Most languages have at the top level, an `Object` class, from which all objects implicitly inherit.  Both Python and Java have an Object class, from which all programmer defined objects get their default constructors and toString(`__str__`) methods.

**Inheritance IS NOT symmetric**

Inheritance is not symmetric.  The fact that a `Border Collie` is a `Dog`  **DOES NOT MEAN** a `Dog` is a `Border Collie`.  

Inheritance is not equality. Equality is both transitive and symmetric.

{{% /notice %}}

In this chapter, we'll see how we can use this feature in our programs. Polymorphism is sometimes difficult to define or describe without seeing it in action. 