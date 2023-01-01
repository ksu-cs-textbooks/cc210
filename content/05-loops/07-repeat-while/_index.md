---
title: "Repeat While"
pre: "7. "
weight: 70
---

<!-- TODO Update Videos -->

One of the fundamental concepts in algorithms is being able to repeat steps or instructions indefinitely, based on a condition. Most programming languages implement one or more of the following types of condition-based loops: <b>REPEAT WHILE</b> or <b>REPEAT UNTIL</b>.

### REPEAT WHILE[^1]

[^1]: This section lifted almost entirely from K-State Courses CC 110 copyright Lavezzi, 2021

This is a very common type of looping structure in programming languages.  Any other type of condition-based loops can be re-written as <b>REPEAT WHILE</b>.

The **REPEAT WHILE** is a way of repeating a set of statements while the loop condition remains True. In pseudo code, this looks like:

```tex
REPEAT WHILE (loop condition)
{
    code to run if loop condition is True
}
```

The code-block (loop body) following the **REPEAT WHILE** statement will be repeated until the _(loop condition)_ expression becomes `False`. Once the loop condition becomes false, the code block is skipped, and execution picks up on the first line after the code-block.  Here's a quick example:

```tex
n <- 5
REPEAT WHILE  n > 0
{
    DISPLAY (n)
    n <- n - 1
}
DISPLAY("done")
```

```tex
5
4
3
2
1
done
```
As you can see, the <b>REPEAT WHILE</b> loop above counts down from 5 to 1 and then finally prints `done` at the bottom once the loop executes. Each iteration of the loop, the value of variable `n` is printed out, then decreases by 1. Each time an iteration is completed, the condition of the **REPEAT WHILE** statement is checked before another iteration occurs. If the condition is `False`, the loop exits, and any code following the loop is executed. Therefore, the overall operation of the **REPEAT WHILE** loop looks like this:

![REPEAT WHILE Loop Structure](/images/05-loop/cc110_Lab4_rp_while.png)

{{% youtube w46v0t1Ucb0 %}}

Most programming languages implement this as a simple "while" loop.

#### While

{{% youtube U3hewt8IF2g %}}

[Video Materials]({{<relref "./video">}})

The simplest form of a loop in our computer programs is commonly known as a **While** loop. In essence, we continue to repeat the steps inside the loop _while_ a particular Boolean expression evaluates to `true`. The program on the previous page is a great example of a **While** loop:

![While Loop Flowchart](/images/05-loop/5.2.countuploop.png)

In this program, we repeat the steps inside the loop, which print the value of `i` and increment that value by `1`, _while_ the Boolean expression `x >= i` evaluates to `true`. Whenever we reach the Boolean expression and it evaluates to `false`, we exit the loop and continue with the program. 

In code, most programming languages implement a **While** loop in a format similar to this:

```tex
<before code block>
while <Loop condition>
    <loop code block>
<after code block>
```

This program begins by executing code in the `<before code block>`. Once it reaches the `<Loop condition>`, a Boolean expression, it will evaluate that expression. If the expression evaluates to `false`, then it will completely skip over the `<loop code block>` and go directly to the `<after code block>`

However, if the `<Loop condition>` evaluates to `true` initially, it will execute the code in the `<loop code block>`. Once it is done executing that code block, the program will _loop_ back to the `<Loop condition>` and evaluate it again. If it evaluates to `true`, it will perform the steps in the `<loop code block>` again. It will continue to do so _while_ the `<Loop condition>` evaluates to `true`.

However, if the `<Loop condition>` ever evaluates to `false`, then the program will move on to the `<after code block>` and continue executing from there.

Also, it is important to remember that the `<Loop condition>` is only evaluated once each time the program loops. So, even if the outcome of the expression may change while the code in the `<loop code block>` is executing, it only checks the value of the `<Loop condition>` once it is completely done executing that block of code. However, as we'll see a bit later in this chapter, there are ways to leave the `<loop code block>` at any time. 

<!-- Do while defered to to langugae specifics summer 2021 -->



