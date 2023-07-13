---
title: "Loop Constructs"
pre: "2. "
weight: 20
---

Thankfully, there is. In addition to conditional statements, programming languages include a second important control construct: _looping constructs_, which allow us to solve problems like this one. A _looping construct_ is a programming construct that allows us to repeat a piece of code as many times as we'd like. In this way, we can perform repeated actions without making our source code infinitely long. Most programming languages refer to this process as _looping_, which makes sense once we see how it looks in a flowchart.

Let's go back to that problem statement:

> Write a program that accepts _any_ positive integer as input, and then prints all integers starting with 1 up to the given number. 

Using a looping construct, we can solve this problem using a program that may resemble this flowchart:

![Looping Program Flowchart](/images/05-loop/5.2.countuploop.png)

This flowchart includes a secondary variable `i`, sometimes referred to as a _loop counter_ or an _iterator variable_, to help us keep track of which number we are on. Let's walk through this program with an input of `6` to see how it works.

Initially, since our input is `6`, we know that `x = 6` and `i = 1`. Next, we reach the first Boolean expression, which will evaluate `x >= i`. Since `6 >= 1` is `true`, we follow the **True** branch. Notice in this diagram that the **True** branch points down, entering the loop-body.  The **False** branch goes to the right, which is different from the conditional constructs we saw in the previous chapter.

Following the **True** branch, we see that our program will print the value in variable `i`, which is `1`; then it will perform `i = i + 1`, making `2` the new value of `i`. 

Finally, it _loops_ back up to the Boolean expression `x >= i` again, but this time evaluates it with the current values for `x` and `i`, which would be `6 >= 2`. Since this evaluates to `true`, we follow the **True** branch once again. It will print the current value of `i`, which is `2`, then _increment_ `i` to `3`. 

We _loop_ again, and evaluate `6 >= 3`, which is still `true`, so we repeat the process again. 

After several _loops_, or _iterations_ of the loop, we eventually reach the situation where `i = 6`. In this case, we'll print the number `6`, then increment `i` to `7`. Now, when we evaluate the Boolean expression `x >= i`, we find `6 >= 7`, which is `false`, so the program now follows the **False** branch and ends. 

In total, it will have printed the value stored in `i` on each iteration, so it will print the numbers `1` through `6`, which is exactly what the problem statement requires.

{{% notice tip "Try It Yourself!" %}}

Pick a value for `x`, and see if you can follow each step in the flowchart to confirm that this program will print out all the numbers from `1` to the value you've chosen. It is very important to have a clear understanding of how this program functions before moving on in this chapter.

{{% /notice %}}

The ability of a computer program to _loop_, or repeat the loop body based on the loop condition, is a very powerful tool for any programmer. Loops allow us to build programs that can handle all kinds of inputs and still operate correctly. We can also handle situations where we may not know how many inputs we need, or how many steps we need to take, since we can tell our program to use a loop counter to determine how many steps we need to repeat. 


![Loop Flowchart elements](/images/05-loop/5-loopconstruct_1.png)