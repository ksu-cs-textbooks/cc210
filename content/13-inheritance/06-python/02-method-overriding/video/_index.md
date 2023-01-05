---
title: "Python Overriding"
pre: "3.P. "
weight: 31
hidden: true
date: 2019-11-03T00:00:26-05:00
---

{{< youtube dBwPhNSmBrg >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

To help us better understand inheritance in our code, we'll look at another example, this time based on vehicles. This UML diagram shows different types of vehicles, both motor vehicles and airplanes. Then, we can also separate motor vehicles into both trucks and cars. Throughout the rest of this module, we'll explore the code needed to implement the program displayed in this UML diagram.

Let's look at the topmost parent class, Vehicle, first. By this point, we can quickly implement the properties and methods in this class based on the UML diagram. There are a few new markings on the UML diagram that we haven't seen yet, but for now we'll just move ahead and learn about those when they become relevant.

So, in this class we've created a constructor that accepts a name as a parameter, and then stores the name in a private attribute. In addition, there is another attribute named speed, which we will simply set to 1.0 at this point.

The Vehicle class also includes two methods, move and describe. The move method accepts a distance as a parameter, and then prints a short message and returns the time it would take to move that distance. The describe method simply returns a string describing the vehicle.

Now, let's look at one of the child classes of Vehicle, Airplane. We can see at the top in the class definition that we are inheriting from the Vehicle class since it is included in parentheses after the name of the Airplane class.

First, we can review the constructor for the Airplane class. It accepts three parameters, and uses those parameters to populate the attributes in the class. Notice that we are trying to set the name attribute on the first line of the constructor, which is actually defined in the Vehicle class as a private attribute. Will that work?

It turns out that it won't! When we try to instantiate an Airplane object and then access the name property of the parent Vehicle class, we'll get an error! This is because the Airplane class is creating its own copy of the name attribute. When we try to use the name property from the Vehicle class, it can't access the name attribute stored in the child Airplane class. So, in our constructor for Airplane, how can we set the value of the private name attribute in the parent Vehicle class?

To do this, we can use a special keyword `super` to access our parent class. If we call it like a method, we can then access any constructors, methods or attributes in the parent class. So, instead of setting the name attribute directly, we can use the constructor for our Vehicle class to do it for us.

Next, let's look at how we can _override_ functions in our parent class, providing new functionality. First, we'll add a private function to our Airplane class to handle putting the landing gear up or down. We'll just have this function print out some messages to make it simple to understand.

Now, we can _override_ the `move()` method of the parent Vehicle class to make sure the landing gear is handled properly. To override a function in Python, the method definition, also known as the method signature, must exactly match the one in the parent class. That means that the types and ordering of the parameters, as well as the method name, must exactly match.

We can also do the same thing with the `describe()` function, adding additional information about an Airplane to that function.

Of course, it is one thing to override a function in a child class, but we should also understand what that actually does, right?

So, let's look at this sample code in a main method that uses the functions we just overrode in our Airplane class. We can step through this code line by line to see how it works.

First, we have instantiated two objects, a Vehicle and an Airplane. So, when we call the `move()` method on our Vehicle object, it runs the code in the Vehicle class, and returns the value generated there.

Likewise, when we do the same for the Airplane object, we get the output from the code in our Airplane class.

The same goes for the describe method - the Vehicle class returns an empty string, while the Airplane class provides additional information.

Why is this important? We'll see this again in the next part of this module as we explore polymorphism. It becomes very useful there.

For now, see if you can do the same for the MotorVehicle class and its child classes.
