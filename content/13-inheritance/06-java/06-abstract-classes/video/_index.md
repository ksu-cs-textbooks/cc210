---
title: "Java Abstract"
pre: "5.J. "
weight: 50
hidden: true
date: 2019-11-03T00:00:26-05:00
---

{{< youtube Sxg75nfH5q4 >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

Another major feature of inheritance in object-oriented programming is the ability to declare a class abstract. In essence, an abstract class cannot be instantiated, but can give the structure of attributes and methods that are inherited by child classes.

In an abstract class, at least one method should also be abstract, which means that it usually doesn't provide any code inside of the method itself. One way to think of this is that each child class should include this method, but each one is responsible for overriding the method with the correct code.

In UML, abstract methods are shown in italics. So, on this diagram, the `describe()` method in the Vehicle class, as well as the `honk_horn()` method of the MotorVehicle class should be abstract. Let's explore how to do that in Java.

First, here is the Vehicle class we saw earlier. On a previous page in this module, we learned that attributes and methods with a pound or hash symbol in front of them should be protected, so we'll need to make that update first.

Then, to make the class and `describe()` method abstract, we can simply add the `abstract` keyword to each one.

For methods, when we make them abstract, we can also remove the code block that gives the code to be executed inside of the method and replace it with a semicolon, vastly simplifying the method in the parent class.

There we go! That's all it takes. See if you can do the same in the MotorVehicle class on this page.
