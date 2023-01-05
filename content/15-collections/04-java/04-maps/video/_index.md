---
title: "Java Maps"
pre: "3.J. "
weight: 30
hidden: true
date: 2019-12-6T00:00:26-05:00
---

{{< youtube cprt3TVt_7c >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

The next collection we'll review is the map, also known as the dictionary. A map is a collection that associates a key with a value. However, instead of arrays associating an array index with a value, a map can use _any_ data type as the key as well as the value. Because of this, maps are easily searchable by key, and are typically used to store and retrieve data quickly in a program.

To explore how we can use maps in our program, this page includes a short problem statement. Basically, we want to assign a random number to any string received as input, but if we receive the same string again, we want to return the value that was previously assigned to that. A map is a great data structure for this, since we can use the string as the key associated with the random number as its value.

So, let's begin by building our `getOutput()` function. For this example, we'll provide a bit more context by showing the class and fields as well. This is because we are storing the map as a static field in our class, as well as our random number generator.

So, inside of our function, we must first make sure our map has been instantiated. If it hasn't, the value of that variable will be `null`, letting us know that we need to instantiate it. As we saw with the List data type earlier, we are using the parent Map class as the data type of the variable...

but we are using the HashMap implementation of the Map class when we instantiate the object. As before, the Map class is abstract and cannot be directly used, but it is a great choice for storing the object since it is the parent class of all map implementations.

In addition, we can use generics to indicate that we'd like the map to use strings as the data type for keys, but it will store integers as values. So, we'll place those both in angle brackets, separated by a comma as shown here.

We'll also need to make sure our `Random` object is instantiated. So, if that variable is `null` we can quickly instantiate a new `Random` object in our code.

Now, we'll need to determine if the input string is already stored in the map as a key. So, we can use the `containsKey()` method of the map to see if it contains an entry with that key.

If so, we can just return the value stored in the map using the `get()` method, providing the key as a parameter.

However, if the map doesn't contain an entry for the input string, we'll need to create a new one. First, we can generate a new random number using the `nextInt()` method of our `Random` object.

Then, we can associate that value with the input string using the `put()` method of our map. The key is the first parameter, and the value associated with it is the second parameter. Remember that if we try to use the same key twice, the value will be replaced.

Finally, we can return the new random number we generated. If we see that input string again, our map will now contain an entry for it that can be returned again.

That's all it takes to make a simple program to associated random numbers with inputs. See if you can complete it yourself!
