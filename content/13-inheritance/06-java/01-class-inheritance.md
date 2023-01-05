---
title: "Class Inheritance"
pre: "1. "
weight: 10
---

Now that we've learned a bit about the theory behind inheritance in object-oriented programming, let's dive into the code and see how we can accomplish this in Java. 

For these examples, we'll be implementing the following UML diagram:

![Vehicle UML Diagram](/images/13-inherit/12.7.j.uml.png)

{{% notice note "Italics & Hash Symbols" %}}

The UML diagram above includes some items that we haven't discussed yet. Don't panic! We'll cover them as they become relevant in this module.

For now, feel free to ignore the fact that methods are italicized. Similarly, you can treat a hash symbol `#` in front of an attribute or method the same as a plus `+` that denotes they should be public. 

We'll learn what each of these indicate later in this module.

{{% /notice %}}

## Inheritance

The first step is to build the inheritance relationships. Let's start by just declaring the `Vehicle` class for now. Remember that the `Vehicle` class should be defined in `Vehicle.java`.  We won't add any methods or attributes at this point:

```java
public class Vehicle{
  
}
```

As you'll recall, a class declaration is pretty simple.

Next, let's declare the `MotorVehicle` class in `MotorVehicle.java`. This class inherits from the `Vehicle` class, so we'll need to use a new keyword to make that work:

```java
public class MotorVehicle extends Vehicle{
  
}
```

In the example above, we've used the `extends` keyword in Java to show that the `MotorVehicle` class inherits from, or _extends_, the `Vehicle` class. That's all we need to do to show that a class inherits from another class.

Let's see if we can do the same process for the `Car`, `Truck`, and `Airplane` classes that are shown in the UML diagram above. We must make sure we place the code for each class in the correct file. Use the tests below to make sure that you have your classes structured correctly.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}
