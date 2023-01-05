---
title: "Multiple Inheritance"
pre: "7. "
weight: 70
---

Finally, we can also build classes that are able to inherit from multiple parent classes. In Java, this is done through the use of interfaces. 

## The Diamond Problem

Before we can really understand the importance of multiple inheritance, we must first discuss the "Diamond Problem." This is a very common example in object-oriented programming, and it is used to describe one of the common pitfalls for multiple inheritance in programming.

Consider the following code, which defines 4 classes:

```java
public abstract class A{
  
  public abstract void do_something();
}

public class B extends A{
  
  public void do_something(){
    System.out.println("B");
  }
}

public class C extends A{
  
  public void do_something(){
    System.out.println("C");
  }
}

public class D extends B, C{
  
}
```

In this code, we are trying to inherit from both class `B` and `C` inside of `D`. So, we'll end up with a class hierarchy diagram that looks something like this:

![Diamond Problem Diagram](/images/13-inherit/12.7.x.7.diamond_wiki.png)[^1]

[^1]: File:Diamond inheritance.svg. (2018, September 25). Wikimedia Commons, the free media repository. Retrieved 02:42, November 4, 2019 from https://commons.wikimedia.org/w/index.php?title=File:Diamond_inheritance.svg&oldid=321823174.

The problem arises when we try to use the class `D`, as in this sample program:

```java
public class Main{
  
  public static void main(String[] args){
    D obj = new D();
    obj.do_something(); // what happens?
  }
}
```

In this example, we are calling the `do_something()` method on an object instantiated from class `D`. However, that method is defined in both `B` and `C`, which are parents of `D`. So, what version of the code should we use?

In short, we have no idea! That is the crux of the diamond problem: if we allow multiple inheritance, we can run into situations where the program has no idea which version of a function's code to use. 

## Interfaces

Java allows us to solve this by the use of a special type of abstract class called an _interface_. An interface is an abstract class that only includes abstract methods, with no other data. One way to think about it is that it is simply describing the actions a class should be able to perform, also known as an _interface_. 

So, we can update the example above a bit using interfaces instead of abstract classes. 

```java

public interface B{
  
  public void do_something();
  
}

public interface C{
  
  public void do_something();
  
}

public class D implements B, C{
  
  public void do_something(){
    System.out.println("D");
  }
}
```

Here, we have used the keyword `interface` to declare that classes `B` and `C` are interfaces, and will only include abstract method declarations. Then, we can use the `implements` keyword to show that our class `D` is implementing both of these interfaces. We can also extend `D` from another class, and that would be placed before the `implements` keyword.

Of course, by doing so, we have to provide the implementation for `do_something()` in D. But, we can store an instance of `D` in variables for storing both `B` and `C` data types. Pretty neat, right?

We won't use multiple inheritance in this course, but it is helpful to know that it is available as we go forward in our programming experience.