---
title: "Properties"
pre: "9. "
weight: 90
---

{{% youtube wwnD-Ih2yWs %}}

[Video Materials]({{<relref "./video">}})

So far in this chapter we've learned how to create private and public attributes in our classes. What if we want to create an attribute that is read-only, or one that only accepts a particular set of values? In Python, we can use a special decorator `@property` to define special methods, called _getters_ and _setters_, that can be used to access and update the value of private attributes. 

## Getter

In Python, a _getter_ method is a method that can be used to access the value of a private attribute. To mark a getter method, we use the `@property` decorator, as in the following example:

```python
class Property:
  
  def __init__(self):
    self.__name = ""    # create empty private attribute
    
  @property
  def name(self):
    return self.__name
```

In this class, the `name` attribute is private, so normally we wouldn't be able to access its value. However, we've created a method `name()` that acts as a _getter_ for the `name` private attribute. The decorator `@property` allows us to use that method as an attribute. In this way, the value of that variable can be accessed in a read-only fashion.

From other code, we can call that method by treating it just like an attribute called `name`:

```python
prop = Property()
name = prop.name
```

## Setter Methods

Similarly, we can create another method that can be used to update the value of the `name` attribute:

```python
class Property:
  
  def __init__(self):
    self.__name = ""    # create empty private attribute
    
  @property
  def name(self):
    return self.__name
  @name.setter
  def name(self, value):
    if not isinstance(value, str):
      raise ValueError("Name must be a string")
    if len(value) == 0:
      raise ValueError("Name cannot be an empty string")
    self.__name = value
```

In this code, we've added another `name()` method below the decorator `@name.setter` that can be used to update the value stored in the `name` attribute. We're also checking to make sure that the argument provided to the `value` parameter is a string, and is not an empty string. If it is, we can raise a `ValueError`, which would alert the user that this is not allowed. Of course, it would be up to the person writing the code that calls this method to properly catch and handle this exception. 

In our other code, we can then update that value just like we would any other attribute:

```python
prop = Property()
prop.name = "test"
```

## UML Class Diagrams

Getter and setter methods are displayed on a UML class diagram just like any other method. We use naming conventions such as `name()` and `name(value: str)` to make it clear that those methods are getters and setters for the attribute `name` of type `str`, as in this UML class diagram:

![UML Class Diagram with Properties](/images/12-class/11.6.p.9.propertyuml.png)

## Try It!

So, through the use of _getter_ and _setter_ methods, along with the `@property` decorators, we can either prevent other code from updating an attribute, or enforce restrictions on that attribute's values, without actually exposing the attribute. Here's a sample `main` class that demonstrates how to use these properties:

```python
from Property import *

class Main:
  
  @staticmethod
  def main():
    prop =  Property()
    name = prop.name
    print(name)
    prop.name = "test"
    print(prop.name)
    
    
if __name__ == "__main__":
    Main.main()
```
