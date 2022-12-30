---
title: "If-Else Statement"
pre: "2. "
weight: 20
---

The **If-Else** statement in Python is very similar to the **If** statement. In Python, the syntax for an **If-Else** statement is shown below:

```python
if <Boolean expression>:
    <True block>
else:
    <False block>
```

As expected, Python will first evaluate the `<Boolean expression>` to a single Boolean value. If that value is `True`, it will execute the instructions in the `<True block>`, which can be one or more lines of code, or even additional constructs as we'll see later. If that value is `False`, then the program will execute the code in the `<False block>` instead. In essence, the **If-Else** statement simply adds a second code block and the `else` keyword after an **If** statement. 


Let's take a look at a few code examples, just to see how this construct works in practice. First, let's consider the program represented by this flowchart from earlier in the chapter:

![If-Then-Else Flowchart](/images/04-cond/4.4.ifthenelse.png)

This flowchart corresponds to the following code in Python. In this case, we'll assume `x` is hard-coded for now:

```python
x = 1
if x >= 0:
    print(x)
else:
    print(-1 * x)
print("Goodbye")
```

As we can see, this program uses `x >= 0` as the Boolean logic expression inside of the **If-Else** statement. If it is `True`, then it will output the value of `x`. If it is `False`, the program will output the value `(-1 * x)`, which represents the inverse of `x`. 

Here's one more example. In this program, we'd like to calculate the difference between two numbers, but we'd only like to output a positive number. So, our code may look something like this:

```python
x = 3
y = 8
if x > y:
    difference = x - y
    print(difference)
else:
    difference = y - x
    print(difference)
```

In this program, we are simply checking to see if `x > y`. If so, we know that `x - y` will be a positive number. Otherwise, we can assume that `y - x` will be either a positive number or {{< math >}}$ 0 ${{< /math >}}. In either case, we see that this program will produce the correct output. 