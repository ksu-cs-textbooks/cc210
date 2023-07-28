---
title: "Properties"
pre: "9. "
weight: 90
---

{{% youtube diUJGAV0iiQ %}}

[Video Materials]({{<relref "./video">}})

So far in this chapter we've learned how to create private and public attributes in our classes. What if we want to create an attribute that is read-only, or one that only accepts a particular set of values? In Java, we can do that using a pattern of _getter_ and _setter_ methods. 

Some languages use the term _property_ to refer to an attribute that is typically accessed using _getter_ and _setter_ methods. We will use that term in this context for now. 

## Getter Methods

In Java, a _getter_ method is a method that can be used to access the value of a private attribute. Conventionally, the method's name begins with `get` to make it clear what it does. Let's look at an example:

```java
public class Property{
  private String name;
    
  public Property(){
    name = "";
  }
  
  public String getName(){
    return name;
  }
  
}
```

In this class, the `name` attribute is private, so normally we wouldn't be able to access its value. However, we've created a method `getName()` that acts as a _getter_ for the `name` attribute. In this way, the value of that variable can be accessed in a read-only fashion.

From other code, we can call that method just like any other:

```java
Property prop = new Property();
String name = prop.getName();
```

## Setter Methods

Similarly, we can create another method that can be used to update the value of the `name` attribute:

```java
import java.lang.IllegalArgumentException;

public class Property{
  private String name;
  
  public Property(){
    name = "";
  }
  
  public String getName(){
    return name;
  }
  
  public void setName(String a_name){
    if(a_name.length() == 0){
      throw new IllegalArgumentException("Name cannot be an empty string!");
    }
    this.name = a_name;
  }
  
}
```

In this code, we've added a `setName()` method that can be used to update the value stored in the `name` attribute. We're also checking to make sure that the argument provided to the `a_name` parameter is not an empty string. If it is, we can throw an `IllegalArgumentException`, which would alert the user that this is not allowed. Of course, it would be up to the person writing the code that calls this method to properly catch and handle this exception. 

## UML Class Diagrams

Getter and setter methods are displayed on a UML class diagram just like any other method. We use naming conventions such as `getName()` and `setName()` to make it clear that those methods are getters and setters for the attribute `name`, as in this UML class diagram:

<!-- TODO UML Incorrect - name property should be private -->

![UML Class Diagram with Properties](/images/12-class/11.6.j.9.propertyuml.png)

## Try It!

So, through the use of _getter_ and _setter_ methods, we can either prevent other code from updating an attribute, or enforce restrictions on that attribute's values, without actually exposing the attribute. Here's a sample `main` class that demonstrates how to use these methods:

```java
public class Main{
  public static void main(String[] args){
    Property prop = new Property();
    String name = prop.getName();
    System.out.println(name);
    prop.setName("test");
    System.out.println(prop.getName());
  }
}
```
