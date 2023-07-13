---
title: "Java Example"
pre: "4.J. "
weight: 40
date: 2019-02-08T00:00:26-05:00
hidden: true
---

{{< youtube fTKunowqEpM >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

Let's walk through a full example to show how we can build a program using loops that fulfils a specific need.

Here's our problem statement. Basically, we'd like to allow our user to input a series of integers, and we'll calculate the sum and average of all of the positive integers entered until the user inputs 0. If the user inputs a negative number, we'll print an error.

So, let's see how we'd build this program. First, we'll need to start with our program skeleton that handles user input. We've seen this several times before. For the rest of this video, we'll be writing code that is placed where this highlighted comment is in our skeleton code.

Now, let's break down our problem statement and see if we can build our program. First, we need to accept a series of inputs from the user, but we don't know how many. So, we'll probably want to use a while loop here, since we can simply have the program repeat while a specific condition is true.

Inside of that loop, we'll read an input from the user, and store it in a variable named `x`.

We also know that we should read input until the user inputs 0, so we can use that to build our while loop's Boolean expression. So, as long as the user's input is not 0, we want to keep repeating.

However, this causes a couple of issues. First, we haven't declared the variable `x` before the loop, so we'll need to fix that in order for our program to work properly. Next, we'll also need to assign it some value by default. Normally, we might consider using 0 as a good default value. However, since the while loop will only repeat if the user's input is NOT 0, we should probably use some other value. So, let's use 1 instead.

Moving on, we want to deal with the case where the user inputs a negative value. This is pretty simple; we'll just need to add an If-Then statement inside of the while loop. If the user inputs a negative value, we'll just print our error message and use the continue keyword to restart the loop.

Next, we need to deal with the program logic. First, we'll want to keep track of the sum of the integers. So, we can add a sum variable at the beginning, and then update that variable with the value of the user's input each time the loop code repeats. Finally, we can print that result at the end.

The average is a bit different. We know that the average of a set of numbers is just the sum divided by the count. Since we are already keeping track of the sum, we just need to add a variable to keep track of the count. At the end, we can divide the sum by the count when we produce our output, which will be the average of the numbers input by the user.

So, that covers it, right?

Unfortunately, this code contains a very important LOGIC BUG! Can you spot it?

Let's walk through this code with some simple inputs to see where the bug is.

First, let's set the initial values of our variables. Then, we'll enter the loop since `x` is not 0.

Inside of the loop, we'll get input from the user. In this case, let's assume the user inputs the number 3. Since that is positive, we'll bypass the If-Then statement. Below, we'll update the values of the sum and count variables accordingly.

Now, we'll repeat the loop again, since the user did not input 0. This time, let's say the user inputs 1. So, once again, we'll bypass the error message, and update the values of `sum` and `count` once again.

On the next loop, let's assume the user inputs 0. This time, we'll still bypass the error message. However, when we update the variables, we'll see that the count variable is increased by 1!

Uh oh! When that happens, it makes the average 1.333 instead of 2. So, our program is counting the last 0 as part of the input, which is not what we want it to do.

So, how could we solve that? It turns out that there are multiple solutions. First, we could wrap the code that updates those variables in another If-Then statement, just to make sure that `x` is not 0 when we update those variables.

Similarly, we could add another If-Then statement to the top, and use the `break` keyword to get out of the loop if the user inputs a 0.

We can also rearrange the code just a bit. Here, we are reading input from the user before we enter the while loop. Then, inside of the while loop, we update the variables before reading another input at the bottom, before looping over. Notice that we also had to remove the `continue` keyword, since it would prevent us from reading a new input at the bottom. Sadly, however, this code does have a couple of repeated lines, namely the line that reads input from the user, so it may not be a preferred solution.

Finally, we can also restructure the code a bit more to use an If-Else If structure like this. In this case, we can just use a "while-true" loop as well, since we are including a `break` statement in the code.

In short, there are always many different solutions and approaches you can take in your code when writing a program. The important part is to choose an approach that you are familiar with, and make sure you clearly understand how the code works. As we saw earlier, it is very easy to write a program that has a bug in it unless we are very careful.

I hope this example helps you understand how to use loops in your code a bit more. On the next page, you'll work through a quick example program yourself. See if you can apply what you've learned to solve that problem. Good luck!
