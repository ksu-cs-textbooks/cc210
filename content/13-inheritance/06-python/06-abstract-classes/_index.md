---
title: "Abstract Classes"
pre: "6. "
weight: 60
---

{{< youtube X21IFfio_h0  >}}

[Video Materials]({{% relref "./video" %}})

<p style="color:red"><b>Note:</b> this video contains errors in the UML diagram, these errors have been fixed below.</p>


Another major feature of class inheritance is the ability to define a method in a parent class, but not provide any code that implements that function. In effect, we are saying that all objects of that type must include that method, but it is up to the child classes to provide the code. These methods are called _abstract_ methods, and the classes that contain them are _abstract_ classes. Let's look at how they work!

![Vehicle UML Diagram](/images/13-inherit/12.7.j.uml.png)

## Abstract

In the UML diagram above, we see that the `describe()` method in the `Vehicle` class is printed in italics. That means that the method should be abstract, without any code provided. To do this in Python, we simply inherit from a special class called `ABC`, short for "Abstract Base Class," and then use the `@abstractmethod` decorator:

```python
from abc import ABC, abstractmethod

class Vehicle(ABC):
  
  def __init__(self, name):
    self.__name = name
    self._speed = 1.0
    
  @property
  def name(self):
    return self.__name
    
  def move(self, distance):
    print("Moving");
    return distance / self._speed;
  
  @abstractmethod
  def describe(self):
    pass
```

Notice that we must first import both the `ABC` class and the `@abstractmethod` decorator from a library helpfully called `ABC`. Then, we can use `ABC` as the parent class of our class, and update each method using the `@abstractmethod` decorator before the method, similar to how we've already used `@staticmethod` in an earlier module. 

In addition, since we have declared the method `describe()` to be abstract, we can either add some code to that method that can be called using `super().describe()` from a child class, or we can simply choose to use the `pass` keyword to avoid including any code in the method.

Now, any class that inherits from the `Vehicle` class must provide an implementation for the `describe()` method. If it does not, that class must also be declared to be abstract. So, for example, in the UML diagram above, we see that the `MotorVehicle` class does not include an implementation for `describe()`, so we'll also have to make it abstract. 

Of course, that means that we'll have to inherit from both `Vehicle` and `ABC`, which we'll learn about in the next page. 

{{% notice info "Abstract Classes in Python" %}}

A class with one or more `@abstractmethod` declarations **cannot** be instantiated.  In our example, we cannot directly create a `Vehicle`.

``` python
if __name__ == "main":
    v1 = Vehicle()
```

```
~$ python3 Vehicle
TypeError: Can't instantiate abstract class a with abstract method describe
~$
```

This holds true for inherited methods

```python
class a(ABC):
  @abstractmethod
  def foome(self):
    pass

class b(a):
  def barme(self): 
    pass

if __name__ == "__main__":
  b1 = b()

```

running this code results in `TypeError: Can't instantiate abstract class a with abstract method foome`.

{{% /notice %}}

