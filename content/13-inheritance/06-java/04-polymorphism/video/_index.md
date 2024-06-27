---
title: "Java Polymorphism"
pre: "4.J. "
weight: 40
hidden: true
date: 2019-11-03T00:00:26-05:00
---

{{< youtube OUoWtw785ss >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>


#### Video Script

As we discussed earlier, the true power of being able to create classes that inherit from others is polymorphism. So, let's explore what that looks like in Java.

Here is some simple code in a Main class that demonstrates polymorphism. Let's walk through it step by step and see how it works.

First, we instantiate an object from the Airplane class. However, notice that we are storing it in a variable declared with the Vehicle data type. This is polymorphism at work - our Airplane object can act like a Vehicle object.

So, as we step through the code, we can see that we are able to call methods declared as part of the Vehicle class. However, when we do, we notice that it is using the code from the Airplane class for methods that were overridden in Airplane, such as the `describe()` and `move()` methods.

We can do the same for an object instantiated from the Car class but stored in a Vehicle variable. It works exactly as we saw above.

So, we've seen that we can store objects of child classes in variables for the parent data type. When we do that, we can access any methods declared as part of the parent class, and it will even use the code from the child class if the method has been overridden.

However, what would happen if we store a Car object in a Vehicle variable, and then try to call the `honk_horn()` method. We know that the object stored in that variable is a Car, so it should work, right?

Unfortunately, it doesn't. Polymorphism only allows us to call methods that are declared based on the data type of the variable, even if the object stored in that variable supports those methods. Since the `honk_horn()` method isn't a part of the Vehicle class, we can't access it. So, this code will generate a compiler error.

Later in this module we'll learn how to determine what type of object is actually stored in a variable, and how to convert it to a compatible type so we can access those methods.

So, there are a few rules for working with object and polymorphism that we should understand:

1. We can store an object instantiated from any child class within a variable using the data type of any parent of that class.
2. We can only call methods and access attributes that are declared public in the class used as the data type of the variable, regardless of what type of object it stores.
3. When we call methods that have been overridden, it will use the overridden code that is defined either in the child class, or the class nearest the child class in the inheritance hierarchy.

As we continue to work with inheritance and polymorphism in this module, we'll see these rules applied over and over again.

Let's review one more example. In this example, we are creating an Airplane, a Car, and a Truck, but storing them all in an array of Vehicle objects. Then, we can use a for loop to loop through the objects, calling methods on each of them directly. As before, we can use any method or attribute that is part of the Vehicle class, without knowing anything about the actual type of the object stored in that array element.

That's a quick overview of polymorphism in Java. Later in this module we'll do another worked example that relies very heavily on polymorphism to function properly.
