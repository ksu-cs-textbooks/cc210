---
title: "For Loop"
pre: "2. "
weight: 20
hidden: true
date: 2019-02-08T00:00:26-05:00
---

{{< youtube SKuR2gbVnaQ >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

Another common type of loop structure in programming is the For loop. In most for loops, there is an explicitly defined iterator variable that goes through each value in a list of values or makes sure the loop only runs a specific number of times.

This flowchart shows a simple program written with a for loop. In this case, is will also print all integers from 1 through the value input by the user. So, let's walk through this diagram to see how it works.

First, as before, we start by accepting input from the user, and storing that input in variable `x`. We'll assume the user inputs 3 again.

Next, we'll reach the decision node in the for loop. This node will set the value of the iterator variable `i` to the first value in the list, in this case 1. Here we're using a mathematical notation for a list, which includes items from 1 to the value of `x`, including both 1 and `x` in the list. Since we haven't run out of list items yet, we'll enter the loop.

Inside of the loop, we'll just print the value of `i`, in this case 1, to the terminal.

When we loop back to the beginning of the loop, the node will update the value of `i` to the next value in the list. Since there are still additional values, we'll set `i` to 2 and continue.

Inside of the loop, we'll print that value to the screen.

Back at the beginning, we'll update the value of `i` to 3, and continue.

Once again, we'll print 3 to the terminal.

Now, when we reach the top of the loop, we'll find that there are no more items in the list that can be assigned to `i`. So, the loop will end, and in this case the program will terminate.

That's all there is to it! For loops are a very common structure in many programming languages, but each one handles them a bit differently. So, read on in this chapter to learn how to write for loops in your langauge of choice.
