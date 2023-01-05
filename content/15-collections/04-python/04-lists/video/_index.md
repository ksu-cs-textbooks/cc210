---
title: "Python Lists"
pre: "2.P. "
weight: 21
hidden: true
date: 2019-12-6T00:00:26-05:00
---

{{< youtube CRJcdyUDneI >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

First, let's take a look at one of the most commonly used data structures from the Java collections library, the list. A list is a data type that can store any number of elements in a sequence. In addition, lists can be searched, elements can be removed, and lists are easily sortable. In Python, we've already learned about lists, so this is not really that new to us. However, previously we would treat our lists as arrays, knowing the size of them ahead of time and not removing elements once they've been inserted, mainly to remain the same as other programming languages such as Java in this course. Now we can explore lists to their full potential!

On this page, we are given a simple program prompt to practice using lists in our program. In a nutshell, we want to generate a sequence of numbers known as the Fibonacci sequence up to a certain size. Then, if the size of the list is also contained in the list, we want to remove it. Finally, when we return the list, we should sort it in descending order.

So, lets explore how we can do that in our code. We'll start with a simple function definition for the `make_list()` function.

Inside, we'll need to define a new list containing the first two numbers of the Fibonacci sequence, 0 and 1.

Then, we can generate the rest of the sequence using a for loop, which iterates from 2 through the size of the sequence desired according to the parameter `x`.

To calculate a new Fibonacci number, we must simply add the last two entries in the list. So, if we use `i` as our index, we want to get items `i-1` and `i-2` from the list, and then add them together to get the next number.

Once we have that number, we can simply append it back to the end of the list.

There we go! We've now generated the first `x` entries of the Fibonacci sequence. According to the problem statement, there are just two more things to do.

First, if the value `x` is in our list, we should remove it. However, in Python, if we try to remove an element that is not in the list, the program will raise an exception. So, we'll need to first check to see if `x` is in the list.

If it is, then we can use the `remove()` operation to remove it.

Finally, we need to sort the list in descending order. To do that, we'll use the `sort()` operation, and provide an optional parameter `reverse=True` to denote that we'd like the list to be sorted in descending order.

Once it has been sorted, we can return the list back to our program.

That's all there is to working with a list. As we can see, lists are a very flexible data type that is easy to use. See if you can successfully complete this example on this page yourself!
