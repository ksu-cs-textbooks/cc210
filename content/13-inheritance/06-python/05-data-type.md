---
title: "Data Type"
pre: "5. "
weight: 50
---

Of course, polymorphism can make things a bit more complicated when it comes to determining exactly what type of object is stored in a variable. Thankfully, Python includes a few easy ways to determine what type of object is really stored in a variable, helping us know what methods and attributes are available. 

## Determining Data Type

Let's go back to the previous example from the last page, where we had placed all of our objects in a list.

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

What if we'd like to call the `honk_horn()` method, but only if the object supports that method? To do that, we'll need to determine what type of object is stored in the variable. So, we can update the code as shown below:


```python
from Car import *
from Airplane import *
from Truck import *
from MotorVehicle import *

class Main:
  
  @staticmethod
  def main():
    vehicles = []
    vehicles.append(Airplane("Plane", 123, 45))
    vehicles.append(Car("Car", 4))
    vehicles.append(Truck("Truck", 157))
    
    for v in vehicles:
      try:
        print(v.honk_horn())
      except AttributeError:
        print(v.name + " can't honk!")
       
# main guard
if __name__ == "__main__":
  Main.main() 
```

Here, we are doing two very important operations. First, we are using `isinstance(v, MotorVehicle)` to determine if the object stored in `v` is actually an object that is a `MotorVehicle` or one of its child classes. So, for objects created from the `Car` and `Truck` classes, this operation will return `True` since both `Car` and `Truck` are child classes of `MotorVehicle`. 

Then, once we've determined that we can treat the object `v` as a `MotorVehicle`, we can call methods and access attributes and properties that are available in the `MotorVehicle` class. We don't have to do anything else in Python for this to work.

It is important to note, however, that if we try to access a method, attribute or property that isn't available, we'll get an exception, the AttributeError. So use a **Try-Except** statement and be prepared to catch an exception if it fails.  You may wonder why you don't "look before you leap" with an **IF** and `isinstance()`.  It is not conventional in dynamically typed language to do so.

We can also inspect the type of an object in a more open-ended manner using the `type` function, which returns an object representing the argument's type, printed in the format `<class c>`, where `c` may be `'int'`, `'str'`, or the name of any other built-in or user-defined type. For example, `type(1) == int` would evaluate to `True`, and the Python interpreter would print the result of `type("Hello")` as `<class 'str'>`. However, this method of examining types doesn't allow us to recover any information about class hierarchies; the type returned is always the most specific applicable type, so we can't use `type` to see whether an instance of a given class can also be treated as an instance of some other class.

## Try It!

Place the code above in the `Main` class and see what it does. Can you come up with any other programs that would require us to check the types of objects?
