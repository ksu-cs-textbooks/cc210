---
title: "Definite Loops"
pre: "9. "
weight: 90
---

### REPEAT n TIMES[^1]

[^1]: This section lifted almost entirely from K-State Courses CC 110 copyright Lavezzi, 2021

The <b>REPEAT n TIMES</b> loop is used when you know exactly how many times to repeat the loop, namely `n` times.  The value of `n` cannot be changed or referred to inside the loop body.  Because it will always execute exactly `n` times, this is sometimes referred to as a <b>definite loop</b>.

```tex
REPEAT n TIMES
{
    code to run n-times 
}
```

```tex
n <- 5
m <- 4
REPEAT m TIMES 
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
done
```

Note here that the variable `m` is used limit the iterations.  Since `m` is less than `n`, this loop does not count all the way down to `1`.

Most languages use `for` for this purpose

### For Loops

{{% youtube SKuR2gbVnaQ %}}

[Video Materials]({{<relref "./video">}})

Most programming languages also support another type of looping construct, known as a **For** loop. A **For** loop usually includes an explicitly defined _loop counter_ , a _loop condition_ and _loop counter incrementor_ as part of the loop definition, and is usually used to make sure that a loop only runs a set number of times. This is especially handy for instances where we need to accept exactly {{< math >}}$ 5 ${{< /math >}} inputs, or if the program should perform a calculation exactly {{< math >}}$ 10 ${{< /math >}} times.

Many programming languages support a variety of different ways to define how the _loop counter_ in a **For** loop functions. For these examples, we'll use a simple definition for the _loop counter_ where it is just an integer that begins at one value and increments by {{< math >}}$ 1 ${{< /math >}} (the _loop counter incrementor_) each time until it reaches a second value (the _loop condition_). 

Here's a flowchart showing what a **For** loop may look like:

![For Loop Flowchart](/images/05-loop/5.4.forloop.png)

In this flowchart, we use the shorthand `i : [1, x] by 1` to show that the _loop counter_ `i` starts at the value {{< math >}}$ 1 ${{< /math >}}, and then each loop it is incremented by {{< math >}}$ 1 ${{< /math >}} until it is larger than `x`. So, if `x = 6`, the loop counter `i` will have the values `1`, `2`, `3`, `4`, `5`, and `6`, and the loop will run exactly {{< math >}}$ 6 ${{< /math >}} times. 

When reading this aloud, we might say `i : [1, x]` as _"For values of `i` from {{< math >}}$ 1 ${{< /math >}} through `x` incrementing by {{< math >}}$ 1 ${{< /math >}}"_. So, we could say this whole loop is _"For values of `i` from {{< math >}}$ 1 ${{< /math >}} through `x` incrementing by {{< math >}}$ 1 ${{< /math >}}, print `i`."_ That should exactly match the original problem statement given earlier:

> Write a program that accepts _any_ positive integer as input, and then prints all integers starting with 1 up to the given number.

In code, there are many different ways that **For** loops are usually defined. We'll learn how our programming language implements these loops later in this chapter. 

{{% notice info "Loops, Convention & Pythonic Weirdness" %}}

**For** loops, as presented above, are really just a special syntax for a **While** loop.  They can do the same things but are used in slightly different semantic situations.  

By convention, **While** loops are used when there will be an indefinite number of loop-iterations-whether or not you loop again depends on what happens in the loop. A conventionally constructed **While** loop must occasionally change some value involved in the loop condition.  If it does not it will loop forever.  Thus readers of **while** loops expect that the variables associated with the loop condition will change inside the loop itself.

In contrast **For** loops should never change the values and variables associated with their loop condition inside the loop body.  The only thing that alters the loop counter is the steady, predictable march of the loop counter incrementer.

Using a definite loop (For-loop) signals to future readers that the number of times you will go through the loop <b>does not</b> depend on what happens in the loop.  This is important information to those who may want to adapt or maintain this code.  Also important, it signals to the interpreter and compiler that certain types of machine code optimization[^2] may be applicable.  This makes the loop part of program execution much faster.

[^2]: Ways to write the machine code so it produces the same outcome, but maybe uses a different (faster) algorithm.  Optimization is beyond the scope of the CC program

If you want to microwave a cup of soup until it boils, thats a **While** loop -- you monitor the soup and stop the microwave when it starts to boil.  If you are just going to microwave the cup of soup for a fixed time, even if it boils over and makes a mess, that is a **FOR** loop -- there is a fixed number of seconds the oven will run.

Python does not have a conventional **For** loop, but rather iterates through a collection (there is no loop condition).  Python **For** loops will be covered after collections and sequences are introduced.  

Technically, since all conventional **FOR** loops can be written as **While** loops, the **FOR** loop is not necessary.

{{% /notice %}}


