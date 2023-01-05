---
title: "Polymorphism"
pre: "4. "
weight: 40
---

{{% youtube OUoWtw785ss %}}

[Video Materials]({{<relref "./video">}})

<!-- TODO Update Video -->

<p style="color:red"><b>Note:</b> this video contains errors in the UML diagram, these errors have been fixed below.</p>

Now that we've learned how to build the structure needed for classes to inherit attributes and methods from other classes, let's explore how we can use those classes in our code.

![Vehicle UML Diagram](/images/13-inherit/12.7.j.uml.png)

## Polymorphism

Earlier, we defined _polymorphism_ as "the condition of occurring in several different forms"[^1]. In code, this allows us to create an object of a child class, and then store it in the data type for the parent class. Let's look at an example.

[^1]: https://www.lexico.com/en/definition/polymorphism

```java
public class Main{
  
  public static void main(String[] args){
    Vehicle plane = new Airplane("Plane", 123, 45);
    System.out.println(plane.getName());
    System.out.println(plane.describe());
    System.out.println(plane.move(10));

    Vehicle car = new Car("Car", 4);
    System.out.println(car.getName());
    System.out.println(car.describe());
    System.out.println(car.move(10));
  }
}
```

In this code, we are instantiating an `Airplane` object and a `Car` object, but we are storing them in a variable declared with the `Vehicle` data type. This is polymorphism at work! Since both `Airplane` and `Car` are inheriting from the `Vehicle` data type, we can store object of each of those types in the `Vehicle` data type.

Also, since those variables are stored using the `Vehicle` data type, we can use any methods and access any attributes that are available publicly from the `Vehicle` class. 

So, when we run this code using these commands:

```bash
cd ~/workspace/12j-inherit/vehicle
javac Vehicle.java Airplane.java MotorVehicle.java Car.java Truck.java Main.java
java Main
```

we'll get the following output:

![Java Screenshot with Output](/images/13-inherit/12.7.j.4.test1.png)

As we can see, even though we are calling methods defined in the `Vehicle` class, it is actually using the code from the methods that were defined in the `Airplane` and `Car` classes, respectively. This is because those methods are **overridden** in the child classes. 

What if we want to use the `honk_horn()` method of the `Car` object? Could we do that?

```java
Vehicle car = new Car("Car", 4);
System.out.println(car.honk_horn());
```

When we try to compile that code, we'll get the following error:

![Java Screenshot with Error](/images/13-inherit/12.7.j.4.error1.png)

This is because the `Vehicle` class doesn't have a method called `honk_horn()` defined. So, even though the _object_ is a `Car`, since it is stored in a variable using the data type `Vehicle`, we can only access things that were defined in the `Vehicle` class.

So, when it comes to polymorphism, there are a couple of important rules to remember:

1. We can store an object instantiated from any child class within a variable using the data type of any parent of that class. 
2. We can only call methods and access attributes that are declared public in the class used as the data type of the variable, regardless of what type of object it stores.
3. When we call methods that have been overridden, it will use the overridden code that is defined either in the child class, or the class nearest the child class in the inheritance hierarchy. 

## Another Example

Here's another example of the power of polymorphism. In this case, we'll create an array that stores `Vehicles`, and fill that array with different types of vehicles. 

```java
public class Main{
  
  public static void main(String[] args){
    Vehicle[] array = new Vehicle[3];
    array[0] = new Airplane("Plane", 123, 45);
    array[1] = new Car("Car", 4);
    array[2] = new Truck("Truck", 157);
    
    for(Vehicle v : array){
      System.out.println(v.getName());
      System.out.println(v.describe());
      System.out.println(v.move(10));
    }
  }
}
```

In this example, we are able to use an enhanced for loop to iterate over the objects in the array and call methods on each one. As long as those methods are defined in the `Vehicle` class, we can use them, no matter what type of object was instantiated and placed in the array. 

So, when we run this program, we'll see the following output:

![Java Screenshot with Output](/images/13-inherit/12.7.j.4.test2.png)

## Try It!

Polymorphism is a very powerful tool for object-oriented programmers. Feel free to modify the `Main` class open to the left, then compile and run the code for this example. See if you can create `Car` and `Truck` objects and store them in the `MotorVehicle` data type, then use the `honk_horn()` method!

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}