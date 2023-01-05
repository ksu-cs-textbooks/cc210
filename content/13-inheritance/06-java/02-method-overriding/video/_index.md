---
title: "Java Overriding"
pre: "3.J. "
weight: 30
hidden: true
date: 2019-11-03T00:00:26-05:00
---

{{< youtube Ap7rHHgDjyw >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

To help us better understand inheritance in our code, we'll look at another example, this time based on vehicles. This UML diagram shows different types of vehicles, both motor vehicles and airplanes. Then, we can also separate motor vehicles into both trucks and cars. Throughout the rest of this module, we'll explore the code needed to implement the program displayed in this UML diagram.

Let's look at the topmost parent class, Vehicle, first. By this point, we can quickly implement the attributes and methods in this class based on the UML diagram. There are a few new markings on the UML diagram that we haven't seen yet, but for now we'll just move ahead and learn about those when they become relevant.

So, in this class we've created a constructor that accepts a name as a parameter, and then stores the name in a private attribute. In addition, there is another attribute named speed, which we will simply set to 1.0 at this point.

The Vehicle class also includes two methods, move and describe. The move method accepts a distance as a parameter, and then prints a short message and returns the time it would take to move that distance. The describe method simply returns a string describing the vehicle.

Now, let's look at one of the child classes of Vehicle, Airplane. We can see at the top in the class declaration that we are using the `extends` keyword to show that the Airplane class inherits from Vehicle.

First, we can review the constructor for the Airplane class. It accepts three parameters, and uses those parameters to populate the attributes in the class. Notice that we are trying to set the name attribute on the first line of the constructor, which is actually declared in the Vehicle class as a private attribute. Will that work?

It turns out that it won't! If we try to compile this code, we'll receive this  error message. It also gives us another warning that we aren't able to instantiate a Vehicle object without proving a parameter. But wait! I thought we were instantiating an Airplane. What is going on?

As it turns out, we need to modify our code just a bit to make this work. When we instantiate a child class, we also must instantiate a version of the parent class.

Normally this is done automatically, but it can only be done if the parent class includes a default constructor that doesn't require any parameters. Since our Vehicle class's constructor requires a parameter, we'll need to do it manually.

So, we can use a special keyword `super` to access our parent class. If we call it like a method, it will execute the constructor of the parent class, and we can provide arguments for any required parameters. Instead of setting the name attribute directly, we can use the constructor for our Vehicle class to do it for us.

One important thing to note is that the call to the parent class constructor **must** be the very first line of code in the constructor of the child class. So, if we move it down to this position, it won't work and the code will not compile.

Next, let's look at how we can _override_ functions in our parent class, providing new functionality. First, we'll add a private function to our Airplane class to handle putting the landing gear up or down. We'll just have this function print out some messages to make it simple to understand.

Now, we can _override_ the `move()` method of the parent Vehicle class to make sure the landing gear is handled properly. To override a function in Java, we must do two things. First, the method declaration, also known as the method signature, must exactly match the one in the parent class. That means that the types and ordering of the parameters, the method name, and the return type must exactly match.

Then, we must also add the `@Override` method decorator above the method declaration. That tells the Java compiler that we are intending to override the method in a parent class, so we won't get any unwanted error messages.

We can also do the same thing with the `describe()` function, adding additional information about an Airplane to that function.

Of course, it is one thing to override a function in a child class, but we should also understand what that actually does, right?

So, let's look at this sample code in a main method that uses the functions we just overrode in our Airplane class. We can step through this code line by line to see how it works.

First, we have instantiated two objects, a Vehicle and an Airplane. So, when we call the `move()` method on our Vehicle object, it runs the code in the Vehicle class, and returns the value generated there.

Likewise, when we do the same for the Airplane object, we get the output from the code in our Airplane class.

The same goes for the describe method - the Vehicle class returns an empty string, while the Airplane class provides additional information.

Why is this important? We'll see this again in the next part of this module as we explore polymorphism. It becomes very useful there.

For now, see if you can do the same for the MotorVehicle class and its child classes.
