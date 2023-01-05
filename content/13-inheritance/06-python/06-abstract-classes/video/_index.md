---
title: "Python Abstract"
pre: "5.P. "
weight: 51
hidden: true
date: 2019-11-03T00:00:26-05:00
---

{{< youtube X21IFfio_h0 >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

Another major feature of inheritance in object-oriented programming is the ability to declare a class abstract. In essence, an abstract class cannot be instantiated, but can give the structure of attributes and methods that are inherited by child classes.

In an abstract class, at least one method should also be abstract, which means that it usually doesn't provide any code inside of the method itself. One way to think of this is that each child class should include this method, but each one is responsible for overriding the method with the correct code.

In UML, abstract methods are shown in italics. So, on this diagram, the `describe()` method in the Vehicle class, as well as the `honk_horn()` method of the MotorVehicle class should be abstract. Let's explore how to do that in Java.

First, here is the Vehicle class we saw earlier. On a previous page in this module, we learned that attributes and methods with a pound or hash symbol in front of them should be protected, so we'll need to make that update first.

Then, we'll need to import both `ABC` and `abstractmethod` from the `abc` library. ABC is short for "abstract base class" in Python, if that is helpful for remembering the name.

Then, we'll update the Vehicle class to inherit from the `ABC` class. The `ABC` class is a special class that tells Python that any class directly inheriting from it should be abstract.

Then, to make the `describe()` method abstract, we can just add the `@abstractmethod` method decorator. This is very similar to the `@staticmethod` decorator we use to make a method static.

For methods, when we make them abstract, we can also remove the code block that gives the code to be executed inside of the method and replace it with  the `pass` keyword, vastly simplifying the method in the parent class. However, that is not required in Python, and abstract classes can contain code if desired.

There we go! That's all it takes. See if you can do the same in the MotorVehicle class on this page.
