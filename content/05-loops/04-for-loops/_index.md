---
title: "For Loops"
pre: "4 "
weight: 40
---

{{< youtube SKuR2gbVnaQ  >}}

[Video Materials]({{% relref "./video" %}})

Most programming languages also support another type of looping construct, known as a **For** loop. A **For** loop usually includes an explicitly defined _loop counter_ , a _loop condition_ and _loop counter incrementor_ as part of the loop definition, and is usually used to make sure that a loop only runs a set number of times. This is especially handy for instances where we need to accept exactly {{< math >}}$ 5 ${{< /math >}} inputs, or if the program should perform a calculation exactly {{< math >}}$ 10 ${{< /math >}} times.

Many programming languages support a variety of different ways to define how the _loop counter_ in a **For** loop functions. For these examples, we'll use a simple definition for the _loop counter_ where it is just an integer that begins at one value and increments by {{< math >}}$ 1 ${{< /math >}} (the _loop counter incrementor_) each time until it reaches a second value (the _loop condition_). 

Here's a flowchart showing what a **For** loop may look like:

![For Loop Flowchart](/images/05-loop/5.4.forloop.png)

In this flowchart, we use the shorthand `i : [1, x] by 1` to show that the _loop counter_ `i` starts at the value {{< math >}}$ 1 ${{< /math >}}, and then each loop it is incremented by {{< math >}}$ 1 ${{< /math >}} until it is larger than `x`. So, if `x = 6`, the loop counter `i` will have the values `1`, `2`, `3`, `4`, `5`, and `6`, and the loop will run exactly {{< math >}}$ 6 ${{< /math >}} times. 

When reading this aloud, we might say `i : [1, x] by 1` as _"For values of `i` from {{< math >}}$ 1 ${{< /math >}} through `x` incrementing by {{< math >}}$ 1 ${{< /math >}}"_. So, we could say this whole loop is _"For values of `i` from {{< math >}}$ 1 ${{< /math >}} through `x` incrementing by {{< math >}}$ 1 ${{< /math >}}, print `i`."_ That should exactly match the original problem statement given earlier:

> Write a program that accepts _any_ positive integer as input, and then prints all integers starting with 1 up to the given number.

In code, there are many different ways that **For** loops are usually defined. We'll learn how our programming language implements these loops later in this chapter. 


