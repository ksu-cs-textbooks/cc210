---
title: "Wash, Rinse, Repeat"
pre: "1. "
weight: 10
---

At this point, we should be able to write a computer program that can accomplish many simple tasks. We've seen programs that determine if a number is even or odd, who wins in a game of "Rock, Paper, Scissors," and whether a given year should be a leap year or not.

However, there's one simple task that all of our current programming skills cannot easily handle. Let's take a look at a version of that task and see if we can figure out how to solve it:

> Write a program that accepts a positive integer between 1 and 5 as input, and then prints all integers starting with 1 up to the given number. 

On the surface, this seems to be a pretty easy problem. We can solve it using a few **if** statements, as shown in this diagram below:

![Counting Up Flowchart](/images/05-loop/5.1.countup.png)

Following this flowchart, we can see if that if our input is `3`, it would first print `1` since `x >= 1` is true, then `2`, then `3` in a similar way. After that, the next check is `x >= 4`, which is false, so the program would stop printing. So, this program meets our given specification.

Now, let's see if we can generalize this program a bit:

> Write a program that accepts _any_ positive integer as input, and then prints all integers starting with 1 up to the given number. 

Could we write this program using our current techniques? Unfortunately, we'd quickly find that it is impossible to handle. We'd need to create at least one **if** statement for each possible integer, which would make our code infinitely long. 

So, is there a better way to approach this problem?