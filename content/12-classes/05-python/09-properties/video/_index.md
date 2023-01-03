---
title: "Python Properties"
pre: "9.P. "
weight: 91
hidden: true
date: 2019-09-24T00:00:26-05:00
---

{{< youtube wwnD-Ih2yWs >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

Finally, we can also learn how to modify our attributes to be properties, providing methods for "getting" and "setting" the value of the attribute directly while enforcing certain rules if desired.

Here's a quick example. In the class Property, we've created a private attribute called `name`. In the UML diagram, we've also specified methods that allow us to get and set that value.

First, we can add the "getter" property. To do this, we create a method with the desired name, but use the `@property` decorator to tell Python that we wish to treat this method as a property. We'll see why that makes a difference later in this video.

The "setter" method is a bit more complex. First, we'll need to define another method with the same name as before, but this time it will accept a value as a parameter. We'll also decorate that method with the `@name.setter` decorator, showing that it is the "setter" method for the `name` property we defined earlier. Inside of the method, we can enforce some rules on the values that we'll accept for this property. For example, let's assume that it must be a string, but we don't want to allow the name to be set to an empty string. In that case, we can add a could of quick If-Then statements to this method, checking to make sure the parameter provided is a string and is not empty, before we assign that value to the `name` attribute.

This process allows us to protect the name attribute, preventing it from being set to an empty string. If the attribute was public instead of private, it could be assigned to any value without the class having any control over that. By doing it this way, we're able to enforce our own rules a bit.

What if we want to make a property read-only? In that case, we can just add a "getter" method, but omit the "setter" method.

Of course, these properties don't have to correspond directly to a single attribute, either. We can use them in many creative ways.

Now that we have defined a property, we can use it elsewhere in our code. Python allows us to treat a property just like any other attribute. So, instead of calling `name` like a method, we can just directly assign a value to it, as shown here.

Similarly, we can access the value stored in the property using the same syntax as we would for any attribute.

There we go! We've covered all sorts of useful techniques for building our own classes and objects in our programs. Later in this module, we'll do a full example program together, the biggest we've made so far, to see how everything could work together in larger program. Good luck!
