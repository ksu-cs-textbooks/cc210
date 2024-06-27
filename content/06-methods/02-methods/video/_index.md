---
title: "Functions Overview"
pre: "1. "
weight: 10
date: 2019-09-23T00:00:26-05:00
hidden: true
---

{{< youtube 5LOXCJZAS40 >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

In this chapter, we're going to learn all about functions and how we can use them to break our programs up into smaller pieces of code that are easier to manage. Before we do that, we should first take a minute to define exactly what we mean by "function." For us, the best way to define a function is "a piece of code that can be executed as part of a program, which may return a value". We may also use the terms "method" and "subroutine" in a similar way, but for this chapter we'll just stick with "function" for now.

So, let's see how we could optimize our code to use a function. We can do this looking at some sample programs written in pseudocode, a fake programming language that should be pretty easy to read and understand if you already know a common programming language. For example, right now all of this program's code is contained in a single function, called "main". If you've been learning some languages such as Java or C, you may already be familiar with a main function, or main method, in your code. However, if you've been learning Python, this will be a bit new to you.

In this main function, the program does several things. Namely, it asks the user to input a name, then it prints the name with some fancy ASCII art around it. Then it does the same for the user's nickname, and a user ID.

If we look closely at this program, it appears that we are repeating several pieces of code. When we see this, it is a good indication that we should consider rewriting our code to avoid repetition.

One way we could do this is by using loops, which we've already seen in this course. However, since we are asking for 3 different inputs, the loop still becomes quite complex due to the use of several If statements to send the correct prompt to the user. Similarly, we aren't able to store the user's input in 3 separate variables, so we don't actually have a good way of handling that either.

Thankfully, there is a better way. One way would be to take each of those blocks of code and simply make them each their own function, like this. Then, in our main function, we can just run, or "call" those functions using the function name, followed by a set of parentheses. However, we haven't really simplified our program at all - in fact, it is even longer!

One way we can improve this program is by rewriting our functions to use a parameter. A parameter is an input value provided to a function from another part of the code when the function is "called". In this case, the main function reads input from the user, but then calls the prettyPrint function to actually print the user's input. When we call the prettyPrint function in main, we are giving it a variable in the parentheses. That variable is called an "argument", and it is stored in the "parameter" variable in the function. So, when we call prettyPrint with the name variable in parentheses as the argument, the input parameter in the prettyPrint function itself gets the value that is stored in the name variable in the main function. We'll talk about how that works later in this chapter.

We can even simplify this program further. In this instance, the function gets the prompt for the user as a parameter, and handles reading the input and printing it directly in the function. In effect, we've moved a repeated line of code from the main function to our new getInputAndPrint function. However, now the main function doesn't have access to the values input by the user.

So, we can use one more feature of a function, which is the ability to "return" a value back to the function that called it. Here, we are still giving the getInputAndPrint function an argument containing the prompt for the user, but now we are also returning that value at the bottom of the function. That value is then brought back to the main function, and can be stored in a variable. So, we can treat the function call as an expression that becomes a value, and store its returned value in a variable.

These are just a few of the ways that we can use functions in our code. In this chapter, we'll learn about many different ways we can improve our programs using this new technique.
