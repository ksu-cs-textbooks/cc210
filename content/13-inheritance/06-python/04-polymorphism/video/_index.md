---
title: "Python Polymorphism"
pre: "4.P. "
hidden: true
weight: 41
date: 2019-11-03T00:00:26-05:00
---

{{< youtube InU9BRjjKsg >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

As we discussed earlier, the true power of being able to create classes that inherit from others is polymorphism. So, let's explore what that looks like in Python.

Here is some simple code in a Main class that demonstrates polymorphism. Let's walk through it step by step and see how it works.

First, we instantiate an object from the Airplane class. However, we're going to treat it like an object of the Vehicle data type. This is polymorphism at work - our Airplane object can act like a Vehicle object.

So, as we step through the code, we can see that we are able to call methods declared as part of the Vehicle class. However, when we do, we notice that it is using the code from the Airplane class for methods that were overridden in Airplane, such as the `describe()` and `move()` methods.

We can do the same for an object instantiated from the Car class but treated like a Vehicle. It works exactly as we saw above.

So, we've seen that we can treat objects of a child class as objects of a parent class. When we do that, we can access any methods declared as part of the parent class, and it will even use the code from the child class if the method has been overridden.

Of course, since we are instantiating objects of the child class, we can always treat them like the class they were instantiated from. So, when we instantiate an object using the Car class, we can access the `honk_horn()` method as well.

So, there are a few rules for working with object and polymorphism that we should understand:

1. We can treat an object instantiated from any child class as an object instantiated from any parent of that class.
2. We can call methods and access attributes that are declared public in the class the variable is instantiated from, as well as any parent classes.
3. When we call methods that have been overridden, it will use the overridden code that is defined either in the child class, or the class nearest the child class in the inheritance hierarchy.

As we continue to work with inheritance and polymorphism in this module, we'll see these rules applied over and over again.

Let's review one more example. In this example, we are creating an Airplane, a Car, and a Truck, but storing them all in a list of objects. Since they are all child classes of the Vehicle class, we can treat each object as an instance of the Vehicle class, regardless of which class was used to create them. So, we can use a for loop to loop through the objects, calling methods on each of them directly. As before, we can use any method or attribute that is part of the Vehicle class, without knowing anything about the actual type of the object stored in that array element.

That's a quick overview of polymorphism in Python. Later in this module we'll do another worked example that relies very heavily on polymorphism to function properly.
