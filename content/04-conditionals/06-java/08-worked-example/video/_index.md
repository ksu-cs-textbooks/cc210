---
title: "Java Worked Example"
pre: "4.J. "
weight: 40
date: 2019-02-08T00:00:26-05:00
hidden: true
---

{{< youtube pTqSqh3gHos >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

Let's walk through the example on this page in depth to see how we can go from a simple problem statement to working code in Java.

The problem statement is shown here. In short, we want to build a program that will tell us if a year is a leap year or not. Sounds pretty simple, right?

According to the US Naval Observatory, here are the official rules for determining if a year is a leap year in the current calendar system we use, the Gregorian calendar. We'll pick this description apart a bit later to build the logic in our program.

So, let's get started. The first part of the problem statement directs us to build a program that will accept a positive integer that represents a year. So, in Java, we'll need to start with a class declaration and a main method declaration. Hopefully this part should be pretty familiar by now.

Next, we'll need to add the code for handling user input. So, we'll add the import statements at the top...

...and build our Scanner object in the code. This is the same code we just saw earlier in this chapter, so feel free to go back and copy-paste from that page if needed.

Oh! And don't forget to add the `throws Exception` statement at the end of the main method declaration.

This is the skeleton we'll use to build our program. The rest of the code we'll show in this video goes where the highlighted comment is in the skeleton code.

Ok, so now we can start building the program logic. From the problem statement, we want to read an integer that represents a year. So, we can create an integer variable named `year` and read input to it from our reader variable.

Next, we also need to deal with the fact that our program should only accept positive integers. We could, of course, depend on our users to only enter positive integers, but that's not a great way to go. Instead, let's add a quick check to our program that will confirm that the year is a positive integer. We can do this using an **If-Then-Else** statement, like so.

No we can start writing our program logic. Let's look at the three rules that determine if a year is a leap year individually. First, we know that any leap year must be divisible by 4. So, we can write another **If-Then-Else** statement to handle this rule.

Notice on the example I've simplified the output, just so it is readable in this format. Make sure you actually look at the required inputs and outputs in the problem statement when writing your solution to this example.

The next rule states that years which are divisible by 4 but also divisible by 100 are not leap years. So, we'll need to add an **If-Then-Else** statement inside the True branch of the first statement in order to make this work. The highlighted code shows where that could go.

Finally, we must amend that last rule a bit by stating that if the year is divisible by 400, it _is_ a leap year, even if it is divisible by 100 as in the previous rule. So, we'll need one more **If-Then-Else** statement. Where should it go?

If we look at our code, we want to adjust the part where the year is divisible by 100, so it would be this statement that we'll replace.

So, we can replace it with one final **If-Then-Else** statement that handles the case where the year is divisible by 400.

There we go! We've got our program up and running. Let's break it down one more time, just to see where each part goes.

We want to accept a positive integer...

If it is not divisible by 4, it isn't a leap year...

If it is divisible by 4 but not 100, it is a leap year...

If it is divisible by 100 but not 400, it is not a leap year. If it is divisible by 400, it is a leap year.

Hopefully this explanation helps you understand how this program was built. Make sure you remember to build and test it yourself as part of this unit before moving on. Good luck!
