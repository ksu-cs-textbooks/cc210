---
title: "Attributes & Initialization"
pre: "4. "
weight: 40
---

<!--{{% youtube 9ZX2RBcsRfc %}}-->

<!--[Video Materials]({{<relref "./video">}})-->

<!-- TODO Update Video -->

Of course, our classes are not very useful at this point because they don't include any attributes or methods. Including attributes in a class is one of the basic uses of classes, so let's start there.  

##  Types of Attributes

There are two types of attributes: Class and Instance.

Class attributes are variables shared by all the instances (unique objects) in a class.  They are typically things like constants, or information about how many objects of the class exists. For example a Stop_Light class may have the class attribute `light _color = ['red', 'yellow', 'green']` to ensure all instances of Stop_Light use the same colors in the same order.  A more complex version of our Student class might have a list of all in-use student_ids to ensure they are all unique.

Class attributes are denoted on the UML diagram by underlining the attribute.  In our example the Main-class contains Class Attributes.

Instance attributes are variables that "belong" to the instance.  It makes sense that a Student-object owns its own name.

 You can see a better discussion of how each type of variable works at these links:
* [Python Class Attributes: An Overly Thorough Guide](https://www.toptal.com/python/python-class-attributes-an-overly-thorough-guide) from Toptal
* [Python Class](https://www.tutorialsteacher.com/python/python-class) from Tutorials Teacher

![UML Class Diagram showing Main, Student, and Teacher Classes, Attributes, and Methods](/images/12-class/11.4.classes.png)


## Class Attributes

Class attributes are added directly the class body.  In this case we use empty lists as the default values.

```python
class Main:
    students = []
    teachers = []
```
Class attributes are accessed by using the class_name.attribute (`Main.students`).

## Instance Attributes and the Initializer

To add an instance attribute to a class, we can simply place a variable assignment inside of a special method called the initializer.

```python
class Student:
    
    def __init__(self):
        self.name = "name"
        self.age = 19
        self.student_id = "123456987"
        self.credits = 0
        self.gpa = 0.0
```

There are a couple of things to note.  First the use of `__` to begin and end the method name.  Python uses this convention to identify methods, variable names, etc for which the Python interpreter has special uses. 

There is a default `__init__()` will run for all objects; its body is basically `pass`.  However, if the class definition **overrides** it, by including its own definition for `__init__()`, the class's definition is used.  Overriding a method is a type of polymorphism.

Next is the keyword `self`.  Python uses `self` to refer to the specific object accessing the code.  It is the mechanism that ensures the Student-object "Bob" sees Bob's data and the Student-object "Mari" sees Mari's data.  Whenever you see a method where the first parameter is `self`, it is an instance method.

To access an instance attribute, use the full name, `self.varible_name`.  

`self` is a Python specific implementation.  As a result, `self` will never be included in the UML parameter list for methods or used in the UML attribute names.  When the UML calls for instance methods/attributes insert self into the code.

{{% notice note "Try Not to Obscure" %}}

In Python the following is acceptable syntax.

``` python
class Example:
    name = "class"  # a class attribute
    
    def __init__(self):
        self.name = "instance"
        
    def method(self):
        name = "local"
        ...
```

It is unacceptable style.  In `method`, there are now three variables called 'name': 
* `name`, with a value if "local";
* `self.name`, with a value if "instance";
* `Example.name`, with a value of "class".

Code written in this style is difficult to read and understand, as such, avoid it.  

Note that it is common in `__init__` to see

```python
def __init__ (self, name):
    self.name = name

```

{{% /notice %}}

Later in this chapter we'll discuss ways that we can indicate to other developers that these attributes should or should not be accessed outside of this class. 

For now, let's go ahead and add the correct attributes and `__init__` methods in `Student.py`, `Teacher.py` and the class attributes in `Main.py` files. Feel free to refer to the UML diagram below to find the correct attributes for each class. For the items in `Main.py`, we'll just create an empty list using `[]` for now. 

