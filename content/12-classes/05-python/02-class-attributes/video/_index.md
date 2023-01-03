---
title: "Python Static"
pre: "8.P. "
weight: 81
hidden: true
date: 2019-09-24T00:00:26-05:00
---

{{< youtube T6aHU60uY2A >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

The next feature of classes we can learn about is static attributes and methods. Static class items are one of the more confusing things to understand when we first start building our own classes, but we'll try to explain it in detail in this video.

In short, a static class item is attached directly to the class itself, and not to any particular instance. Put another way, all instances of the class share the same value for a static attribute, and static functions can be called without instantiating an object first, since it is not attached to any particular instance of the class.

On a UML class diagram, any static items are underlined. In Python, we must handle static attribute and methods differently. To create a static attribute, also known as a class attribute, we must simply move the assignment of the variable to the class itself, outside of any constructors or methods. As you'll recall, this is originally how we were creating attributes in our classes before we learned to create constructors. Later in this video, we'll see how each of these approaches are different.

To create a static method, we must use the `@staticmethod` decorator above the method definition. When we do that, we can then remove the `self` parameter from the list of parameters, since this method will no longer be attached to a particular object. Finally, in the method itself, we may want to update the reference to the variable `x` to be `Stat.x` so we make sure we are accessing the class attribute `x` in each case.

Let's look at an example in code to see how this impacts how we interface with code. In this example, we've created a class called Stat that contains both a static attribute, `x`, and a normal class attribute, `y`. By default, the static value `x` is set to 5, while the value for `y` is set in the constructor to the parameter provided.

Now we can step through the code in the `main()` method to see what happens. First, we are instantiating a Stat object in the `some_stat` variable, giving it the value 7 to be stored in `y`. Since `x` is a static variable, we can just list that variable under the name of the class instead of the object.

Next, we'll create another instance of Stat called `another_stat`, giving it the value 8 to be stored in `y`. Again, since `x` is a static attribute, it does not change, and there isn't a second copy of that variable created, either.

Then, the program will print the values in `x` and `y` from both objects. We can look at the variable values on the bottom left of the slides to see what values would be printed. Notice that each object will print its own value for `y`, but the shared static value for `x` will be used in both cases.

Next, the program will update the value of `x` that is accessed through the Stat class to 10. Since `x` is a static attribute, this will actually update the value of `x` that is shared among all instances of the Stat class.

So, now when we print these values again, both `some_stat` and `another_stat` will report that `x` is now equal to 10. This it the power of static attributes - we can change it once, and it will apply to all instances of the object.

What happens if we update the value of the class attribute `x` that is attached to a particular instance, such as `some_stat`? In this case, Python does something a bit unique. When we update a class attribute by going through an object, Python will convert that class attribute to an instance attribute for just that object. So, now `some_stat` has its own entry for `x`, with the value 10. The class attribute is unchanged.

Once we've done that update, `some_stat` will now print 10 for the value of `x`, since it is an instance attribute. However, `another_stat` will still print 25, which is the value of the class attribute for Stat, since `another_stat` doesn't have an instance attribute named `x`.

I hope that helps explain how static class attributes and methods work a bit more clearly. It is one of the more confusing aspects of object-oriented programming at first, but as we work with more and more classes, hopefully become clearer over time.
