---
title: "Overriding and Abstraction"
pre: "5. "
weight: 50
---

![UML Diagram showing Relationship between Student, Person, and Teacher Classes and Overloaded Methods](/images/13-inherit/12.5.uml.png)

Another handy feature of class inheritance is the ability to _override_ certain methods of the parent class. For example, in our **Person** class, we've included a method called `birthday()` that will simply increase that person's age by 1. 

However, what if we want to do something special when a student has a birthday? In that case, we can _override_ the `birthday()` method from the **Person** class by providing our own code for the method in the **Student** class. Then, when we create an object using the Student class, it will use the `birthday()` method from the **Student** class instead of the one from the **Person** class. In most languages, this will even work if we have the Student object stored in a variable using the Person data type. It's pretty handy!

Finally, we can also use another concept in object-oriented programming to create _abstract methods_ in our classes. An **abstract method is a method that is declared to be part of the parent class but is not implemented with any code.** We call a class containing such a method an _abstract class_. Since it has a method containing no code, we can no longer instantiate that class and use it.

However, any class that inherits from that class has the option to _implement_ the abstract methods by overriding and providing code for those methods. By doing so, the child class is no longer abstract and can be instantiated. However, if it does not do so, then the child class will also be abstract. 

In our UML diagram above, the `do_work()` method  and the class **Person** are abstract.  Because at least one method is abstract, the class **must** also be abstract.  We know this since their names are printed in an italic font. In the two child classes, both **Student** and **Teacher** have included an entry for the `do_work()` method. Since neither of those classes contains any italicized items, we know that they are not abstract. 

That covers most of the major concepts when working with inheritance and polymorphism in our programs. Before we learn how to write code using these ideas in our language of choice, we'll take a minute to review the important terminology we've learned so far in this chapter. 