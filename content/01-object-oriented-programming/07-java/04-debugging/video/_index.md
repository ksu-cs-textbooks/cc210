---
title: "Java Debugging"
pre: "4.J. "
weight: 40
hidden: true
date: 2019-02-05T10:53:26-05:00
---

{{< youtube 1aeEZ4Z-jdc >}}

TODO Update Video

#### Resources

#### Video Script

One of the major frustrations when learning to write computer code is dealing with errors in your code. So, let's review a few common mistakes that you may encounter and how to solve them.

First, let's look at this simple program. See if you can spot the error!

Let's try to compile this program and see what output we get from the Java Compiler.

In this case, it tells us that it reached the end of the file while parsing. That means that it was looking for a particular symbol but couldn't find it. So, we need to carefully check our code, looking particularly for missing parentheses, curly braces, or quotation marks. In this case, we left out one of the last curly braces. So, we can add that back in, try to compile our program again, and it should work.

Here's another example. What is the error in this code?

Once again, the compiler will give us a helpful error message. This one is pretty easy - it not only tells us what we are missing, but where it needs to be placed in our code. So, we can make that quick fix and we're good to go.

Finally, let's look at an example of a runtime issue in Java. These are errors that won't be caught by the Java Compiler, but they'll cause problems when we try to execute our program. Here's the code we are starting with.

When we compile that code, it seems to work just fine. However, when we run the code, we get this error.

If we look at the code, we'll see that we left off the square brackets in the main method declaration. So, we can make that change, recompile our code, and it should work.

Of course, anytime you run into an error in your code, you should take some time to see if you can solve it yourself. If you really get stuck, don't be afraid to ask for help on Piazza. Especially when you are learning to code, there is a great chance that you'll run into an error that is difficult to solve by yourself, but we're always available to help!

Good luck completing this rest of this module!
