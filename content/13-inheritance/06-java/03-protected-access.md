---
title: "Protected Access"
pre: "3. "
weight: 30
---

Working with inherited classes also gives us an opportunity to learn about how data can be secured in the parent class so that any child class can easily access it, without any external class being able to do so.

![Vehicle UML Diagram](/images/13-inherit/12.7.j.uml.png)

## Protected Attributes

In Java, we can simply use the `protected` keyword as a security modifier, just like we learned how to use `private` and `public` in an earlier module. In effect, anything marked as `protected` in Java will be accessible to the class in which it is declared, as well as to any child classes, but not to any other classes.

In our UML diagram, we use the hash symbol `#` before an item to denote that it should be protected using the `protected` keyword. So, we can update our `Vehicle` class to make the `speed` attribute as well as the constructor protected:

```java
public class Vehicle{
  
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
  
  public String describe(){
    return "";
  }
  
}
```

It is worth noting, however, that any developer could simply chose to inherit from one of these classes, giving them access to all of that data. So, while call these "security modifiers", they aren't actually providing a real sense of security. Instead, they are simply making it more difficult to accidentally access or use these items. Any determined programmer will probably be able to figure out a way around it.

Also, since we are making the constructor in this class protected, it will prevent any class that doesn't extend this class from instantiating an object based on this class. A bit later in this chapter, we'll also learn how to declare this class as an abstract class, which will also prevent any other class from instantiating it. 

Let's go ahead and update all of the items marked as protected in the UML diagram above in our code.
