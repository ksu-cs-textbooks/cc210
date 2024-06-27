---
title: "Polymorphism"
pre: "4. "
weight: 40
---

{{< youtube InU9BRjjKsg  >}}

[Video Materials]({{% relref "./video" %}})

<!-- TODO Update Video -->

<p style="color:red"><b>Note:</b> this video contains errors in the UML diagram, these errors have been fixed below.</p>

Now that we've learned how to build the structure needed for classes to inherit attributes and methods from other classes, let's explore how we can use those classes in our code.

![Vehicle UML Diagram](/images/13-inherit/12.7.j.uml.png)

## Polymorphism

Earlier, we defined _polymorphism_ as "the condition of occurring in several different forms"[^1]. In code, this allows us to create an object of a child class, and then use it just like an object from its parent class. Let's look at an example.

[^1]: https://www.lexico.com/en/definition/polymorphism


```python
from Car import *
from Airplane import *

class Main:
  
  @staticmethod
  def main():
    plane = Airplane("Plane", 123, 45)
    print(plane.name)
    print(plane.describe())
    print(plane.move(10))
    
    car = Car("Car", 4)
    print(car.name)
    print(car.describe())
    print(car.move(10))
       
# main guard
if __name__ == "__main__":
  Main.main() 
```

In this code, we are instantiating an `Airplane` object and a `Car` object, but we are treating them just like objects instantiated from the `Vehicle` class. This is polymorphism at work! Since both `Airplane` and `Car` are inheriting from the `Vehicle` data type, we can use any methods and access any attributes and properties that are available publicly from the `Vehicle` class. 

So, when we run this code, we'll get the following output:

![Python Screenshot with Output](/images/13-inherit/12.7.p.4.test1.png)

As we can see, even though we are calling methods defined in the `Vehicle` class, it is actually using the code from the methods that were defined in the `Airplane` and `Car` classes, respectively. This is because those methods are **overridden** in the child classes. 

What if we want to use the `honk_horn()` method of the `Car` object? Could we do that?

```python
car = Car("Car", 4)
print(car.honk_horn())
```

When we run that code, we'll see this output:

![Python Screenshot with Output](/images/13-inherit/12.7.p.4.test2.png)

Yup! That works too. So, even though we are able to treat them as `Vehicle` objects, we can still remember that this object is also a `Car` object, so we can use those methods as well.

So, when it comes to polymorphism, there are a couple of important rules to remember:

1. We can treat an object instantiated from any child class as an object instantiated from any parent of that class. 
2. We can call methods and access attributes that are declared public in the class the variable is instantiated from, as well as any parent classes.
3. When we call methods that have been overridden, it will use the overridden code that is defined either in the child class, or the class nearest the child class in the inheritance hierarchy. 

## Another Example

Here's another example of the power of polymorphism. In this case, we'll create a list that stores `Vehicles`, and fill that list with different types of vehicles. 

```python
from Car import *
from Airplane import *
from Truck import *

class Main:
  
  @staticmethod
  def main():
    vehicles = []
    vehicles.append(Airplane("Plane", 123, 45))
    vehicles.append(Car("Car", 4))
    vehicles.append(Truck("Truck", 157))
    
    for v in vehicles:
      print(v.name)
      print(v.describe())
      print(v.move(10))
       
# main guard
if __name__ == "__main__":
  Main.main() 
```

In this example, we are able to use a for loop to iterate over the objects in the list and call the same methods on each one. This will work as long as each object in the list has methods with the correct names, whether they appear in the object's class definition or are inherited from a parent class.

So, when we run this program, we'll see the following output:

![Python Screenshot with Output](/images/13-inherit/12.7.p.4.test3.png)

## Try It!

Polymorphism is a very powerful tool for object-oriented programmers. Feel free to modify the `Main` class open to the left, and then run the code for this example. See if you can create `Car` and `Truck` objects and store them in the `MotorVehicle` data type, then use the `honk_horn()` method!

