---
title: "Python Raise"
pre: "3.P. "
weight: 31
date: 2019-09-10T00:00:26-05:00
hidden: true
---

{{< youtube WTo7Xdrg0Ec >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

We can also create our own custom exceptions in Python. This can be really helpful in some of our programs.

Consider the following program. It reads two floating-point numbers as input, then tries to divide the first number by the second number. If we recall our basic math training, we realize that we could cause an error if the second input is exactly 0, which would make our program divide by 0. While we could just let the program handle that exception, we can also throw our own exception with more information for the user.

To do that, we can simply replace this print statement with a new exception. I chose to use the ValueError here, since it is the one that best represents the type of error that is happening in this code. We can use any existing exception here, including the generic Exception type.

There we go! Now we have a program that throws its own custom exception. Now our users will know exactly what the cause of the problem was, and we can customize the error message as needed to provide even more information to our users.
