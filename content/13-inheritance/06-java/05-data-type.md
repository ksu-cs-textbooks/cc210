---
title: "Data Type"
pre: "5. "
weight: 50
---

Of course, polymorphism can make things a bit more complicated when it comes to determining exactly what type of object is stored in a variable. Thankfully, Java includes a few easy ways to determine what type of object is really stored in a variable, as well as ways that we can convert the types if needed. 

## Determining Data Type

Let's go back to the previous example from the last page, where we had placed all of our objects in an array.

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

What if we'd like to call the `honk_horn()` method, but only if the object supports that method? To do that, we'll need to determine what type of object is stored in the variable, and then convert it, or _cast_ it, to a type that supports the `honk_horn()` method. So, we can update the code as shown below:

```java
public class Main{
  
  public static void main(String[] args){
    Vehicle[] array = new Vehicle[3];
    array[0] = new Airplane("Plane", 123, 45);
    array[1] = new Car("Car", 4);
    array[2] = new Truck("Truck", 157);
    
    for(Vehicle v : array){
      if(v instanceof MotorVehicle){
        MotorVehicle m = (MotorVehicle)v;
        System.out.println(m.honk_horn());
      }else{
        System.out.println(v.getName() + " can't honk!");
      }
    }
  }
}
```

Here, we are doing two very important operations. First, we are using `v instanceof MotorVehicle` to determine if the object stored in `v` can be stored in a variable using the `MotorVehicle` data type. So, for objects created from the `Car` and `Truck` classes, this operation will return `True` since both `Car` and `Truck` are child classes of `MotorVehicle`. 

Then, once we've determined that we can store the object in `v` as a `MotorVehicle`, we must convert it. To do that, we use the expression `(MotorVehicle)v`. This is called a _cast_ operation. To do this, we put the data type we'd like to convert the variable to in parentheses, directly in front of the variable to be converted. Then, we can store this result in a variable using the `MotorVehicle` data type.

As you may recall, we've done this before to convert numbers stored as integers to floating point numbers. 

It is important to note, however, that if we try to cast an object to a type that isn't allowed, we will get an exception. So, we'll either need to use an **If-Then** statement to confirm that we can make the conversion before attempting it, or use a **Try-Catch** statement and be prepared to catch an exception if it fails. 

## Try It!

Place the code above in the `Main` class and see what it does. Can you come up with any other programs that would require us to convert objects between types?
