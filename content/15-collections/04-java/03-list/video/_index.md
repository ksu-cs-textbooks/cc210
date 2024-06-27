---
title: "Java Lists"
pre: "2.J. "
weight: 20
hidden: true
date: 2019-12-6T00:00:26-05:00
---

{{< youtube 8SXbDr0nZtQ >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

First, let's take a look at one of the most commonly used data structures from the Java collections library, the list. A list is a data type that can store any number of elements in a sequence. In addition, lists can be searched, elements can be removed, and lists are easily sortable. In Java, lists serve a similar function to arrays. The biggest difference is that arrays must be statically sized when we create them, whereas lists can grow and shrink as needed. Similarly, it is easy to remove an element from the middle of a list without leaving a gap, whereas the same action in an array requires shifting elements manually. Java includes two different types of lists, ArrayList and LinkedList. We won't get into the difference in this course, but it mainly has to do with performance. In a later class, we'll explore how to understand the differences between these two implementations of the list data structure.

On this page, we are given a simple program prompt to practice using lists in our program. In a nutshell, we want to generate a sequence of numbers known as the Fibonacci sequence up to a certain size. Then, if the size of the list is also contained in the list, we want to remove it. Finally, when we return the list, we should sort it in descending order.

So, lets explore how we can do that in our code. We'll start with a simple function definition for the `makeList()` function.

Inside, we'll need to declare a new list. At first glance, this line of code is very complex, so let's break it down a bit and discuss how it works.

First, we are using the abstract List class as the data type for our variable. The List class is a parent class to all implementations of a list, and includes all of the common list methods that we'll need to use. So, it is generally a good practice to store our lists in that data type, just to be flexible.

However, since the List class is abstract, we cannot directly initialize it. So, we'll need to pick an implementation of that class to use. In this program, we have chosen to use an ArrayList, but we can just as easily use a LinkedList and it would work in the same way.

Next, since the List class uses generics, we can declare the type of data we'd like the list to store as well. We'll place that inside of angle brackets as shown here. Also, even though we want our list to store integers, we cannot use the primitive `int` data type. Instead, we'll need to use the object `Integer` type. Thankfully, Java can automatically convert between the two for us in many instances, though a bit later we'll see one instance where it cannot do that directly.

Finally, we'll make sure the return type of the method matches the data type of our list. Again, we want to use the parent List class here, since we really don't care which implementation of a list we are using. So, any class that calls this method should simply know that it returns a list of integers.

Ok, once we have our list created, we can start by adding the first two numbers of the Fibonacci sequence, 0 and 1, to the list.

Then, we can generate the rest of the sequence using a for loop, which iterates from 2 through the size of the sequence desired according to the parameter `x`.

To calculate a new Fibonacci number, we must simply add the last two entries in the list. So, if we use `i` as our index, we want to get items `i-1` and `i-2` from the list, and then add them together to get the next number.

Once we have that number, we can simply append it back to the end of the list.

There we go! We've now generated the first `x` entries of the Fibonacci sequence. According to the problem statement, there are just two more things to do.

First, if the value `x` is in our list, we should remove it. In Java, we can just use the `remove()` method to do this. So, we can try to just remove element `x` from the list, right?

Unfortunately, this won't work.

This is because the list is storing `Integer` objects, but `x` is an `int`. The Java compiler recognizes that these are incompatible types, and gives us an error. So, how do we get around this?

Thankfully, we can simply _cast_ our parameter `x` to an `Integer` object, and then try to remove that from the list. That will work as intended. This is an example of one of the times that Java cannot automatically convert values between the primitive data types and their object counterparts.

What if `x` is not in the list? Will trying to remove it have any side-effects? Thankfully, if `x` is not inside the list, the `remove()` method won't do anything, and it won't throw an exception either. So, we don't have to worry about that.

Finally, we need to sort the list in descending order. To do that, we'll use a method from the `Collections` class called `sort()`. We can simply give that method the list as the first parameter, and optionally we can give it `Collections.reverseOrder()` as the second parameter to denote that we want the list sorted in descending order.

Once it has been sorted, we can return the list back to our program.

That's all there is to working with a list. As we can see, lists are a very flexible data type, and in many cases are just as easy to use as arrays, if not even easier. See if you can successfully complete this example on this page yourself!
