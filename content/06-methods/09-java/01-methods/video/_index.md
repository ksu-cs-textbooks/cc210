---
title: "Java Functions"
pre: "3.J. "
weight: 30
date: 2019-09-23T00:00:26-05:00
hidden: true
---

{{< youtube F6YsCehtfS0 >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

Creating our own functions in Java is pretty easy. Let's look at this quick example function and explore each part of it.

First, we are using the `static` keyword at the beginning of our function declaration. We've already been doing this with our main function, since it allows us to run the function without creating an object first. In a later module in this class, we'll learn how to do that, but for now all of our functions will include the `static` keyword at the beginning of the function declaration.

Next, we have the `void` keyword. This second keyword gives the data type of the value that is being returned by the function. We are using a special keyword `void` to show that this function does not return a value. In a later video, we'll learn how to write functions that return values, but for now we'll stick with `void` here.

Next, we have the name of the function, `foo`. This name can be any valid identifier in Java, but functions are typically written in camel case starting with a lowercase letter. The function name `foo` is used in many textbooks as a simple example function name, so we'll continue to use that here.

Following the name of the function, we have a set of parentheses. These can be used to declare parameters for the function, which would be input values that must be provided when another part of the code wants to use this function. We'll see how to do that in a later video, so for now we'll just leave them blank.

Finally, we have a set of curly braces, and inside of them we see the code contained in the function. When this function is executed, it will execute the code contained inside of the curly braces, just like we expect.

The code also includes the `return` keyword, which is just there to denote the end of the function. However, since we aren't returning a value, it isn't required in this instance, but we've included it just to show that we can.

Now that we've seen how to write our own functions, what does it look like when we use them? Let's look at this quick example program to see how that works.

As with any program, we start in the `main` function. Every Java program must include at least one `main` function somewhere to show where the program should begin.

So, when we start the main function, the first line of code will print "Main 1" to the terminal.

Then, we get to a line that calls a function named `foo`. We can tell it is a function call because it is an identifier followed by parentheses. So, when our program sees that, it will look through the code for a function named `foo` and then execute it's code.

So, our program control goes to the `foo` function, and inside of that function it will print the text "Foo 1" to the terminal. Then, it reaches the `return` keyword, which exits the function. So, control goes back to the `main` function, which moves to the next line of code.

That line will print "Main 2" to the terminal. Then, the `main` function will call `foo` again. Mentally, we probably already know exactly what the `foo` function does, so when we see that function call in `main`, we can mentally just run that function quickly to see that it will print "Foo 1" to the terminal again, then return.

Finally, the `main` function will print "Main 3" to the terminal, and then return, which stops the program.

There we go! I hope that example helps you better understand what is going on in our code when we write and call our own functions. On this page, see if you can improve this sample program by adding another function.
