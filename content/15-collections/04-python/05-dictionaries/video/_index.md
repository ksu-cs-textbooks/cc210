---
title: "Python Dictionaries"
pre: "3.P. "
weight: 31
hidden: true
date: 2019-12-6T00:00:26-05:00
---

{{< youtube UAawcVBZgXc >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

The next collection we'll review is the dictionary, also known as the map. A dictionary is a collection that associates a key with a value. However, instead of arrays associating an array index with a value, a dictionary can use _any_ data type as the key as well as the value. Because of this, dictionaries are easily searchable by key, and are typically used to store and retrieve data quickly in a program.

To explore how we can use dictionaries in our program, this page includes a short problem statement. Basically, we want to assign a random number to any string received as input, but if we receive the same string again, we want to return the value that was previously assigned to that. A dictionary is a great data structure for this, since we can use the string as the key associated with the random number as its value.

So, let's begin by building our `get_output()` function. For this example, we'll provide a bit more context by showing the class and fields as well. This is because we are storing the dictionary as a static field in our class.

So, inside of our function, we must first determine if the input string is already stored in the dictionary as a key. So, we can use the `in` keyword, which will determine if the line is contained in the set of keys stored by the dictionary.

If so, we can just return the value stored in the dictionary using square brackets, providing the key as the index. This is very similar to how we use lists in Python.

However, if the dictionary doesn't contain an entry for the input string, we'll need to create a new one. First, we can generate a new random number using the `randint()` method of the `random` library.

Then, we can associate that value with the input string by looking up the index in the dictionary and setting it equal to a value. This is where lists differ from dictionaries. If we were using a list, we'd typically have to append a new value. However, for dictionaries, we can simply use the key inside of square brackets, and if we assign a value to it, a new entry is created in the dictionary. Pretty neat, right?

Finally, we can return the new random number we generated. If we see that input string again, our dictionary will now contain an entry for it that can be returned again.

That's all it takes to make a simple program to associated random numbers with inputs. See if you can complete it yourself!
