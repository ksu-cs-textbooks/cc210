---
title: "Java Order of Operations"
pre: "3.J. "
weight: 30
hidden: true
date: 2019-02-06T10:53:26-05:00
---

{{< youtube P9v4yJrow9A >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

We all probably learned the acronym PEMDAS for the order of operations in mathematics. It stands for parentheses, exponents, multiplication & division, addition & subtraction. When faced with a large math equation, we can use this list to understand which operations should be performed first.

Programming languages such as Java also enforce an order of operations. In fact, it is very similar to the one we're already familiar with from math. Just like in math, we must evaluate everything in parentheses first. Then, we perform any prefix actions, or symbols before the variables, such as increment, decrement, or negative when they are placed in front of the number. Following that, we deal with any postfix actions, such as increment or decrement after the variables. Finally, we can do multiplication, division, and modulo operations, then addition and subtraction from left to right just like we do in math. Finally, the assignment operator is handled last, storing the result from the right-hand side into the variable on the left.

To really understand how this works, let's walk through an example. Here's a simple piece of code, taken directly from the textbook, that can help us illustrate how the order of operations works in Java.

First, we set the value of `x` to 1. That's pretty simple.

Next, we reach this second line, which will determine the value of `y`. Let's break it down. Since there are no parentheses in this expression, we don't have to worry about that step.

The next step is prefix operators, such as the increment operator here. Since this operator is placed in front of the variable, we must perform this operation first. So, we'll go ahead and update the value of `x` to be 2, before doing anything else.

Next, we'll handle any postfix operators, which would be this decrement operation here. Since it is placed after the variable, we actually should do this operation after the rest of the expression is calculated. So, mentally, we'll need to add a new line of code below this one, which will update the value of `x` after we're done.

Now we can deal with the operators themselves. First comes the multiplicative operators, which are multiply, divide, and modulo. We deal with these from left to right, just like we do in math. So, the first one is a division operation. We replace the variables with their current values, then calculate the result. Since both of these are integers, Java will produce an integer when performing division.

We can then do the same for the multiplication operator. We replace any variables with their current values, then perform the calculation.

Finally, we will perform the modulo operation here as well.

Next, we'll do the same process for any addition and subtraction operators, also from left to right. So, we'll perform the addition first, then the subtraction to reach our final result.

Lastly, we'll handle the assignment operator, which will assign the value 4 to `y`.

But wait, we also need to remember that we had a postfix decrement operator, which is represented by this new line of code we mentally added to the code. So, we'll need to decrement `x` again, making its value 1.

That should do it! I hope this example helps you understand how Java handles the order of operations a bit clearer.
