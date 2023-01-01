---
title: "Repeat Until"
pre: "8. "
weight: 80
---

### REPEAT UNTIL[^1]

[^1]: this section lifted almost entirely from K-State Courses CC 110 copyright Lavezzi, 2021

The REPEAT UNTIL is a way of repeating a set of statements until the loop condition <b>becomes</b> True (i.e. statements are repeated while the loop condition is False). Once the loop condition becomes True, the code block is skipped, and execution picks up on the first line after the code-block. In pseudo code this looks like:

```tex
REPEAT UNTIL (loop condition)
{
    code to run if loop condition is False
}
```

```tex
n <- 5
REPEAT UNTIL n ≤ 0
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
Most modern programming languages do not implement a "REPEAT UNTIL" looping structure[^2]. Those that do often also have a <b>REPEAT WHILE</b> structure, such as Lua and Pascal.

[^2]: "Scratch", a graphics based teaching language, and "Lua" a multi-paradigm embedded systems language,  implement this structure.  Pascal, an early programming language (a community supported version is still maintained) also has a "repeat until".

<b>REPEAT WHILE</b> and <b>REPEAT UNTIL</b> loops are used when the body of the loop alters one or more values used in the loop-condition. Execution of the next loop iteration depends on the results of the previous iteration.  

If the loop body cannot <emp>eventually</emp> change the values in the loop condition, it will <b>never</b> change the condition. If you enter the loop, you'll stay in it forever.  This is called an infinite loop.  Infinite loops are generally considered to be a "bug".  

### Interchangeability of REPEAT WHILE and REPEAT UNTIL

Most languages implement REPEAT WHILE. However, the conversion between it and UNTIL can be fairly straight forward.

```tex
x <- 5
i <- i
REPEAT WHILE (x  >= i){

  DISPLAY(i)
  i <- i +1
}
```

is the same as

```tex
x <- 5
i <- i
REPEAT UNTIL (NOT(x  >= i)){

  DISPLAY(i)
  i <- i +1
}
```
