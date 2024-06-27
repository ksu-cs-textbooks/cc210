---
title: "Abstract Classes"
pre: "6. "
weight: 60
---

{{< youtube Sxg75nfH5q4  >}}

[Video Materials]({{% relref "./video" %}})

<p style="color:red"><b>Note:</b> this video contains errors in the UML diagram, these errors have been fixed below.</p>

Another major feature of class inheritance is the ability to define a method in a parent class, but not provide any code that implements that function. In effect, we are saying that all objects of that type must include that method, but it is up to the child classes to provide the code. These methods are called _abstract_ methods, and the classes that contain them are _abstract_ classes. Let's look at how they work!

![Vehicle UML Diagram](/images/13-inherit/12.7.j.uml.png)

## Abstract

In the UML diagram above, we see that the `describe()` method in the `Vehicle` class is printed in italics. That means that the method should be abstract, without any code provided. To do this in Java, we simply must use the `abstract` keyword on both the method and the class itself:

```java
public abstract class Vehicle{
  
  private String name;
  protected double speed;
 
  public String getName(){ return this.name; }
  
  protected Vehicle(String name){
    this.name = name;
    this.speed = 1.0;
  }
 
  
  public double move(double distance){
    System.out.println("Moving");
    return distance / this.speed;
  }
  
  public abstract String describe();
  
}
```

Notice that the keyword `abstract` goes after the security modifier, but before the `class` keyword on a class declaration and the return type on a method declaration.  

In addition, since we have declared the method `describe()` to be abstract, we must place a semicolon after the method declaration, without any curly braces. This is because an abstract method cannot include any code. 

Now, any class that inherits from the `Vehicle` class must provide an implementation for the `describe()` method. If it does not, that class must also be declared to be abstract. So, for example, in the UML diagram above, we see that the `MotorVehicle` class does not include an implementation for `describe()`, so we'll also have to make it abstract. 

We can also declare a class to be abstract without including any abstract methods. By doing so, it prevents the class from being instantiated directly. Instead, the class can only be inherited from, and those child classes can choose to be instantiated by omitting the `abstract` keyword.

## Try It!

Let's see if we can update the `Vehicle` and `MotorVehicle` classes to be abstract, with an abstract definition for the `describe()` and `horn_honk()` method as well.