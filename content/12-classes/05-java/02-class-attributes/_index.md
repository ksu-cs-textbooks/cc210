---
title: "Class Attributes"
pre: "2. "
weight: 20
---

{{< youtube iAi_LIWyU_c  >}}

[Video Materials]({{% relref "./video" %}})

Some methods and attributes belong to the class and are shared by all the instances of the class. On the UML these are noted by underlines.  In Java,  we use the `static` modifier to make "class features". We've seen this modifier each time we declare the `main` method in our programs, but we haven't really been able to discuss exactly what it means.  In essence, the `static` modifier makes an attribute or method part of the class in which it is declared instead of part of objects instantiated from that class. 

## Static Attributes

First, we can use the `static` modifier with an attribute, attaching that attribute to the class instead of the instance. Here's an example:

```java
public class Stat{
  public static int x = 5;
  public int y;
  
  public Stat(int an_y){
    this.y = an_y;
  }
}
```

In this class, we've created a `static` attribute named `x`, and a normal attribute named `y`. Here's a `main()` method that will help us explore how the static keyword operates:

```java
public class Main{
 public static void main(String[] args){
   Stat someStat = new Stat(7);
   Stat anotherStat = new Stat(8);
   
   System.out.println(someStat.x);      // 5
   System.out.println(someStat.y);      // 7
   System.out.println(anotherStat.x);   // 5
   System.out.println(anotherStat.y);   // 8
   
   someStat.x = 10;
   
   System.out.println(someStat.x);      // 10
   System.out.println(someStat.y);      // 7
   System.out.println(anotherStat.x);   // 10
   System.out.println(anotherStat.y);   // 8
   
   Stat.x = 25;
   
   System.out.println(someStat.x);      // 25
   System.out.println(someStat.y);      // 7
   System.out.println(anotherStat.x);   // 25
   System.out.println(anotherStat.y);   // 8
 } 
}
```

First, we can see that the attribute `x` is set to 5 as its default value, so both objects `someStat` and `anotherStat` contain that same value. Then we can update the value of `x` attached to `someStat` to 10, and we'll see that both objects will now contain that value. That's because the value is `static`, and there is only one copy of that value for all instances of the `Stat` class. 

Finally, and most interestingly, since the attribute `x` is static, we can also access it directly from the class `Stat`, without even having to instantiate an object. So, we can update the value in that way, and it will take effect in any objects instantiated from `Stat`. 

## Static Methods

We can also do the same for static methods. 

```java
public class Stat{
  public static int x = 5;
  public int y;
  
  public Stat(int an_y){
    this.y = an_y;
  }
  
  public static int sum(int a){
    return x + a;
  }
}
```

We have now added a static method `sum()` to our `Stat` class. The important thing to remember is that a static method cannot access any non-static attributes or methods, since it doesn't have access to an instantiated object. Likewise, we cannot use the `this` keyword inside of a static method. 

As a tradeoff, we can call a static method without instantiating the class either, as in this example:

```java
public class Main{
 public static void main(String[] args){
   //other code omitted
   Stat.x = 25;
   
   Stat moreStat = new Stat(7);
   System.out.println(moreStat.sum(5));  // 30
   System.out.println(Stat.sum(5));      // 30
 }
}
```

This becomes extremely useful in our `main()` method. Since the `main()` method is always static, it can only access static attributes and methods in the class it is declared in. So, we can either create all of our additional methods in that class as `static` methods, or we can instantiate the class it is contained in. We'll see how to do that later in the example project in this chapter. 

## UML Class Diagrams

Of course, we can also denote items that should be static in our UML class diagrams. According to the UML specification, any static items should be underlined, as in this sample UML diagram below:

![UML Class Diagram with Static Items](/images/12-class/11.6.j.7.staticuml.png)
