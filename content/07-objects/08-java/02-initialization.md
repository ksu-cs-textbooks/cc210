---
title: "Objects & Initialization"
pre: "2. "
weight: 20
---

Of course, our classes are not very useful at this point because they don't include any attributes or methods. Including instance attributes in an object class is one of the their basic uses, so let's start there.  

##  Types of Attributes

There are two types of attributes: Class and Instance.

Instance attributes are variables that "belong" to the instance.  It makes sense that a `Student` object owns its own name.

We will defer discussion of class attributes to a later module.

## Instance Attributes and the Constructor

To add instance attributes to a class, we can simply place a variable declarations <b>with access modifiers</b> inside the class but outside of any methods.

```java
public class Ingredient{
    
    public String name;
    public double amount;
    public String units;
}
```

This tells the compiler that each instance of "Ingredient" will have three variables.  This is one of the ways that objects store their data.  It is possible to assign values at this point, i.e. `public int amount= 2;`, but this stylistically bad.  Default values should be assigned in the constructors.

### The Constructor

The Constructor is a method named after the class.  It called each time an object is instantiated;  it gets triggered by use of the `new` keyword. Typically the constructor sets default values for the instance attributes.  

The Java compiler creates a default, no parameter constructor for every class.

```java
public Ingredient(){} // provided by the complier if not overwritten
```

But it is normal to **override** this definition with a constructor if your own.

```java
public Ingredient(){
    this.name = "flour";
    this.amount = 2.0;
    this.units = "cup";
}

```

Typically, all instance variables should be given a value in the constructor.  This gives programmers one place to look for all the names and values of all the instance variables in the object.  Also, the constructor(s) should always be the first method(s) inside an object class's definition.

### `this`

Java uses `this` to refer to the specific object used when calling a method.  It is the mechanism that ensures the `Ingredient` object `first` sees `first`'s data and `Ingredient` object `second` sees `second`'s data.  It is typically used for clarity.

```java
public Ingredient(String name, double amount, String units){
    this.name = name;
    this.amount = amount;
    this.units = units;
}
```

Here the parameter names obscure (or shadow) the instance variable names, and the use of `this` clarifies the code.  We assign the values of the parameters to the instance attributes of the same name.  "Shadowing" instance/class names with parameter names is considered bad coding style anywhere <b>except</b> in constructors.  Even in constructors is is easy to avoid, such as using `public Ingredient(String nameIn, int amountIn, String unitsIn)`.

{{< youtube nKbV2fbfT0w  >}}

<!-- TODO Update Video? -->

Feel free to refer to the UML diagram below to find the correct instance attributes for the `Ingredient` class so far.

![UML Class Diagram showing Ingredient](/images/07-object/ingredient_uml.png)

