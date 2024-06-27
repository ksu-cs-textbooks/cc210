---
title: "Python User Input"
pre: "3.P. "
weight: 31
date: 2019-02-08T00:00:26-05:00
hidden: true
---

{{< youtube WLOOldm9GJM >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

We've completed several projects that involve user input at this point, but we really haven't discussed how to build programs that can read input from the user, either via the terminal or from a file. Now that we've learned a bit about Python, let's take some time to review that code and explain how it works, so you can begin to use more user input in your programs.

Here is the sample code that we've already seen in several projects. Let's break it down and discuss what each part does.

First, in order to read input in Python, we need to import an additional library that are provided as part of the Python language. This class handles reading input from a file or the terminal, and then parsing that input into data types that we can use in our programs. We'll spend an entire chapter learning how to use libraries like this later in this course, but for now we'll just include the ones we need. So, at the top of every program where you'll be handling user input, you'll need to include this line. It should go at the very beginning, before any other code.

If you forget to include that line, the Python interpreter gives us a handy error message. If you see a message like this, most likely you forgot to include the import statement at the top of your code.

Now, let's look at the **If-Then-Else** statement. What we are doing here is checking to see if the user provided any command-line arguments to this program. If so, we'll assume that the argument was the name of a file we'd like to read input from. So, this first part of the statement checks to see if the length of the arguments list is greater than 1. If it is, we know that we can initialize our reader to read input from that file. In Python, the first argument is always the name of the program, so we have to check if there are _more_ than one argument to find any arguments provided by the user.

If the arguments list only contains a single item, we use the False branch to just initialize the reader to read from `sys.stdin`. The `sys.stdin` statement refers to the system terminal, which is typically called "Standard In" in many programming languages.

Finally, once we've created the reader, we can use it to read input. Thankfully, we can use the same cast methods we've already learned to convert the input read from the user into the primitive data types we're familiar with. This example shows how we could read a single integer from the input.

For reference, here are the methods we could use to read both an integer and a floating point number from the input. In a later chapter, we'll learn how to read entire sentences, or Strings, of data as well.

In summary, we really only have to add a few lines to our program to read input from the user, either via the terminal or from a file. I highly recommend learning this code very well, since you'll use it over and over again in your programs.
