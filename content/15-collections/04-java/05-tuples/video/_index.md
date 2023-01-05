---
title: "Java Tuples"
pre: "4.J. "
weight: 40
hidden: true
date: 2019-12-6T00:00:26-05:00
---

{{< youtube geyyRmH-oIc >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

Finally, let's look at one other collection, called the tuple. A tuple is a very simple data structure that stores multiple pieces of data in the same object. Technically, a tuple is a "finite ordered list of values" but we can really think of it as a simple class or list of data. Some programming languages, such as Python, natively include tuples as part of the language. Sadly, Java does not, but it is very simple to build our own `Tuple` class. Let's look at how to do that by building a class that stores a `Tuple` of two ints.

Here is the starting point for the class. As we can see, it includes a field `first` for the first int...

and another field `second` to store the other one. The field names are really up to the developer, but I've found that these work well without conflicting with other methods or fields that we might be working with.

In addition, we've included a simple constructor that will set the value of each of these fields. This makes it quick and easy to create a tuple on just one line of code.

Since we are building our own class, there are a few other methods we should implement to make this class more useful. First, we'll want to provide an implementation of the `toString()` method to provide an easy to read version of the class for debugging. Tuples are typically printed in parentheses, with each element separated by a comma.

Likewise, we may want to implement the `equals()` method to help check for equality between two tuples. This is another method that is included in all Java objects by default. However, if we don't provide our own implementation for it, it will simply check to see if the objects are the same instance, and not if they store the same values. In this case, we want two tuples which store the same values to be considered equal, even if they are different instances. So, we can provide our own code for the `equals()` method.

First, notice that the `equals()` method must accept an `Object` as a parameter. This is because we could be provided any value, so we have to handle all possible cases.

First, the simplest case is to make sure the object provided is not `null`. If it is, we can just return false since it will definitely not be equal to our tuple.

Next, we can check and see if the object is exactly the same instance as our current object. Here we can use the `this` keyword and check to see if it is the same as the object given as a parameter. This is what the default `equals()` method does.

Next, we must check to see if the parameter is the same data type as our class. If it isn't, we know that they can't be equal, so we can return false.

However, if they are the same data type, we can then _cast_ the object to an IntTuple object.

Finally, we can check the values of each field in our object and the provided IntTuple object. If they are all the same, we can return true. If not, then the tuples are not exactly the same, and this line will return false. It seems a bit complex, but this is a very useful method as we'll see in our example.

So, now that we've built a tuple class in Java, let's look at a simple program to explore how it can be used. In this program, we're playing a simple guessing game. The program chooses a random location on a 10x10 grid, and we must guess a location. The program will respond with a cardinal direction, letting us know which way the hidden location is. In addition, it will let us know if we repeat a guess. So, let's see how we can build that.

Once again, we'll start by looking at the class itself. We have a few static fields to store our list of guesses, a random number generator, as well as the hidden location stored as a tuple.

So, first, we'll need to make sure our list of guesses has been initialized. If not, we can do that. Notice here that we are storing a list of `IntTuple` objects. That is the other handy thing about generics in Java: we can even store our own custom classes inside of collections.

We'll also check to see if our `Random` object has been initialized. If not, we'll quickly do that as well.

Finally, we'll check to see if we've selected a hidden location yet. If not, we'll make sure we do that using the random number generator to pick two random numbers and store them in a tuple.

Ok, now we are ready to process the guess given to us from the user. So, let's clear out this code and just look at the rest of the function to see how that work.

For starters, let's convert the two parameters to a tuple. So, we can instantiate a new `IntTuple` object, providing `x` and `y` as arguments to the constructor.

Then, we need to see if the guess is correct. Thankfully, we can use our handy-dandy `equals()` method to check and see if two tuples contain the same values. Notice that this _will not_ work if we don't write our own `equals()` method, since there is no way that the `guess` object will be the same instance as the `location` object we created earlier. That's one of the most powerful features we can build into our tuples.

If the guess isn't correct, we need to check and see if it is a repeat. So, we can use the `contains()` method of our `guesses` list to see if the guess is already stored there. Once again, this depends on the `equals()` method to determine if two tuples are the same, even if they aren't the same exact object. If we find it in our list, we can simply return "Repeat!"

So, at this point, we know that the guess is not correct, and it is not a repeat. So, we need to add it to our list of guesses using the `add()` method.

Then, we can figure out what the response should be. Thankfully, this program makes things simple for us: if it isn't on the same row, we can just return either "North" or "South". So, we can add a couple of if statements to check and see if the first part of the `guess` tuple is greater than or less than the `location` tuple's first component, and return the appropriate response.

Finally, if we know they are on the same row, we can do the same for the second component of both the `guess` and `location` tuples, responding with either "West" or "East".

There we go! We've learned all about how to use tuples in our programs, as well as lists and maps. See if you can complete all of the examples in this module before continuing. The project for this module will use all three to build an interesting take on a classic game!
