---
title: "Classes"
pre: "4. "
weight: 40
---

The first step in creating a program that can represent _things_ in the real world is to determine which things we'd like to include in our program, and then create _classes_ that can describe the different types of objects.

## Class

In programming, a _class_ describes an individual entity or part of the program. In many cases, the _class_ can be used to describe an actual thing, such as a person, a vehicle, or a game board, or a more abstract thing such as a set of rules for a game, or even an artificial intelligence engine for making business decisions.  

In _object-oriented programming_, a class is the basic building block of a larger program. Typically each part of the program is contained within a class, representing either the main logic of the program or the individual entities or _things_ that the program will use.

{{% notice info "Every Class is a Type" %}}

Every time we define a new class, we create a new type.

```java
public class Dog {
    // class definition for Dog
    String name;

    public Dog(String aName){
        this.name = aName;
    }
}

public class Driver {
    public static void main(String[] args) {
        Dog x = new Dog("rover");  // Dog is now a data type
        Dog y = new Dog("spot");   // We use it when declaring a variable
    }
}
```

{{% /notice %}}

## Example

![Teacher and Student Clipart Image](/images/07-object/11.2.teacherstudent.png)

For example, let's consider a program that could be used to store the information about students and teachers at a school. For this program, we could create 2 instancs classes: **Student**, **Teacher**, and a driver class called **Main**. To help represent this program, we can use a _UML Class Diagram_ like this:

![UML Class Diagram showing Main, Student, and Teacher class](/images/07-object/11.2.classes.png)

In the diagram above, we see three boxes, one labeled for each class. Below the names we see entries for the _fields_ and _methods_ in the class, which we'll discuss on the next page. 

Obviously, the **Student** class can be used to represent a single student in school. Likewise, we'll use the **Teacher** class to represent a teacher. Finally, we've also included a **Main** class, which will store the actual logic for the program we're creating. However, right now the classes are just names, and aren't very useful in that form.

{{% notice note "UML Diagrams" %}}

The _Unified Modeling Language_ or _UML_ is a standard way to visualize the structure and design of a software program. UML includes many different types of diagrams, including _class diagrams_, _use case diagrams_, _sequence diagrams_, and more. 

In this course, we'll use some simple _class diagrams_ to help describe the structure and layout of classes in our programs. Those diagrams are very simple to read and understand, and you won't be asked to create any diagrams of your own right now. If you take some later programming courses, we'll cover more information about UML diagrams and how to work with them there.

If you want to learn more, here are a few helpful links:
* [Unified Modeling Language](https://en.wikipedia.org/wiki/Unified_Modeling_Language) on Wikipedia
* [Class Diagram](https://en.wikipedia.org/wiki/Class_diagram) on Wikipedia
* [What is Class Diagram?](https://www.visual-paradigm.com/guide/uml-unified-modeling-language/what-is-class-diagram/) from Visual Paradigm

{{% /notice %}}