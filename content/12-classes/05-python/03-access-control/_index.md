---
title: "Access Control"
pre: "3. "
weight: 30
---

{{% youtube m5GaZDI8Xmw %}}

[Video Materials]({{<relref "./video">}})

<p style="color:red; font-size:110%; padding:10">Note:  the practice of making class identifiers starting with `__` hard to call is called mangling. "Mangling" is a Python term,  not a generic coding term, and was originally introduced to prevent name-collisions (shadowing) in child classes.<br><br>The reason one can call `__init__()` is that the pattern `__name__` is used for Python language support elements.  The trailing `__`, overrides any mangling.</p>

As we work on developing our classes, we may want to protect data and methods stored in those classes. While Python doesn't include any security modifiers that enforce these restrictions, there are some conventions used in Python code to denote attributes and methods that should not be accessed outside the class. Let's review those and see how they work in our programs.

## Private Attributes and Methods

In Python, we can use two underscores `__` in front of the name of any attribute or method in the class to denote that it should be private. This will let other developers know that those attributes and methods should not be accessed from outside the class. 

Let's look at an example to see how this would work:

```python
class Security:
  
  def __init__(self):
    self.__reset()
    
  def count(self):
    return len(self.name)
  
  def __reset(self):
    self.name = "test"
    self.__secret = 123
```

In this class, we have created both a private and a public attribute, and a private and a public method. We can also see that we are able to call the private method `__reset()` from within our constructor, and in the `reset()` method we are able to access the `secret` private attribute without an issue. So, within our class itself, we don't have to worry about not being able to access anything we need.

However, outside of that class, they have a big impact on what we can easily access. Consider the following `main()` method from a different class:

```python
from Security import *

class Main:
  
  def main():
    some_security = Security()
    print(some_security.name)      # "test"
    print(some_security.__secret)  # AttributeError
    print(some_security.count())   # 4
    some_security.__reset()        # AttributeError
    
if __name__ == "__main__":
    Main.main()
```

In this code, we cannot access any private members of the `Security` class. So, when we try to run this code, we'll get the following error message:

```tex
Traceback (most recent call last):
  File "11p-classes/security/Main.py", line 13, in <module>
    Main.main()
  File "11p-classes/security/Main.py", line 8, in main
    print(some_security.__secret)  # AttributeError
AttributeError: 'Security' object has no attribute '_Main__secret'
```

As we can see, Python itself has a method for enforcing these security modifiers, making a very powerful way to limit access to the members and attributes in our classes. 

Unfortunately, Python does have a way to get around these restrictions as well. Instead of referencing `__secret`, we can instead reference `_Security__secret` to find that value, as in this example:

```python
from Security import *

class Main:
  
  def main():
    some_security = Security()
    print(some_security.name)               # "test"
    print(some_security._Security__secret)  # 123
    print(some_security.count())            # 4
    some_security._Security__reset()        # No errors
    
if __name__ == "__main__":
    Main.main()
```

Behind the scenes, Python adds an underscore `_` followed by the name of the class to the beginning of any class attribute or method that is prefixed with two underscores `__`. So, knowing that, we can still access those attributes and methods if we want to. Thankfully, it'd be hard to do this accidentally, so it provides some small level of security for our data. 

{{% notice note "Why Limit Access?" %}}

So, why would we want to do this? After all, if we're the ones writing the code, shouldn't we be able to access everything anyway? 

In many cases, the classes we are writing become part of a larger project, so we may not always be the ones writing code that interfaces with our class. For example, if we are writing an engine for a video game, we may want to make attributes such as the player's health private. In that way, anyone writing a mod for the engine would not be able to easily modify those values and cheat the system. Similarly, there are some actions, such as a `reset()` method, that we may only want to call from within the class. 

As we build larger and more complex programs, we'll even find that it is helpful as developers to limit access to just the methods and attributes that should be accessed by anyone using our classes, helping to simplify our overall program's structure. 

Limiting access is part of encapsulation, one of the pillars of object oriented programming.

{{% /notice %}}

## UML Class Diagrams

We can denote the access level of items in a UML class diagram using a few simple symbols. According to the UML standard, any item with a plus `+` in front of it should be public, and any item with a minus `-` in front should be private. So, we can build a UML class diagram showing the `Main` and `Security` classes as shown below:

![UML Class Diagram with Security](/images/12-class/11.6.p.6.secureuml.png)
