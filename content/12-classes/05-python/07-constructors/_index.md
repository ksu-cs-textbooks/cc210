---
title: "Constructors"
pre: "7. "
weight: 70
---

<!--{{< youtube ck_uPDPhaV8  >}} -->

<!--[Video Materials]({{% relref "./video" %}}) -->

<!-- TODO Update Video -->

On the last page, we created functions in the `Main` class to instantiate a `Student` and `Teacher` object and set the attributes for each object. However, wouldn't it make more sense for the `Student` and `Teacher` classes to handle that work internally? 

Thankfully, we can do just that by providing a special type of method in our classes, called a _constructor_ method.

## Constructors

A _constructor_ is a special method that is called whenever a new instance of a class is created. It is used to set the initial values of attributes in the class. We can even accept parameters as part of a constructor, and then use those parameters to populate attributes in the class. 

<p style="font-size:110%;padding:10">Technically, in Python one initializes an object by calling the <u>initializer</u>.  The differences between constructors and initializers are arcane and deal with how and when memory is allocated on the heap; your computer, no kidding, has a has a heap of memory. We are going to use and stick to the much more standard "constructor" terminology.   </p>


Let's go back to the `Student` class example we've been working on and look at our "constructor"  for that class:

```python
class Student:
  def __init__(self):
    self.name = "name"
    self.age = 19
    self.student_id = "123456987"
    self.credits = 0
    self.gpa = 0.0
  
  # other methods omitted

```

In this way, we can enforce the default attributes and values through the default constructor, without including them in the class declaration above, making the code a bit easier to read. 

With that constructor, we can then instantiate the class and see that the attribute values are set correctly:

```python
from Student import *

class Main:

  ...   
  def main(cls, args):
    some_student = Student()
    print(some_student.name) # "name"
    print(some_student.age)  # 19
  ...
```

So, constructors are a very easy way to help set initial values for attributes in a class. We can even call class methods directly from the constructor if needed to help with setup. 

## Constructors with Parameters

We can also create constructors that accept arguments. For example, we can create a constructor that accepts a value for each attribute as in this example:

```python
class Student:
  
  def __init__(self, name, age, student_id, credits, gpa):
    self.name = name
    self.age = age
    self.student_id = student_id
    self.credits = credits
    self.gpa = gpa

  # other methods omitted

```

Inside that constructor, the code looks very similar to the function we added to the `Main` class on the previous page. It will use each parameter to set the corresponding attribute, using the `self` variable once again to refer to the current object. 

However, this constructor will require us to include a value for each parameter in order to instantiate an object. What if we want to be able to instantiate an object without providing all of these values? To do that, we can include default values for each parameter, allowing us to call the constructor with some or all parameters omitted. Let's look at an example:

```python
class Student:
  
  def __init__(self, name="name", age=19, student_id="123456987", credits=0, gpa=0.0):
    self.name = name
    self.age = age
    self.student_id = student_id
    self.credits = credits
    self.gpa = gpa

  # other methods omitted

```

This example will assign a value to each attribute using the values provided as arguments to the constructor, or else the default values if some arguments are omitted. 

When instantiating an object with a constructor like this one, we can use keyword arguments to specify which parameters we are including, as shown below:

```python
a_student = Student(name="Jane", credits=15)
```

So, by including default values for each parameter in our constructor, we can create a very convenient way to instantiate our object containing attributes populated by any combination of default values and values provided by our code. 

## UML Class Diagrams

We can also add constructors to our UML class diagrams. A constructor is usually denoted in the methods section of a class diagram by using the `__init__` method name and omitting the return type. In addition, they are usually included at the top of the methods section, to make them easier to find:

![UML Class Diagram with Constructors](/images/12-class/11.6.p.5.constructuml.png)

The diagram above shows the `Student` and `Teacher` classes with constructors included. 

For UML not written specifically for Python, you will generally see the "constructor" syntax instead of an `__init__` method.  This syntax is a method with the class name as a method, so a `Student()` method in the Student class diagram.  

## Try It!

Now that we know how to use constructors, let's modify our working example to add the following constructors to both `Teacher` and `Student`:

* A constructor that accepts a parameter for each attribute, and uses those values to populate the object. Each parameter should be given a default value such that the constructor can optionally be called with no arguments or keyword arguments.

In Main change `new_student` and `new_teacher` so they call the constructor with the proper arguments-- hint each should contain 2 -lines, a call to the appropriate constructor and a line adding the new object to the correct list.

The example for `Student` has already been created above, but we'll have to figure out how to do the same for the `Teacher` class. 
