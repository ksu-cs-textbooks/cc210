---
title: "Access Modifiers"
pre: "3. "
weight: 30
---

Working with inherited classes also gives us an opportunity to learn about how data can be secured in the parent class so that any child class can easily access it, while still making it clear to external classes that these items should not be used.

![Vehicle UML Diagram](/images/13-inherit/12.7.j.uml.png)

## Protected Attributes

In Python, we've already seen how to implement a "private" variable.  Prefixing any attribute or method with two underscores `__` will make it difficult to access that item. This is because Python will automatically update the name of that item by adding the class name to it. Private attributes/methods of a super-class (parent) **are not directly accessible** to a sub-class (child). 

In most object oriented languages, there are "middle ground" access modifiers, more protected than "public" but less protected than "private".  One of these is literally called "protected" and noted on a UML class diagram with a `#`. Protected generally mean that the attribute or method should be available to child-classes, but not everyone.

Python has no language support for this level of access protection. However, by convention, Python developers add just a single underscore `_` in front of an item to indicate to other programmers that the "protected" level of access is intended.  It is up to other developers if they want to honor this decision.

So, we can use that method to mark items protected in our parent class, making them more easily identifiable to the child classes, while still making it clear to other classes that these items are internal and should not be accessed directly. 

In our UML diagram, we use the hash symbol `#` before an item to denote that it should be protected. So, we can update our `Vehicle` class to make the `speed` attribute protected:

```python
class Vehicle:
  
  def __init__(self, name):
    self.__name = name
    self._speed = 1.0
    
  @property
  def name(self):
    return self.__name
    
  def move(self, distance):
    print("Moving");
    return distance / self._speed;
  
  def describe(self):
    return ""
```

We'll also have to update the reference to the `speed` attribute in the `Airplane.move()` method.

Let's go ahead and update all of the items marked as protected in the UML diagram above in our code. Don't forget to look for any uses of those attributes as well, since they'll need to be updated, too. The test below will simply check the structure of the code to make sure we did it correctly.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}