---
title: "While Loop"
pre: "2. "
weight: 20
---

Now let's look at how Python implements the REPEAT WHILE. First, here is the general syntax for a **While** loop:

```python
while <Loop Condition>:
  <loop code block>
```

As expected, Python will first evaluate the `<Loop Condition>` to a single Boolean value. If that value is `True`, it will execute the instructions in the `<loop code block>`, which can be one or more lines of code, or even additional constructs. Once the `<loop code block>` execution is complete, the program will return to the top of the loop and evaluate the `<Loop Condition>` again. It will repeat this process until the expression evaluates to `False`. Of course, if the expression is `False` initially, the code in the `<loop code block>` will not be executed at all. 

It is very important to remember that the Loop Condition is followed by a colon `:`, while the block of code that should be executed if that expression is `True` is indented, just like in an **If** statement.

Let's take a look at a quick example, just to see how this construct works in practice. First, let's consider the program represented by this flowchart from earlier in the chapter:

![Looping Program Flowchart](/images/05-loop/5.2.countuploop.png)

This flowchart corresponds to the following code in Python. In this case, we'll assume `x` is hard-coded for now:

```python
x = 8
i = 1
while x >= i:
  print(i)
  i = i + 1
```

By walking through the execution of this program, we see that it will output all integers from $1$ through $8$. If the user inputs a number less than $1$, the program will not produce any output at all. 