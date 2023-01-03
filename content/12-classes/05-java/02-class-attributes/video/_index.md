---
title: "Java Static"
pre: "8.J. "
weight: 80
hidden: true
date: 2019-09-24T00:00:26-05:00
---

{{< youtube iAi_LIWyU_c >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

The next feature of classes we can learn about is static attributes and methods. Static class items are one of the more confusing things to understand when we first start building our own classes, but we'll try to explain it in detail in this video.

In short, a static class item is attached directly to the class itself, and not to any particular instance. Put another way, all instances of the class share the same value for a static attribute, and static functions can be called without instantiating an object first, since it is not attached to any particular instance of the class.

On a UML class diagram, any static items are underlined. In Java, we simply must add the `static` keyword to those items. The `static` keyword must be placed after any security modifiers such as `public` or `private`, but before the data type of an attribute or the return type of a method. That's really all that changes in code when we convert items to static items.

Let's look at an example in code to see how this impacts how we interface with code. In this example, we've created a class called Stat that contains both a static attribute, `x`, and a normal class attribute, `y`. By default, the static value `x` is set to 5, while the value for `y` is set in the constructor to the parameter provided.

Now we can step through the code in the `main()` method to see what happens. First, we are instantiating a Stat object in the `someStat` variable, giving it the value 7 to be stored in `y`. Since `x` is a static variable, we can just list that variable under the name of the class instead of the object.

Next, we'll create another instance of Stat called `anotherStat`, giving it the value 8 to be stored in `y`. Again, since `x` is a static attribute, it does not change, and there isn't a second copy of that variable created, either.

Then, the program will print the values in `x` and `y` from both objects. We can look at the variable values on the bottom left of the slides to see what values would be printed. Notice that each object will print its own value for `y`, but the shared static value for `x` will be used in both cases.

Next, the program will update the value of `x` that is accessed through `someStat` to 10. Since `x` is a static attribute, this will actually update the value of `x` that is shared among all instances of the Stat class.

So, now when we print these values again, both `someStat` and `anotherStat` will report that `x` is now equal to 10. This it the power of static attributes - we can change it once, and it will apply to all instances of the object.

In fact, as we can see on this line, we can even set the value of `x` directly using the name of the class Stat as an object. Since `x` is static, we don't even need to instantiate an object to access or change that value.

Once we've done that update, both `someStat` and `anotherStat` will show that `x` is now equal to 25.

I hope that helps explain how the `static` keyword works a bit more clearly. It is one of the more confusing aspects of object-oriented programming at first, but as we work with more and more classes, hopefully become clearer over time.
