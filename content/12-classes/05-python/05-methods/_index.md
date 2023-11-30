---
title: "Methods"
pre: "5. "
weight: 50
---

<!-- {{% youtube Cd5sEy9Svsc %}} -->

<!--[Video Materials]({{<relref "./video">}}) -->

<!-- TODO Update Video -->

We can also add additional methods to our classes. These methods are used either to modify the attributes of the class or to perform actions based on the attributes stored in the class. Finally, we can even use those methods to perform actions on data provided as arguments. In essence, the sky is the limit with methods in classes, so we'll be able to do just about anything we need to do in these methods.

As with attributes, there are class and instance methods. Class methods have access to their parameters and class attributes, which the access via the syntax class_name.attribute_name.   Instance methods by convention have their first parameter as `self` and have access to their parameters, class attributes and their instance attributes (self.attribute_name).  Class methods are underlined on the UML diagram.

### Adding Instance Methods

To add a method to our class, we can simply add a method declaration inside of our class declaration. So, let's add the methods we need to our `Student` class:

```python
class Student:
  def __init__(self):
    self.name = "name"
    self.age = 19
    self.student_id = "123456987"
    self.credits = 0
    self.gpa = 0.0
    
  def birthday(self):
    self.age += 1
   
  def grade(self, credits, grade_points):
    current_points = round(self.gpa * self.credits)
    self.credits += credits
    current_points += grade_points
    self.gpa = current_points / self.credits

```

The `birthday()` method is pretty straightforward. When that method is called, we simply increase the age of this student by 1 year. However, since this an instance method, we need to add a parameter to the function at the very beginning of our list of parameters, typically named `self`. This parameter is automatically added by Python whenever we call an instance method, and it is a reference to the current _instance_ on which the method is being called. We'll learn more about this later. 

Therefore, instead of referencing the `age` variable directly, we are using `self.age` to access the _attribute_ `age` in the current _instance_ of the class. Whenever we want to access an _attribute_ of an instance in the definition of a class, we must use the variable `self` (or whatever is the first argument of the method) and a dot in front of it; otherwise, Python may complain that the attribute is not defined or behave in unexpected ways.

The `grade()` method is a bit more complex. As parameters, it accepts a reference to the current instance named `self`, a number of credits, and the grade points earned for a class; it then must update the `credits` and `gpa` attributes based on that new information. To do this, it must first calculate the current number of grade points the student has earned based on the current GPA, then update those values and recalculate the GPA. 

So, in short, whenever we create an _instance method_ while defining a class in Python, we'll always need to remember to add an extra parameter—conventionally named `self`—to the beginning of our list of parameters so that we can always have a reference to the current _instance_ of the class.

Note, no argument is passed for the `self` parameter when calling an instance method.  To add a grade to the Student object `Bob`, the syntax for calling `grade()` is `Bob.grade(3, 9)`.

### Adding Class methods

Let's add some class methods. In the class `Main`,  we note that it has a class-attribute `students` which is a list of `Student` objects.  We'll add a `main` method, create a student and add it to the list of students.

```python
from Student import *

class Main:
  students = []
  teachers = []

  @classmethod
  def main(cls, args):
    student1 = Student()
    cls.students.append(student1)
    # change name
    cls.students[0].name = "Mari"
    print(cls.students[0].name)
    #cls.students - a list of student-objects
    #cls.students[0] - a student-object stored at index 0
    #cls.students[0].name - the name attribute of a student-object stored at index 0
```

Here we create a student-object, add it to the class-list of students by using `cls.students`, then change its name.

{{% notice info "Variable Scope" %}}

We've already discussed variable scope earlier in this course. Recall that two different functions may use the same local variable names without affecting each other because they are in different scopes. 

The same applies to classes. A class may have an attribute named `age`, but a method inside of the class may also use a local variable named `age`. Therefore, we must be careful to make sure that we access the correct variable,  using the `self` reference if we intend to access the attribute's value in the current instance. Here's a short example:

```python
class Test:
  age = 15
  
  def foo(self):
    age = 12
    print(age)      # 12
    print(self.age) # 15
    
  def bar(self):
    print(self.age) # 15
    print(age)      # NameError
```

As we can see, in the method `foo()` we must be careful to use `self.age` to refer to the attribute, since there is another variable named `age` declared in that method. However, in the method `bar()` we see that `age` itself causes a `NameError` since there is no other variable named `age` defined in that scope. We have to use `self.age` to reference the attribute. 

So, we should always get in the habit of using `self` to refer to any attributes, just to avoid any unintended problems later on.

{{% /notice %}}

Let's go ahead and add the `promotion()` method to the `Teacher` class as well. That method should accept a single integer as a parameter (along with a parameter named `self` as the first parameter, of course), and then add that value to the Teacher's current salary. 

Use the first test below to check that we've included the correct methods in the `Student` and `Teacher` classes and `main` in `Main`. Then, use the second test to confirm that those methods work correctly. Each test below is worth 5 points in this module, for a total of 10 points. 
