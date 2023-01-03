---
title: "Python Security"
pre: "7.P. "
weight: 71
hidden: true
date: 2019-09-24T00:00:26-05:00
---

{{< youtube m5GaZDI8Xmw >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

As we build programs with code that can be stored in multiple files, it becomes more and more important to be able to restrict access to certain attributes or methods, protecting them from being accessed outside of the class. This helps us maintain the data integrity of anything stored in our classes, and also prevents us from making intended mistakes by accidentally changing values that we shouldn't change or calling methods that we shouldn't call.

Right now, we have two options that we can use: `public` and `private`. Anything that is marked `public` can be accessed outside of this class, while things that are marked `private` can only be accessed by code within the class.

In our UML diagram, we can denote public attributes and methods by placing a plus `+` symbol in front of them. Likewise, we can denote private items using a minus `-` symbol.

Most languages have a way to make items truly private, but Python does not. All methods and attributes in a Python class are public and accessible anywhere.

However, we can do one thing to make attributes and methods that we'd like to keep private a bit harder to access. To do this, we can simply add two underscores `__` before the name of any attributes or functions that we'd like to keep private. Again, they aren't truly private as we'll see in a minute, but at least they are a bit more protected.

Let's look at an example. On the left, we have the Security class we just updated. On the right, we'll add some code to a `main()` method in another class. First, we can create a new instance of the Security class. This is allowed in Python, even though the `__init__` method starts with two underscores. It is a special method that can always be accessed to instantiate a class.

Next, we can try to print the value of the `name` attribute. This is also allowed, since the `name` attribute in Security has not been modified and is public. Similarly, we are also allowed to call the `count()` method since it is public.

What if we try to access the `secret` attribute? We could try to access it using the new name, but if we do, we'll get a ValueError. The same thing will happen if we try to access the `reset()` method.

This is because Python adds an extra layer to the name of any attribute or method that starts with two underscores. To access them, we have to include the full name of the class as well as the name of the attribute or method, as shown here. So, while they aren't truly private, we have at least made it much more difficult to access those items accidentally.

As we can see, making attributes or methods private in Python is a very useful way to protect data and methods in our classes from being accessed accidentally. In a later video, we'll see how we can create some special methods to allow pseudo read-only or write-only access to certain attributes.
