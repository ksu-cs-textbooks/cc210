---
title: "Python Order of Operations"
pre: "3.P. "
weight: 31
hidden: true
date: 2019-02-07T10:53:26-05:00
---

{{< youtube FI9XFlFOtSQ >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

We all probably learned the acronym PEMDAS for the order of operations in mathematics. It stands for parentheses, exponents, multiplication & division, addition & subtraction. When faced with a large math equation, we can use this list to understand which operations should be performed first.

Programming languages such as Python also enforce an order of operations. In fact, it is very similar to the one we're already familiar with from math. Just like in math, we must evaluate everything in parentheses first. Then, we perform any exponents using the exponentiation operator. Next, we handle any prefix actions, or symbols before the variables, such as a negative sign. Following that, we can do multiplication, division, and modulo operations, then addition and subtraction from left to right just like we do in math. Finally, the assignment operator is handled last, storing the result from the right-hand side into the variable on the left.

To really understand how this works, let's walk through an example. Here's a simple piece of code, taken directly from the textbook, that can help us illustrate how the order of operations works in Python.

First, we set the value of `x` to 2. That's pretty simple.

Next, we reach this second line, which will update the value of `x`. Let's break it down. Since there are no parentheses in this expression, we don't have to worry about that step.

So, the first step is to handle this exponentiation operator. So, we substitute the current value for each variable, then perform the calculation, and put the result in its place.

The next step is prefix operators, such as the negative sign here. Since this operator is placed in front of the variable, we must perform this operation first. So, we'll replace this variable with the inverse of its value here. In this case, it will be -2.

Now we can deal with the operators themselves. First comes the multiplicative operators, which are multiply, divide, and modulo. We deal with these from left to right, just like we do in math. So, the first one is a division operation. We replace the variables with their current values, then calculate the result. Since we are using the standard division operator here, Python will produce a floating point value as a result, even though it is a whole number. That will be important as we move through this expression.

We can then do the same for the multiplication operator. We replace any variables with their current values, then perform the calculation.

We can perform the modulo operation here as well.

Following that, we'll run into a floor division operator. In this instance, even though it is a floor division, one of the operands is a floating point number, so the result must also be a floating point number, even though it will be floored to the nearest whole number. This is a very important thing to remember, but it follows the rules we've learned in this chapter.

Next, we'll do the same process for any addition and subtraction operators, also from left to right. So, we'll perform the addition first, then the subtraction to reach our final result.

Lastly, we'll handle the assignment operator, which is a `+=` sign. So, this is the same as saying `x = x + 0.0`. That will produce `2.0` as the result, which will then be stored in the value of `x`.

So, in essence, this big complicated expression only changed the data type of `x` from an integer to a floating point number.

That should do it! I hope this example helps you understand how Python handles the order of operations a bit clearer.
