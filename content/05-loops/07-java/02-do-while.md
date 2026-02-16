---
title: "Do-While Loop"
pre: "2. "
weight: 20
---

Java also includes another form of a **While** loop, known as a **Do-While** loop . Here is the general syntax for a **Do-While** loop in Java:

```java
do{
  <loop code block>
}while(<Loop Condition>);
```

In this code, Java will first execute all of the code in the `<loop code block>` without evaluating any Boolean expressions. The main use of a **Do-While** loop is to guarantee that the code inside the loop is executed at least once. Then, it will evaluate the `<Loop Condition>` to a Boolean value. If that value is `true`, then the program will repeat the code in the `<loop code block>` once again. If it is `false` at any time it is evaluated, then the program will continue running the code directly below the **Do-While** loop.

It is very important to remember that the Loop Condition is enclosed by parentheses `( )`, while the block of code that should be executed if that expression is `true` is enclosed by curly braces `{ }`, just like in an **If** statement, class body or method body. In addition, notice that Java also requires a semicolon `;` after the Boolean expression. 

Let's take a look at a quick example, just to see how this construct works in practice. First, let's consider the program represented by this flowchart from earlier in the chapter:

![Do While Loop Flowchart](/images/05-loop/5.3.dowhile.png)

This flowchart corresponds to the following code in Java. In this case, we'll assume `x` is hard-coded for now:

```java
int x = 8;
int i = 1;
do{
  System.out.println(i);
  i = i + 1;
}while(x >= i);
```

By walking through the execution of this program, we see that it will output all integers from `1` through `8`. 

However, this program will perform differently than a **While** loop if the user inputs a number less than `1`. Since this program is built using a **Do-While** loop, it will always execute the code inside the loop first, so the program will always print at least `1` to the terminal. After that, the program will evaluate `x >= i`, which will be `false` if `x` is less than `1`, so it will terminate. Notice that this is different than the **While** loop on the previous page, which will not produce any output at all in this instance. 

Therefore, it is very important to understand how each loop functions and choose the appropriate loop for each task. In practice, **Do-While** loops are used very rarely, but they can be useful in some instances. 

{{% notice note "Uncommonly Used" %}}

In practice, **Do-While** loops are not commonly used in Java. We're including them here just in case you see them in other code you find, but we generally don't recommend using them in your own code unless the situation calls for this loop structure.

{{% /notice %}}