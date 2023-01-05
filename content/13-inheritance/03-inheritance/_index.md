---
title: "Inheritance"
pre: "3. "
weight: 30
---

{{% youtube Dz0JB0krAA8 %}}

[Video Materials]({{<relref "./video">}})

<p style="color:red;font-size:110%;padding:10">The arrowheads in the video's UML are the wrong type.  UML uses different arrowheads to mean different things.  Inheritance uses an "open triangle" not filled in arrows as depicted here.  The images in the text have been updated. </p>

![Person Inherited by Student and Teacher](/images/13-inherit/12.3.inherit.png)

For example, we could create a class called **Person** in our program, and that class could represent all of the attributes and methods that are shared by both students and teachers, as well as by any other people we might want to include in our program. 

Then, we can update the **Student** and **Teacher** classes to _inherit_ those attributes and methods from the **Person** class. In effect, we are saying that a student or a teacher is also a person, so anything that a person is or does also applies to a student or a teacher. 

{{% notice note "Terminology" %}}

There are some special terms we can use to describe the classes in an inheritance relationship. In this example:

**Person** is the _parent_ class, _base_ class, or _superclass_.
**Student** and **Teacher** are _child_ classes, _derived_ classes, or _subclasses_ of **Person**. 

{{% /notice %}}

This is a really important concept in object-oriented programming. It allows us to easily define the similarities between several classes. 

![UML Diagram showing Relationship between Student, Person, and Teacher Classes](/images/13-inherit/12.3.uml.png)

In a UML diagram, we can show this inheritance relationship using an open arrow between the classes. It's important to remember that the arrow points to what the class is inheriting _from_. So, the arrow going from the Student class to the Person class says "the Student class inherits from the Person class." We can also remember this by saying the arrow "**P**oints to the **P**arent" class. This can be confusing, so we must always make sure we look closely at the direction the arrow is pointing in our UML diagrams.

![UML Diagram showing Relationship between Many Classes Classes](/images/13-inherit/12.3.uml2.png)

Finally, we can even go further and create another set of classes to represent **Graduate** and **Undergraduate** students, and have them inherit from the **Student** class. There is no limit to how many layers of inheritance we can create in our programs. In addition, some languages—such as Python—allow a class to inherit from multiple parent classes!