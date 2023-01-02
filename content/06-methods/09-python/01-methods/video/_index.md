---
title: "Python Functions"
pre: "3.P. "
weight: 31
hidden: true
date: 2019-09-23T00:00:26-05:00
---

{{< youtube NNKPa8fLz9E >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

Creating our own functions in Python is pretty easy. Let's look at this quick example function and explore each part of it.

First, we are using the `def` keyword at the beginning of our function declaration. This keyword simply tells us that we are creating, or "defining" a new function.

Next, we have the name of the function, `foo`. This name can be any valid identifier in Python, but functions are typically written in lowercase, with multiple words separated by underscores. The function name `foo` is used in many textbooks as a simple example function name, so we'll continue to use that here.

Following the name of the function, we have a set of parentheses. These can be used to declare parameters for the function, which would be input values that must be provided when another part of the code wants to use this function. We'll see how to do that in a later video, so for now we'll just leave them blank.

Finally, we have colon, and below that line we have an indented block of code that tells us what the function should do. When we call the function, the code indented inside of the function declaration will be executed.

The code also includes the `return` keyword, which is just there to denote the end of the function. However, since we aren't returning a value, it isn't required in this instance, but we've included it just to show that we can.

Now that we've seen how to write our own functions, what does it look like when we use them? Let's look at this quick example program to see how that works.

In this example, we've also included both a `main` function and a special piece of code at the bottom called the "main guard." In all of our previous programs, we didn't worry about writing code in a main function, but instead just wrote the code directly in the file. However, now that we are building more complex programs, we should start using a `main` function in our code to help keep things organized. The main guard is a short piece of code that determines if this Python program is being run directly by the interpreter. If so, it calls the `main` function for us to start our program. As we'll see in a later chapter, we may also use this code as part of another program, so in that case we don't want it to execute itself.

So, when we run this program, the Python interpreter will skip past the function declarations and find the main guard, which will call the `main` function. Inside of the `main` function, the first line of code will print "Main 1" to the terminal.

Then, we get to a line that calls a function named `foo`. We can tell it is a function call because it is an identifier followed by parentheses. So, when our program sees that, it will look through the code for a function named `foo` and then execute it's code.

So, our program control goes to the `foo` function, and inside of that function it will print the text "Foo 1" to the terminal. Then, it reaches the `return` keyword, which exits the function. So, control goes back to the `main` function, which moves to the next line of code.

That line will print "Main 2" to the terminal. Then, the `main` function will call `foo` again. Mentally, we probably already know exactly what the `foo` function does, so when we see that function call in `main`, we can mentally just run that function quickly to see that it will print "Foo 1" to the terminal again, then return.

Finally, the `main` function will print "Main 3" to the terminal. Since there is no more code inside of the `main` function, it will terminate and the program will stop.

There we go! I hope that example helps you better understand what is going on in our code when we write and call our own functions. On this page, see if you can improve this sample program by adding another function.
