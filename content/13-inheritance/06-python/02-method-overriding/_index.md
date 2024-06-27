---
title: "Method Overriding"
pre: "2. "
weight: 20
---

{{< youtube dBwPhNSmBrg  >}}

[Video Materials]({{% relref "./video" %}})

Now that we've created some classes that follow different inheritance relationships, let's explore how we can use those relationships to change some methods in each class through the use of _method overriding_.

![Vehicle UML Diagram](/images/13-inherit/12.7.j.uml.png)

## `Vehicle` Class

First, let's look at a couple of methods in the `Vehicle` class, the `move()` and `describe()` methods. As we might recall, the `describe()` method is an _abstract method_ since it is in italicized text in the UML diagram. We'll discuss how to build an abstract method later in this chapter, but for now we'll just implement it as a normal method that does nothing. Likewise, we haven't discussed what a hash symbol `#` means in front of the `speed` attribute or the constructor, so we'll just make them public for now. 

```python
class Vehicle:
  
  def __init__(self, name):
    self.__name = name
    self.speed = 1.0
    
  @property
  def name(self):
    return self.__name
    
  def move(self, distance):
    print("Moving")
    return distance / self.speed
  
  def describe(self):
    return None
```

That's a very simple implementation of the Vehicle class. The `move()` method simply accepts a distance to move as a floating point number, and then divides that by the speed of the vehicle to get the time it takes to go that distance. For the default vehicle, we'll assume that it moves at a speed of 1.0. 


## Inheritance and Constructors

Now that we've created some methods in the Vehicle class, let's go back to the `Airplane` class and see how we can build it. First, we'll need to add the attributes and the constructor for this class:

```python
from Vehicle import *

class Airplane(Vehicle):
  
  def __init__(self, name, wingspan, capacity):
    self.__name = name
    self.__wingspan = wingspan
    self.__capacity = capacity
```

Before we go any further, let's stop there and run this code to make sure that it works. For starters, let's add some quick code to the `Main` class in `Main.py` that instantiates an Airplane object and tries to print the `name` attribute, using the property defined in the `Vehicle` class:

```python
from Airplane import *

class Main:
  
  @staticmethod
  def main():
    a = Airplane("Test", 123, 45)
    print(a.name)
    
# main guard
if __name__ == "__main__":
  Main.main()
```

Once we have that code, we can use the Python interpreter to run it. So, to do that, we can use the **Python - Run File** option in the run menu above with the `Main.py` file selected, or we can open the terminal in Codio and use the following two commands to open the directory containing these files and then execute Main:

```bash
cd ~/workspace/12p-inherit/vehicle
python3 Main.py
```

When we do that, we'll get some errors as shown in this screenshot:

![Python Interpreter Errors](/images/13-inherit/12.7.p.2.error.png)

In this error, it says that the `name` attribute in the `Vehicle` class doesn't exist. This is because we haven't actually called the constructor for the `Vehicle` class, so that attribute has not been defined yet. So, when we try to access the `name` property defined in the `Vehicle` class, it can't give us the value we want. This is because the `name` attribute in the `Vehicle` class is actually defined in the constructor for that class.

So, to set the value of the `name` attribute, we'll need to somehow provide that value to the constructor of the `Vehicle` class. But wait, why do we need to call the constructor and create a `Vehicle` object? Aren't we just trying to create an `Airplane` object?

One of the major things to recall when inheriting from a class is that each object instantiated from the child class is _also_ an instance of the parent class. We can think of it as though the child object _contains_ an instance of the parent object. Because of that, when we try to create an instance of the child class---`Airplane` in this example---that class's constructor must also be able to call the constructor for the parent class, or `Vehicle`.

We run into a snag, however, because we've provided a constructor in `Vehicle` that requires an argument. In that case, we **must** provide an argument to the constructor for `Vehicle` in order to instantiate that object, since the default constructor is no longer available. How can we do that?

Thankfully, there is a quick and easy way to handle this in Python. Inside of our constructor, we can use the special method `super()` to reference the parent class, allowing us to call that class's constructor---its `__init__()` method---directly. We can provide any needed arguments to that method call, which are then provided to the constructor in the parent class. So, let's update our constructor to use a call to `super().__init__()`:

```python
from Vehicle import *

class Airplane(Vehicle):
  
  def __init__(self, name, wingspan, capacity):
    super().__init__(name)
    self.__wingspan = wingspan
    self.__capacity = capacity
```

Now, inside of the constructor for `Airplane`, we have added the line `super.__init__(name)`, which calls the constructor of the parent class `Vehicle`, providing `name` as the argument for the parameter. This will resolve the error. We can try it for ourselves by running the code in the `Main` class again and seeing that it produces the correct output.

## Method Overriding
Finally, we can explore how to override a method in our child class. In fact, it is as simple as providing a method declaration that uses the same _method signature_ as the original method. A _method signature_ in programming describes the method name and the order of parameters defined in the function. So, we can override the `move()` and `describe()` methods in `Airplane` using code similar to the following:

```python
from Vehicle import *

class Airplane(Vehicle):
  
  def __init__(self, name, wingspan, capacity):
    super().__init__(name)
    self.__wingspan = wingspan
    self.__capacity = capacity
    
  def __landing_gear(self, set):
    if set:
      print("Landing gear down")
    else:
      print("Landing gear up")
  
  def move(self, distance):
    self.__landing_gear(False)
    print("Moving")
    self.__landing_gear(True)
    return distance / self.speed
  
  def describe(self):
    return "I am an airplane with a wingspan of {} and capacity {}".format(self.__wingspan, self.__capacity)
```

In this code, we see that we have included method declarations for both `move()` and `describe()` that use the exact same method signatures as the ones declared in `Vehicle`. 

## Calling Overridden Methods

To really understand how this works, let's look at a quick `main()` method that explores how each of these work. 

```python
from Vehicle import *
from Airplane import *

class Main:
  
  @staticmethod
  def main():
    vehicle = Vehicle("Boat")
    airplane = Airplane("Plane", 175, 53)
    print(vehicle.move(10))
    print(airplane.move(10))
    print(vehicle.describe())
    print(airplane.describe())
       
# main guard
if __name__ == "__main__":
  Main.main()
```

This code will simply call each method, printing whatever values are returned by the methods themselves. We must also remember that some of the methods may also print information, so we'll see that output before we see the return value printed. 

To run this code, we should see the following output:

![Screenshot Showing Successful Output](/images/13-inherit/12.7.p.2.test.png)

In this screenshot, we can see that calling the `move()` method on the `Vehicle` object just prints the message "Moving", while calling it on the `Airplane` object causes the messages about landing gear to be printed as well. This shows that our `Airplane` object is using the code from the overridden `move()` method correctly. 

In a later part of this chapter, we'll discuss polymorphism and how overridden methods have a major impact on the functionality of objects stored in that way. 

## Try it!

Let's see if we can do the same for the overridden methods in the `Truck` and `Car` classes. First, we'll start with this code for the `MotorVehicle` class:

```python
from Vehicle import *

class MotorVehicle(Vehicle):
  
  def __init__(self, name):
    super().__init__(name)
    self.number_of_wheels = 2
    self.engine_volume = 125
    
  def honk_horn(self):
    return ""
```

See if you can complete the code for the `Truck` and `Car` classes to do the following:

* `Truck.describe(self)` should return "I'm a big semi truck hauling cargo"
* `Truck.honk_horn(self)` should return "Honk"
* `Car.describe(self)` should return either "I'm a sedan" if it has 4 doors, "I'm a coupe" if it has 2 doors, or "I'm different" if it has any other number of doors
* `Car.honk_horn(self)` should return "Beep"

You'll also need to write the constructors for each class. Inside the constructor, you should store the parameters provided to the appropriate attributes.

The first test below will determine if your code is structured properly, and the second test will check the functionality of each method.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}