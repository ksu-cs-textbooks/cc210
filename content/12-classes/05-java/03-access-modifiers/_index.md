---
title: "Access Modifiers"
pre: "3. "
weight: 30
---

{{< youtube 74s7zT2xKIY  >}}

[Video Materials]({{% relref "./video" %}})

As we work on developing our classes, we can also learn about a few special keywords called _modifiers_ we can use to protect data and methods stored in those classes. Let's review those and see how they work in our programs.

## Public and Private

First, we can use the `public` keyword in front of any of our class attributes and methods to make them accessible to any other Java code. We've already seen this keyword in used when we declare the `main` method in each of our programs. 

Alternatively, we can use the `private` keyword to prevent any code outside of our own class from accessing the attributes or methods we mark using `private`. 

Let's look at an example to see how this would work:

```java
public class Security{
  public String name;
  private int secret;
  
  public Security(){
    this.reset();
  }
  
  public int count(){
    return name.length();
  }
  
  private void reset(){
    this.name = "test";
    this.secret = 123;
  }
}
```

In this class, we have created both a private and a public attribute, and a private and a public method. We can also see that we are able to call the private method `reset()` from within our constructor, and in the `reset()` method we are able to access the `secret` private attribute without an issue. So, within our class itself, we don't have to worry about `private` or `public` modifiers preventing access to anything.

However, outside of that class, they have a big impact on what we can access. Consider the following `main()` method from a different class:

```java
public class Main{
  public static void main(String[] args){
    Security someSecurity = new Security();
    System.out.println(someSecurity.name);     // "test"
    System.out.println(someSecurity.secret);   // COMPILER ERROR
    System.out.println(someSecurity.count());  // 4
    someSecurity.reset();                      // COMPILER ERROR
  }
}
```

In this code, we cannot access any private members of the `Security` class. So, when we try to compile this code, we'll get the following error messages:

```tex
Main.java:5: error: secret has private access in Security
    System.out.println(someSecurity.secret);
                                   ^
Main.java:7: error: reset() has private access in Security
    someSecurity.reset();
                ^
2 errors
```

As we can see, the Java compiler itself enforces these security modifiers, making a very powerful way to limit access to the members and attributes in our classes. 

{{% notice info "Why Limit Access?" %}}

So, why would we want to do this? After all, if we're the ones writing the code, shouldn't we be able to access everything anyway? 

In many cases, the classes we are writing become part of a larger project, so we may not always be the ones writing code that interfaces with our class. For example, if we are writing an engine for a video game, we may want to make attributes such as the player's health private. In that way, anyone writing a mod for the engine would not be able to modify those values and cheat the system. Similarly, there are some actions, such as a `reset()` method, that we may only want to call from within the class. 

As we build larger and more complex programs, we'll even find that it is helpful as developers to limit access to just the methods and attributes that should be accessed by anyone using our classes, helping to simplify our overall program's structure. 

{{% /notice %}}

## UML Class Diagrams

We can denote the access level of items in a UML class diagram using a few simple symbols. According to the UML standard, any item with a plus `+` in front of it should be public, and any item with a minus `-` in front should be private. So, we can build a UML class diagram showing the `Main` and `Security` classes as shown below:

![UML Class Diagram with Security](/images/12-class/11.6.j.6.secureuml.png)
