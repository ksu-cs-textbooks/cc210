---
title: "Java Getters & Setters"
pre: "9.J. "
weight: 90
hidden: true
date: 2019-09-24T00:00:26-05:00
---

{{< youtube diUJGAV0iiQ >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

Finally, we can also learn how to add special methods to our classes, typically called "getters" and "setters" that allow us to manipulate the value of instance attributes, even if they are private.

Here's a quick example. In the class Property, we've created a private attribute called `name`. In the UML diagram, we've also specified methods that allow us to get and set that value.

Let's add the `getName()` method first. This method is super simple - when we call it, it will simply return the value stored in the `name` attribute.

The `setName()` method is a bit more complex. For example, let's assume that we don't want to allow the name to be set to an empty string. In that case, we can add a quick If-Then statement to this method, checking to make sure the parameter provided is not empty, before we assign that value to the `name` attribute.

In Java, we traditionally use the terms `get` and `set` before the name of the attribute when naming these methods. However, that is just done by convention, and technically these methods could have any valid name we wish.

This process allows us to protect the name attribute, preventing it from being set to an empty string. If the attribute was public instead of private, it could be assigned to any value without the class having any control over that. By doing it this way, we're able to enforce our own rules.

What if we want to make an attribute read-only? In that case, we can just add a "getter" method, but omit the "setter" method.

Now that we have these methods, we can use them elsewhere in our code. For example, we can use the `getName()` method to get the value in the `name` attribute and store it in a variable.

Similarly, we can use the `setName()` method to update the value stored in that attribute, and then later use `getName()` again to retrieve it.

There we go! We've covered all sorts of useful techniques for building our own classes and objects in our programs. Later in this module, we'll do a full example program together, the biggest we've made so far, to see how everything could work together in larger program. Good luck!
