---
title: "Multiple Inheritance"
pre: "7. "
weight: 70
---

Finally, we can also build classes that are able to inherit from multiple parent classes. In Python, this is done in a very straightforward way, but it comes with an important caveat.  

## The Diamond Problem

Before we can really understand the importance of multiple inheritance, we must first discuss the "Diamond Problem." This is a very common example in object-oriented programming, and it is used to describe one of the common pitfalls for multiple inheritance in programming.

Consider the following code, which defines 4 classes:

```python
class A:
  
  def do_something(self):
    pass
  
class B:
  
  def do_something(self):
    print("B")
    
class C:
  
  def do_something(self):
    print("C")
    
class D(B, C):
  
  pass

```

In this code, we are trying to inherit from both class `B` and `C` inside of `D`. So, we'll end up with a class hierarchy diagram that looks something like this:

![Diamond Problem Diagram](/images/13-inherit/12.7.x.7.diamond_wiki.png)[^1]

[^1]: File:Diamond inheritance.svg. (2018, September 25). Wikimedia Commons, the free media repository. Retrieved 02:42, November 4, 2019 from https://commons.wikimedia.org/w/index.php?title=File:Diamond_inheritance.svg&oldid=321823174.

The problem arises when we try to use the class `D`, as in this sample program (ignoring import statements for now):

```python
class Main:
  
  def main():
    obj = D()
    obj.do_something()
       
# main guard
if __name__ == "__main__":
  Main.main() 
```

In this example, we are calling the `do_something()` method on an object instantiated from class `D`. However, that method is defined in both `B` and `C`, which are parents of `D`. So, what version of the code should we use?

In this case, Python will look at the parent classes declared in `D`, and try to find a method named `do_something()` in each class in the order listed. So, since `D` inherits from `B` and `C`, in that order, Python will first determine if there is a method named `do_something()` in class `B`. Since there is, that is the code that will be executed.

Beyond that, multiple inheritance in Python is very straightforward. We can simply list any number of classes in parentheses as part of the class definition, and then Python will look through those classes in order when looking for the parent methods and attributes. This process also applies to any use of the `super()` method as well.

## Try It!

![Vehicle UML Diagram](/images/13-inherit/12.7.p.uml.png)

Let's see if we can update the `Vehicle` and `MotorVehicle` classes to be abstract, with an abstract definition for the `describe()` and `horn_honk()` method as well. The test below will simply check the structure of the code to make sure we did it correctly.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}