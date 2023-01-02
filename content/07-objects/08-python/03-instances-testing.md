---
title: "Instances & Testing"
pre: "3. "
weight: 30
---

Your class should now look something like this, although your default values may be different:

```python
class Ingredient:
    
    def __init__(self):
        self.name = "butter"
        self.amount = .25
        self.units = "cups"
```

As classes grow large you will want to test methods as you add them.  In CC 410 we will learn about test frameworks and will write formal tests in parallel with project development. 

For now we will follow the convention of a `__TEST(cls)` method.  The basic flow would be:

1. Create class
1. Write `__init__`, may be blank
1. Create `__TEST(cls)`, instantiate an object and test (print out) the initialized value to test for correctness.
1. Create `main(args)`, it should call `__TEST`
1. Run program (class)
1. Repeat until done:
1. Create new method
    1. Update `__TEST`, usually involves instantiating and object and using it to call the new method
    1. Run 


## Instantiation

To _instantiate_, or create, an object in Python, we call the class constructor, the method with name of the class[^1]

[^1]: if `__init__()` takes parameters other than `self` you provide them in the at this time:

```python
Ingredient()
```

When `Ingredient()` is called, it runs the `__int__()` method so all new objects start with attributes set up in `__int__()`. Of course, this line of code  will create a `Ingredient` object, but it won't store it anywhere. To store that object, we can create a new variable to which to assign the `Ingredient` object we created:

```python
ingr1 = Ingredient()
```

This will create a new `Ingredient` object, and then store it in a variable of type `Ingredient` named `ingr1`. While this may seem a bit confusing at first, it is very similar to how we've already been working with variables of types like `int` and `float`.

### Accessing Attributes

Once we've created a new object, we can access the instance _attributes_ as defined in the class from which it is created. 

For example, to access the `name` attribute in the object stored in `ingr1`, we could use:

```python
ingr1 = Ingredient()
n = ingr1.name # n is assigned the current value of
               # ingr1's name-attribute
print (n == ingr1.name) # prints True they are equal
```

Python uses what is called _dot notation_ to access attributes and methods within instances of a class. So, we start with an object created from that class and stored in a variable, and then use a period or dot `.` directly after the variable name followed by the attribute or method we'd like to access. Therefore, we can easily access all of the attributes in an `Ingredient` object using this notation:

```python
ingr1 = Ingredient()
print(ingr1.name)
print(ingr1.amount)
print(ingr1.units)
```

We can then treat each of these attributes just like any normal variable, allowing us to use or change the value stored in it:

```python
ingr1 = Ingredient()
print(ingr1.name)
print(ingr1.amount)
print(ingr1.units)

n = ingr1.name
ingr1.name = "cardamom"
print (n == ingr1.name) # False they are not equal we changed ingr1.name
```

## How to test

When testing it is important to avoid "feature creep" in the class.  We want to avoid adding attributes or methods that are not called for by the UML class diagram.  In software development you will drive up test and maintenance cost[^3].

[^3]: Software <a href="https://galorath.com/software-maintenance-costs/#:~:text=SOFTWARE%20MAINTENANCE%20COST%20DEFINED&text=Software%20maintenance%20costs%20will%20typically,20%25%20of%20software%20maintenance%20costs)">maintenance</a> is estimated to be 60 - 75% of the total cost of ownership for a software project.

In this class it is always acceptable to add a `__TEST(cls)` and a `main`.  This is an exception to the rule that the program must match the UML.  So we will put all our test code <b>for instance classes</b> in a `__TEST` method.


```python
import sys
class Ingredient:
    
    def __init__(self):
        self.name = "butter"
        self.amount = .25
        self.units = "cups"
    
    def __TEST(cls)():
        test_obj = Ingredient()  # create an Ingredient object and assign it to test_obj
        print(test_obj.name)     # print out attributes
        print(test_obj.amount)
        print(test_obj.units)

    def main(args):
        Ingredient.main(sys.argv))        

if __name__ == "__main__":
```

This is how one might test an `__init__` method.

Things to keep in mind for this course:
* YOU need to know what the answer (print out) should be
* Never use input (keyboard or file) in your test code
  * Hard code the values you want to test with
* Consider deleting `__TEST` before submission
* Consider deleting `__TEST`'s contents after testing each method
  * You can continue to append to the end but it makes for a long program