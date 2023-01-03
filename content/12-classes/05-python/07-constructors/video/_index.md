---
title: "Python Constructors"
pre: "6.P. "
weight: 61
hidden: true
date: 2019-09-24T00:00:26-05:00
---

{{< youtube ck_uPDPhaV8 >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

Another powerful feature of writing our own classes is the ability to have code automatically execute anytime a new object is created based on the class. This is done through a special method called a "constructor". Let's see how we can do that in Python.

First, we'll update the class UML diagram to include a constructors. Constructors typically look like methods, but they have a couple of special features. First, the name of the constructor method is always "__init__" in Python. Also, that method doesn't specify a return type, since the constructor itself doesn't actually return a value.

In code, we can create a constructor by declaring a special method that uses the name "__init__".

Inside of the parentheses, we can accept parameters as part of our constructor. However, we'll leave that blank for now, and add more parameters later. Since the constructor is just like any other class method, we will need to add a parameter for `self`.

There we go! This is what is called a "default constructor" for the class. It doesn't accept any parameters, and it doesn't do anything either. Since it is blank, we use the special keyword `pass` in Python to tell the Python interpreter that we meant to leave the constructor blank. Python actually adds this to our class by default if we don't include a constructor, just so we can always instantiate our classes.

However, a blank constructor is really pretty useless. So, let's add some code to it. For example, if we look at our class, we see that each attribute is given a default value. Instead of doing it where the attribute is declared, we can move those default values into the default constructor, like this.

Once we do, we can remove the attribute declarations from the top of the class. This makes our code a bit clearer and easier to follow. By doing so, we've changed our attributes from class attributes to instance attributes. The textbook discusses this difference in greater detail, and we'll learn a bit more about it later in this chapter.

Back in the Main class, when we use name of the class and a set of parentheses to instantiate an object, we are actually calling the class's constructor method. So, this is what actually executes the code we've defined in the constructor. Pretty handy!

We can also create a constructor that accepts parameters. It works exactly the same as any other class method declaration. Inside of the constructor, we still must use the `self` keyword to reference class attributes. So, this new constructor will accept parameters giving values for each attribute, and instead of setting the attributes to a set of default values, it can fill them in with the desired values given as arguments.

To make our constructor even more flexible, we can move the default values for each attribute to the parameter declarations. In that way, we can call the constructor with any number of parameters, and the ones we don't specify will be given default values.

So, if we want to use that constructor, we can simply use the name of the class, and then include arguments for each parameter inside of the parentheses. In this way, we have overloaded the constructor with multiple sets of parameters, just like we learned how to do with other functions in an earlier module.

As we can see in the comments after each line that prints output, we get the values we expect out of each attribute of the class, whether we've instantiated it using the default constructor or our own constructor that accepts default values. See if you can add the constructors needed in the Teachers class.
