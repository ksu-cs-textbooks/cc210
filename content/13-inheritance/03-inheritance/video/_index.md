---
title: "Inheritance"
pre: "1. "
weight: 10
hidden: true
date: 2019-11-03T00:00:26-05:00
---

{{< youtube Dz0JB0krAA8 >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

In this module, we'll learn how we can enhance the classes and objects we are creating in our programs by using inheritance to share attributes and methods between related classes.

A great example in the real world would be writing classes to represent animals such as dogs, cats, and mice. It is easy to see that there are numerous differences between each of these, but there are lots of similarities as well. So, if we want to write a program that includes classes that represent dogs, cats, and mice, we might want to use inheritance to represent the similarities between each species, helping us minimize the amount of code we need to write.

In fact, biologists realized something similar years ago. All species of life are classified using a hierarchical system, where members of the same class at each level share certain characteristics. This allows us to clearly describe the similarities and differences between two different species, simply by looking at which classes they share and where they diverge.

Going back to our earlier example representing data in a school, could we apply the same notion to students and teachers? For example, students and teachers both share a name and an age, and both have birthdays. Those are just a few of the similarities that might exist in a system like this.

So, we could move those shared attributes and methods to a new class, and then have both our student and teacher classes **inherit** from that parent class. In that way, both students and teachers will have access to those shared attributes and methods, but can also include their own unique attributes and methods in their respective child classes.

As a UML diagram, we could represent this program like this. both the Student and Teacher classes inherit from the Person class. That means that the Person class is a parent class or super class to both Student and Teacher, and those classes are child or subclasses to Person. We can represent that in UML using an arrow, which points from a child class to a parent class.

We can even go a step further, separating students into both undergraduate and graduate students, each with their own unique attributes and methods. However, due to inheritance, they would also share the attributes and methods of the Student and Person class, allowing us to reuse that code quickly and easily.

In this module, we'll explore how this works in theory, and then see how to build a structure like this in code.
