---
title: "Instance Methods"
pre: "4. "
weight: 40
---

We can also add additional methods to our classes. These methods are used either to modify the attributes of the class or to perform actions based on the attributes stored in the class. Finally, we can even use those methods to perform actions on data provided as arguments.  In essence, the sky is the limit with methods in classes, so we'll be able to do just about anything we need to do in these methods. Let's see how we can add methods to our classes.

As with attributes, there are class and instance categories. Class methods are underlined on the UML diagram and will be discussed in a later module. 

Instance methods by convention have their first parameter as `self`.  This provides access to instance features inside the method via the dot-notation (self.feature_name). 

## Adding Methods

To add a method to our class, we can simply add a method declaration inside of our class declaration. So, let's add the methods we need to our `Ingredient` class:

```python
class Ingredient:
    
    def __init__(self):
        self.name = "flour"
        self.amount = 2
        self.units = "cups"
    
    def toString(self):
        return "{:.2f}".format(self.amount) + " " + self.units + " of " + self.name
```

The `toString()` method is pretty straightforward. When that method is called, we simply return a string of `<amount> <units> of <name>`.  However, since this an instance method, we need to add a the parameter `self` to the very beginning of our list of parameters.This parameter is automatically added by Python whenever we call an instance method, and it is a reference to the current _instance_ on which the method is being called. 

Therefore, instead of referencing the `amount` variable directly, we are using `self.amount` to access the _instance attribute_ `amount` in the current _object_ of the class. Whenever we want to access an _attribute_ of an instance in the definition of a class, we must use the variable `self` (or whatever is the first argument of the method) and a dot in front of it; otherwise, Python may complain that the attribute is not defined or behave in unexpected ways.

So that we get consistent results, we used the formatting place holder `{:.2f}` to round the `amount` off to two decimal places.

{{% notice info "Variable Scope" %}}

We've already discussed variable scope earlier in this course. Recall that two different functions may use the same local variable names without affecting each other because they are in different scopes. 

The same applies to classes. A class may have an attribute named `age`, but a method inside of the class may also use a local variable named `age`. Therefore, we must be careful to make sure that we access the correct variable,  using the `self` reference if we intend to access the object's attribute's value in the current instance. Here's a short example:

```python
class Test:
  age = 15  # a class attribute
  
  def foo(self):
    age = 12
    print(age)      # 12
    print(self.age) # 15
    
  def bar(self):
    print(self.age) # 15
    print(age)      # NameError
```

As we can see, in the method `foo()` we must be careful to use `self.age` to refer to the attribute, since there is another variable named `age` declared in that method. However, in the method `bar()` we see that `age` itself causes a `NameError` since there is no other variable named `age` defined in that scope. We have to use `self.age` to object's reference the attribute, &lt;className&gt;.age to access the class's attribute.

{{% /notice %}}

For the `convert()` method, lets specify objects of type `Ingredient` must have units of "cups" or "ml" (milliliters).  As parameters, it accepts a reference to the current instance named `self`, and value for conversion units.  It must determine if a conversion is necessary.  If so, it must update the attributes `units` and `amount`.  There are 236.588 milliters in a cup.

```python
def convert(self, unts):
    if self.units == "cups":
        if unts == "ml":  
            self.units = "ml"
            self.amount *= 236.588
        else:
            pass  #if unts and self.units are the same do nothing
    else:
        ...
```

Let's go ahead and add the `scale()` method.  That method should accept a single float as a parameter (along with a parameter named `self` as the first parameter, of course). It should: (1) create a new object: (2) copy its object attributes to the new object, (3) scale the new object's `amount` by the scaling factor.  We'll leave this for you to do.  Remember to instantiate (create) a new object call it's 

![UML](/images/07-object/driver_ingr_2_UML.png)

## Test your work

Use the first test below to check that we've included the correct methods in the `Ingredient` class (3 points). Then, use the second test to confirm that those methods work correctly (7 points). 

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

{{% notice note "Try Not to be Obscure" %}}

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