---
title: "Java Security"
pre: "7.J. "
weight: 70
hidden: true
date: 2019-09-24T00:00:26-05:00
---

{{< youtube 74s7zT2xKIY >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

As we build programs with code that can be stored in multiple files, it becomes more and more important to be able to restrict access to certain attributes or methods, protecting them from being accessed outside of the class. This helps us maintain the data integrity of anything stored in our classes, and also prevents us from making intended mistakes by accidentally changing values that we shouldn't change or calling methods that we shouldn't call.

Right now, we have two options that we can use: `public` and `private`. Anything that is marked `public` can be accessed outside of this class, while things that are marked `private` can only be accessed by code within the class.

In our UML diagram, we can denote public attributes and methods by placing a plus `+` symbol in front of them. Likewise, we can denote private items using a minus `-` symbol.

In code, it is as simple as placing the `public` keyword in front of all public items with the plus symbol in the UML diagram.

And the `private` keyword in front of items that should be private, as shown by the minus symbols in the UML diagram.

There we go! It is a very simple change to make, but it has very important consequences.

Let's look at an example. On the left, we have the Security class we just updated. On the right, we'll add some code to a `main()` method in another class. First, we can create a new instance of the Security class. This is allowed because we marked the constructor in Security with the `public` keyword. If it was marked `private`, we would not be able to instantiate the class.

Next, we can try to print the value of the `name` attribute. This is also allowed, since the `name` attribute in Security is marked `public`. Similarly, we are also allowed to call the `count()` method since it is public.

What if we try to access the `secret` attribute? In this case, since it is marked `private` in the Security class, the compiler will throw an error, preventing us from even compiling this code. The same thing will happen if we try to call the `reset()` method.

As we can see, using the `public` and `private` keywords is a very useful way to protect data and methods in our classes from being accessed when they shouldn't be. In a later video, we'll see how we can create some special methods to allow read-only or write-only access to certain attributes.
