---
title: "Class Inheritance"
pre: "1. "
weight: 10
---

Now that we've learned a bit about the theory behind inheritance in object-oriented programming, let's dive into the code and see how we can accomplish this in Python. 

For these examples, we'll be implementing the following UML diagram:

![Vehicle UML Diagram](/images/13-inherit/12.7.j.uml.png)

Above is an example of a UML that is not Python specific.   For example in the class **Truck**, has a method `Truck(name:string, horsepower: float)`, in Python this would be a method `__init__(string ,float)`.

{{% notice note "Italics & Hash Symbols" %}}

The UML diagram above includes some items that we haven't discussed yet. Don't panic! We'll cover them as they become relevant in this module.

For now, feel free to ignore the fact that methods are italicized. Similarly, you can treat a hash symbol `#` in front of an attribute or method the same as a plus `+` that denotes they should be public. 

We'll learn what each of these indicate later in this module.

{{% /notice %}}

## Inheritance

The first step is to build the inheritance relationships. Let's start by just declaring the `Vehicle` class for now. Remember that the `Vehicle` class should be defined in `Vehicle.py`.  We won't add any methods or attributes at this point:

```python
class Vehicle:
  pass
```

As you'll recall, a class declaration is pretty simple. We'll include a `pass` keyword just to let Python know that we are intending to leave the class blank for now.

Next, let's declare the `MotorVehicle` class in `MotorVehicle.py`. This class inherits from the `Vehicle` class, so we'll need to use a new syntax to make that work:

```python
from Vehicle import *

class MotorVehicle(Vehicle):
  pass
```

In the example above, we've included the parent class `Vehicle` inside of parentheses after the name of the child class `MotorVehicle`. We also must remember to import the `Vehicle` class at the top of the file. That's all we need to do to show that a class inherits from another class.

Let's see if we can do the same process for the `Car`, `Truck`, and `Airplane` classes that are shown in the UML diagram above. We must make sure we place the code for each class in the correct file. Use the tests below to make sure that you have your classes structured correctly.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}