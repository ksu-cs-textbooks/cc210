---
title: "Class Features"
pre: "1. "
weight: 10
date: 2019-09-24T00:00:26-05:00
hidden: true
---

{{< youtube fhLq9_iUZ3k >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

In this module, we'll learn how we can model real-world items in our code through the use of classes. It is one of the core features of any object-oriented programming language, but it can sometimes be difficult to understand at first how this works. So, let's walk through a quick example to see how we can represent items from the world in our classes, and what features those classes might have.

A very classic example from object-oriented programming is to model a student and a teacher at a school. It seems pretty natural, given our academic setting. So, on this slide, we see a representation of a teacher and a student.

The most commonly used method for representing the structure of classes in code is through the use of UML diagrams. UML is short for "Unified Modeling Language" which is a meta-language that defines all sorts of ways to represent items from code and programs visually. In this case, we are using boxes from a specific type of UML diagram, a class diagram. In this type of diagram, we'll have a box named "Student" and a box named "Teacher", representing a student and a teacher.

Next, we can think about what types of information might help us represent a student and a teacher. For example, a student would have a name, as well as an age, student id, and the number of credits completed and a GPA. For a teacher, we'll probably also have a name, but maybe a salary and focus area as well.

Each of those items represents an "attribute" of the class. So, in our diagram, we'll list these in the top section of the box. We'll also label each of them with a data type, telling us a bit more about what type of data we are storing.

Also, we can think about the actions that a student or a teacher might perform, or actions that may be performed on a student or a teacher to update some information about that item. For example, a student might have a birthday that updates their age, or they might receive a grade and update their number of credits and GPA. For a teacher, they might get a promotion, resulting in a higher salary.

Those actions are the methods, or class functions, that each class can perform. So, we'll list those in the bottom section of each box. Just like any other function, we can list the name and types of the parameters, as well as the type of data returned by the method.

There we go! This is a quick exploration of how we can represent real-world things such as a student and a teacher in our code using classes. In this module, we'll see how we can write classes like this in code, and how to instantiate objects based on those classes to represent individual students and teachers in our programs.
