---
title: "While Loops"
pre: "3. "
weight: 30
---

{{< youtube U3hewt8IF2g >}}

[Video Materials]({{% relref "./video" %}})

The simplest form of a loop in our computer programs is commonly known as a **While** loop. In essence, we continue to repeat the steps inside the loop _while_ a particular Boolean expression evaluates to `true`. The program on the previous page is a great example of a **While** loop:

![While Loop Flowchart](/images/05-loop/5.2.countuploop.png)

In this program, we repeat the steps inside the loop, which print the value of `i` and increment that value by `1`, _while_ the Boolean expression `x >= i` evaluates to `true`. Whenever we reach the Boolean expression and it evaluates to `false`, we exit the loop and continue with the program. 

In code, most programming languages implement a **While** loop in a format similar to this:

```tex
<before code block>
while <loop condition>
    <loop code block>
<after code block>
```

This program begins by executing code in the `<before code block>`. Once it reaches the `<loop condition>`, a Boolean expression, it will evaluate that expression. If the expression evaluates to `false`, then it will completely skip over the `<loop code block>` and go directly to the `<after code block>`

However, if the `<loop condition>` evaluates to `true` initially, it will execute the code in the `<loop code block>`. Once it is done executing that code block, the program will _loop_ back to the `<loop condition>` and evaluate it again. If it evaluates to `true`, it will perform the steps in the `<loop code block>` again. It will continue to do so _while_ the `<loop condition>` evaluates to `true`.

However, if the `<loop condition>` ever evaluates to `false`, then the program will move on to the `<after code block>` and continue executing from there.

Also, it is important to remember that the `<loop condition>` is only evaluated once each time the program loops. So, even if the outcome of the expression may change while the code in the `<loop code block>` is executing, it only checks the value of the `<loop condition>` once it is completely done executing that block of code. However, as we'll see a bit later in this chapter, there are ways to leave the `<loop code block>` at any time. 

## Do-While Loops

Some programming languages also implement another type of loop, known as a **Do-While** loop. Here's a flowchart showing what a **Do-While** loop might look like:

![Do While Loop Flowchart](/images/05-loop/5.3.dowhile.png)

In code, a **Do-While** loop looks similar to this:

```tex
<before code block>
do
    <loop code block>
while <loop condition>
<after code block>
```

These loops are very similar to a **While** loop, but instead of checking the `<loop condition>` first, the code inside the `<loop code block>` is executed before any test is done. In this way, it guarantees that the code in the `<loop code block>` is executed at least once. Then, the `<loop condition>` is evaluated, and if it evaluates to `true` the code in the `<loop code block>` is executed again. If it evaluates to `false`, then the program moves on to the `<after code block`>

If we look at the flowchart for the **Do-While** loop above, can we determine if it matches the problem statement from earlier?

> Write a program that accepts _any_ positive integer as input, and then prints all integers starting with 1 up to the given number.

Let's assume the user chose the number `3` as input. First, the program will set `i = 1`, then it will print `1` and set `i = 2`. Next, it will evaluate the Boolean expression `x >= i`, or `3 >= 2`, which evaluates to `true`, so the loop repeats.

The program will then print `2` and set `i = 3`, and then it will evaluate `3 >= 3`, which is also `true`. So, it will loop once again, printing `3` and setting `i = 4`. Finally, it will evaluate `3 >= 4`, which is `false`, and the program will terminate. So, in this case, the program works as expected. 

However, there are some cases where a **While** loop and a **Do While** loop may produce different output, even if the same code and Boolean expression are used. We'll see an example of that later in this chapter. 