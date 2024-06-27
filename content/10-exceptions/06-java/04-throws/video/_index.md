---
title: "Java Throw & Throws"
pre: "3.J. "
weight: 30
date: 2019-09-10T00:00:26-05:00
hidden: true
---

{{< youtube xJSxraNRqhk >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

Let's look at a couple more things related to exceptions in Java.

First, consider this program. We've seen code very similar to this many times throughout this textbook so far. Can you see what's missing?

It's pretty tough. Let's try to compile this code and see what happens. Uh oh! When we do, we'll get the following error about an unreported exception. This is because the FileNotFoundException is an example of a _checked exception_ in Java. Whenever our program includes code that could cause this error, we have to either place it in a **Try-Catch** statement, or declare that our code could throw that exception.

In this case, let's do the second option. To do this, we'll just need to include a **Throws Clause** after our main method declaration, but before the opening curly brace, right here. When we do this, we'll also need to import the appropriate module for the FileNotFoundException too. There! Now the compiler won't complain about this code when we try to compile it.

One question you may ask yourself is why we would ever do this, especially when we can catch and handle exceptions directly in our code. As we learn more about programming in Java, we'll see how to write our own methods. In that case, sometimes it is better to handle an exception outside of the method that caused it, so we'll want to be able to throw those exceptions outside of our method. That's what this is for.

We can also create our own custom exceptions in Java. This can be really helpful in some of our programs.

Consider the following program. It reads two floating-point numbers as input, then tries to divide the first number by the second number. If we recall our basic math training, we realize that we could cause an error if the second input is exactly 0, which would make our program divide by 0. While we could just let the program handle that exception, we can also throw our own exception with more information for the user.

To do that, we can simply replace this print statement with a new Exception. I chose to use the ArithmeticException here, since it is the one that best represents the type of error that is happening in this code. We can use any existing exception here, including the generic Exception type. As before, we'll need to import the correct module in order to use it.

There we go! Now we have a program that throws its own custom exception. Now our users will know exactly what the cause of the problem was, and we can customize the error message as needed to provide even more information to our users. Thankfully, since the ArithmeticException is not a checked exception, we don't have to add it to the `throws` clause in our main method declaration. It can be a bit confusing at first, but the compiler is very good about giving us helpful messages when we need to deal with checked exceptions.
