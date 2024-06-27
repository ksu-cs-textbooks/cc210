---
title: "Objects & Initialization"
pre: "2. "
weight: 20
---

<!--<iframe width="660" height="370" style="margin-bottom: 24px;" src="https://www.youtube-nocookie.com/embed/9ZX2RBcsRfc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> -- video does not match UML and class builr in woring order -->


Of course, our classes are not very useful at this point because they don't include any attributes or methods. Including instance attributes in an object class is one of the their basic uses, so let's start there.  

##  Types of Attributes

There are two types of attributes: Class and Instance.

Instance attributes are variables that "belong" to the instance.  It makes sense that a Student-object owns its own name.

We will deffer discussion of class attributes to a later module.

## Instance Attributes, the Initializer and `self`

To add instance attributes to a class, we can simply place a variable assignment inside of a special method called the initializer.  In Python, all instance attribute identifiers are prepended with the keyword `self`.

```python
class Ingredient:
    
    def __init__(self):
        self.name = "flour"
        self.amount = 2
        self.units = "cup"
        
```

Python uses `__` to begin and end method names, variable names, etc for which the Python interpreter has special uses. YOU CANNOT OVERRIDE THIS INTERPRETER BEHAVIOR.  Thus `__<anything>__` is effectively a another keyword in Python.

### `__init(self)__`

There is a default `__init__(self)` will run for all objects; its body is basically `pass`.  However, if the class definition **overrides** it, by including its own definition for `__init__(self)`, the class's definition is used.  Overriding a method is a type of polymorphism.

By convention, place all instance variables in `__init__`, even those for which we do not have default values.  This gives programmers one place to look for all the names of all the instance variables in the object.  Also, `__init__()` should always be the first method inside an object classes definition.

### `self`

Python uses `self` to refer to the specific object accessing the code.  It is the mechanism that ensures the Ingredient-object `first` sees `first`'s data and Ingredient-object `second` sees `second`'s data.  Whenever you see a identifier where the first part is `self.`, it is an instance attribute.

`self` is a Python specific implementation.  As a result, `self` will never be included in the UML parameter list for methods or used in the UML attribute names.  When the UML calls for instance methods/attributes insert self into the code.

```python
class Ingredient:
    
    def __init__(self):
        self.name = None
        self.amount = None
        self.units = None
```
#### Initializers and UML

`__init()__`, like `self`, is a Python specific thing.  You won't see them in standard UML class diagrams.  What you will see is a specification for a constructor; a method which
* always has the same identifier as the class
* may have parameters (which generally map to the instance variables)

When you see a constructor with parameters, add those parameters to the initializer; `self` must <b>always</b> be the first parameter to `__init()__`.  If you do not see a constructor, add an `__init__(self)`.  Remember, by convention all instance attributes are included in `__init()__`.

![Constructor UML example](/images/07-object/with_wo_UML.png)

The above translates into

```python
class With:
    
    def __init__(self, number1, number2):
        self.number1 = number1 # the value that comes in for the parameter is assigned
                               # to the attribute of the same name
        self.number2 = number2 # the value that comes in for the parameter is assigned
                               # to the attribute of the same name
    ...

class Without:
    
    def __init__(self):
        self.number1 = None    # lacking other guidance use None
        self.number2 = None    # lacking other guidance use None
        
    ...
```
{{% notice warning "Other Languages" %}}

Many other object oriented languages use a different keyword (`this`) instead of `self`, and by default its use is optional.

Because Python is a multi paradigm language, it requires more explicit syntax in certain areas.  <b>`self` is never optional in Python.</b>  To access an instance attribute inside of the class definition you must use the full name, `self.varible_name`.

{{% /notice %}}

{{< youtube nKbV2fbfT0w  >}}

<!-- TODO Update Video? -->

For now, let's go ahead and add the correct attributes and `__init__` methods in `Ingredient.py`.  Feel free to refer to the UML diagram below to find the correct instance attributes. You may set them to any default value wish.

![UML Class Diagram Ingredient](/images/07-object/ingr1_UML_py.png)

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}


