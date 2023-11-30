---
title: "Constructors"
pre: "7. "
weight: 70
---

{{% youtube kFre_ANNvQc %}}

[Video Materials]({{<relref "./video">}})

On the last page, we created functions in the `Main` class to instantiate a `Student` and `Teacher` object and set the attributes for each object. However, wouldn't it make more sense for the `Student` and `Teacher` classes to handle that work internally? 

Thankfully, we can do just that by providing a special type of method in our classes, called a _constructor_ method.

## Constructors

A _constructor_ is a special method that is called whenever a new instance of a class is created. It is used to set the initial values of attributes in the class. We can even accept parameters as part of a constructor, and then use those parameters to populate attributes in the class. 

Let's go back to the `Student` class example we've been working on and add a simple constructor to that class:

```java
import java.lang.Math;

public class Student{
  String name = "name";
  int age = 19;
  String student_id = "123456987";
  int credits = 0;
  double gpa = 0.0;
  
  Student(){
  }
  
  // other methods omitted
}
```

The constructor itself is very simple:

```java
  Student(){
  }
```

This is called the _default constructor_ for the class because it accepts no parameters. A constructor is simply a method in the class with he same name as the class, without any return type defined. 

In fact, Java automatically creates a _default constructor_ which contains no code if one isn't added to the class, just like this one. So, really, this constructor isn't adding anything. Let's add some code to see what it can do!

```java
import java.lang.Math;

public class Student{
  String name = "name";
  int age = 19;
  String student_id = "123456987";
  int credits = 0;
  double gpa = 0.0;
  
  Student(){
    this.name = "name";
    this.age = 19;
    this.student_id = "123456987";
    this.credits = 0;
    this.gpa = 0.0;
  }
  
  // other methods omitted
}
```

In this example, we have added code to the default constructor to initialize the attributes to default values. Notice that we also used the `this` keyword once again to refer to the current object, just to be sure that we are setting the correct attributes. 

In fact, now that our default constructor includes these default values, we can remove them from the attribute declaration themselves:

```java
import java.lang.Math;

public class Student{
  String name;
  int age;
  String student_id;
  int credits;
  double gpa;
  
  Student(){
    this.name = "name";
    this.age = 19;
    this.student_id = "123456987";
    this.credits = 0;
    this.gpa = 0.0;
  }
  
  // other methods omitted
}
```

In this way, we can enforce the default values through the default constructor, without including them in the attribute declarations above, making the code a bit easier to read. 

With that constructor, we can then instantiate the class and see that the attribute values are set correctly:

```java
public class Main{
  
  public static void main(String[] args){
    Student someStudent = new Student();
    System.out.println(someStudent.name) // "name";
    System.out.println(someStudent.age)  // 19
  }
}
```

So, constructors are a very easy way to help set initial values for attributes in a class. We can even call class methods directly from the constructor if needed to help with setup. 

## Constructors with Parameters

We can also create constructors that accept arguments. For example, we can create a constructor that accepts a value for each attribute as in this example:

```java
import java.lang.Math;

public class Student{
  String name;
  int age;
  String student_id;
  int credits;
  double gpa;
  
  Student(){
    this.name = "name";
    this.age = 19;
    this.student_id = "123456987";
    this.credits = 0;
    this.gpa = 0.0;
  }
  
  Student(String name, int age, String student_id, int credits, double gpa){
    this.name = name;
    this.age = age;
    this.student_id = student_id;
    this.credits = credits;
    this.gpa = gpa;
  }
  
  // other methods omitted
}
```

In this example, we still have the default constructor with no parameters that sets the default values for each attribute. However, we've also added a second constructor that accepts 5 parameters, one for each attribute in the class. 

Inside that constructor, the code looks very similar to the function we added to the `Main` class on the previous page. It will use each parameter to set the corresponding attribute, using the `this` keyword once again to refer to the current object. 

Also, this example shows one very important aspect of constructors: just like with methods, we can include multiple constructors, each one accepting a different set of parameters. So, it is possible to make any number of constructors if needed, as long as each one accepts a different set of parameters. 

## UML Class Diagrams

We can also add constructors to our UML class diagrams. A constructor is usually denoted in the methods section of a class diagram by using the name of the class as the method name and omitting the return type. In addition, they are usually included at the top of the methods section, to make them easier to find:

![UML Class Diagram with Constructors](/images/12-class/11.6.j.5.constructuml.png)

The diagram above shows the `Student` and `Teacher` classes with constructors included. 

## Try It!

Now that we know how to use constructors, let's modify our working example to add the following constructors to both `Teacher` and `Student`:

* A default constructor that sets the default values for each attribute
* A constructor that accepts a parameter for each attribute, and uses those values to populate the object

The examples for `Student` have already been created above, but we'll have to figure out how to do the same for the `Teacher` class. 
