---
title: "Python Tuples"
pre: "4.P. "
weight: 41
hidden: true
date: 2019-12-6T00:00:26-05:00
---

{{< youtube 1ErzWJlvl0M >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

Finally, let's look at one other collection, called the tuple. A tuple is a very simple data structure that stores multiple pieces of data in the same object. Technically, a tuple is a "finite ordered list of values" but we can really think of it as a simple class or list of data. Some programming languages, such as Java, do not include support for tuples directly in the language. Python, thankfully, does include tuples, so let's learn how to use them in our code.

Let's look at a simple program to explore how it can be used. In this program, we're playing a simple guessing game. The program chooses a random location on a 10x10 grid, and we must guess a location. The program will respond with a cardinal direction, letting us know which way the hidden location is. In addition, it will let us know if we repeat a guess. So, let's see how we can build that.

Once again, we'll start by looking at the class itself. We have a couple of static fields to store our list of guesses as well as the hidden location stored as a tuple.

So, first, we'll need to check to see if we've selected a hidden location yet. If not, we'll make sure we do that using the random number generator to pick two random numbers and store them in a tuple. Notice that we are simply creating two random numbers, and putting a comma between them to indicate that they should be part of a tuple.

Ok, now we are ready to process the guess given to us from the user. For starters, let's convert the two parameters to a tuple. Once again, we can simply list the variable with a comma between them to create a tuple.

Then, we need to see if the guess is correct. Thankfully, Python allows us to use the double equals sign `==` to check if two tuples contain the same values. That's one of the most powerful features we of tuples, since we don't need to check each element individually. If it is correct, we can simply return "Found!" from our function.

If the guess isn't correct, we need to check and see if it is a repeat. So, we can use the `in` keyword to check our `guesses` list to see if the guess is already stored there. If we find it in our list, we can simply return "Repeat!"

So, at this point, we know that the guess is not correct, and it is not a repeat. So, we need to add it to our list of guesses using the `append()` method.

Then, we can figure out what the response should be. Thankfully, this program makes things simple for us: if it isn't on the same row, we can just return either "North" or "South". So, we can add a couple of if statements to check and see if the first part of the `guess` tuple is greater than or less than the `location` tuple's first component, and return the appropriate response.

Finally, if we know they are on the same row, we can do the same for the second component of both the `guess` and `location` tuples, responding with either "West" or "East".

There we go! We've learned all about how to use tuples in our programs, as well as lists and maps. See if you can complete all of the examples in this module before continuing. The project for this module will use all three to build an interesting take on a classic game!
