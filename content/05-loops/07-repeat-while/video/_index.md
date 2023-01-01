---
title: "While Loop"
pre: "1. "
weight: 10
date: 2019-02-08T00:00:26-05:00
hidden: true
---

{{< youtube U3hewt8IF2g >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

The simplest form of repeated code in a computer program is the while loop. In essence, the computer will repeat the code inside of the loop while a Boolean expression evaluates to True. This flowchart shows a simple program written with a while loop. It accepts an integer as input, and will print out all of the integers starting at 1 through that value. Let's see if we can step through this code and understand how it works.

When stepping through code, I like to keep track of the current values of each variable, as well the output that the program will produce to the user. So, here on the right, we'll have two sections to keep track of that information.

First, we'll need to accept input from the user. Let's assume the user inputs 3 for this example. So, we'll store the value 3 in the variable named `x`.

In addition, we'll create another variable named `i` to keep track of where we are in the loop, and initialize that variable with the value 1. Sometimes we'll refer to a variable that we use in this was as an "iterator variable," which is why we typically use the variable name `i` here.

Next, we reach the Boolean condition at the start of the loop. If this condition evaluates to true, we'll enter the loop and run the code inside of it. If it is false, we'll bypass the loop and continue on with the program. In this case, the statement `x >= i` evaluates to True, since 3 is definitely greater than 1. So, we'll enter the loop.

Inside of the loop, we'll first output the value of `i` to the screen, so our output will contain 1. Then, we'll increment the value of `i` by 1, so it will now be 2.

Then, we'll go back to the beginning of the loop and reevaluate the Boolean condition. Since `x` is still greater than or equal to `i`, we'll enter the loop once again.

Inside of the loop, we'll print 2, and then update the value of `i` to 3.

Back at the Boolean condition, we see that `x` is equal to `i`, so we'll enter the loop again.

Once inside, we'll print 3 and update the value of `i` to 4.

At this point, the Boolean condition evaluates to false, since `i` is now greater than `x`. So, we'll leave the loop, and terminate the program. As we can see, the program outputs all integers from 1 through the input of 3, so it works as expected.

Some programming languages also include a Do loop, which is similar to a while loop in many respects. Make sure you read the rest of the text on this page to learn about how Do loops work.
