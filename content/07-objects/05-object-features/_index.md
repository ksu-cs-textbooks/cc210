---
title: "Object Features"
pre: "5. "
weight: 50
---

{{% youtube fhLq9_iUZ3k %}}

[Video Materials]({{<relref "./video">}})

To make our classes more useful, we must give them features to help define the properties and actions of that class. So, let's look at each of those in turn and discuss how we might use those in our programs.

## Object Attributes

First, each class can have a set of _attributes_, sometimes known as _fields_, to describe the data stored by that class. In programming, these would be the variables stored within the class itself. These attributes represent the different properties of the thing the class represents, helping to distinguish it from other things in the world. 

For example, an **Ingredient** for a recipe might have a name of the ingredient, an amount and a units.  These might be "flour", 4 and "cups".

Inside a Unified Modeling Language (UML) class diagram, instance attributes go in the section immediately under the class name. Typically both attribute's proposed identifier and type are included.

![UML Class Diagram showing Ingredient](/images/07-object/UML_ingredient.png)

## Object Methods

In addition, each class can have a set of _methods_ or _actions_ that it can perform. In programming, these are the methods stored available to the object to help manipulate or provide the object's data. Lets assume we have and object `ingrd1` of type `Ingredient` with the following attributes: `name = "flour"`, `amount = 3.0`, `unit = "cup"`.

These methods may represent actions taken directly on the attributes. Our `Ingredient` class has three methods:

*  `toString()`:  returns a string describing the <b>object</b>; Something like `amount + units + " of " + name`
   * `ingrd1.toString()` would return the string "3.0 cup of flour"
*  `scale(factor)`: returns a new ingredient object scaled to the provide factor
   * `ingrd2 = ingrd1.scale(2.0)` results in 
     * `ingrd2` with `name = "flour"`, `amount = 6.0`, `unit = "cup"`.
     * `ingrd1` is unchanged
*  `convert(units)`: returns nothing.  Changes the object's `unit` attribute to the provided value and adjusts the objects `amount` attribute so that is correct for the new units
   * `ingrd1.convert("ml") ` results in `ingrd1` now containing `name = "flour"`, `amount = 709.1`, `unit = "ml"`
   
Here, each instance method is listed in the lower part of the UML class diagram.  It is annotated with the types of its expected parameters and return value or `void` if the method does not return any value[^1]

[^1]: Some UML diagrams may also use `void` instead of an empty parameter list if the method takes no parameters.

## Designing Classes

When designing a class for a program, it is important to make sure that each class includes the attributes and methods needed to represent the object fully within the program. However, we also don't need to include every single attribute and method we can think of. Sometimes it is best to be as simple as possible, only including the ones that will be used within the program. This helps make our code simple and easy to read. 

A great way to start is to make a list. We can ask ourselves questions such as "what information is needed to identify a single student?" or "what actions can a teacher perform in this program?" Typically the answers to those questions will help us build our classes, and eventually build our entire program. 

{{% notice note "Modeling" %}}

Classes are not typically modeled in pseudo code.  The design function usually creates and UML diagrams from which developers work.  Developers usually use pseudo code to develop individual methods or work through the logic of complex method call-chains.

{{% /notice %}}