---
title: "Chaining & Nesting"
pre: "4. "
weight: 40
---

{{% youtube F29jX1H-iUY %}}

[Video Materials]({{<relref "./video">}})

One of the most powerful features of the conditional constructs we've covered so far in this course is the ability to chain them together or nest them within each other to achieve remarkably useful program structures. The ability to use conditional constructs effectively is one of the most powerful skills to develop as a programmer. 

## Zero, One, Negative One

A great example of the many ways to structure a program using conditional constructs is building a simple program that does three things: 

1. If `x` is less than {{< math >}}$ 0 ${{< /math >}}, output `-1`
1. If `x` is equal to {{< math >}}$ 0 ${{< /math >}}, output `0`
1. If `x` is greater than {{< math >}}$ 0 ${{< /math >}}, output `1`

Let's look at two different ways we could structure this program using the conditional constructs we've already learned.

{{% notice tip "Try It!" %}}

See if you can build each of these examples in `Conditionals.py` file, which is open in to the left. Doing so is a great way to get additional practice working with conditional constructs. 

{{% /notice %}}

## Chaining If-Then Statements

First, we could chain together several **If** statements to create this program. As a flowchart, the program might look like this:

![Chaining If-Then Statements](/images/04-cond/4.7.x.3.chaining.png)

Here's one way that program could be written in Python. Once again, we're just using hard-coded variables for now:

```python
x = 3
if x < 0:
    print(-1)
if x == 0:
    print(0)
if x > 0:
    print(1)
```

Just like we see in the flowchart, this program contains three **If** statements chained together, one after another. If we run this program with various inputs, we should see that it produces the expected result.

## Nesting If-Then-Else Statements

Next, we can achieve the same result using **IF-Else** statements. Here's what that program would look like as as flowchart:

![Nesting If-Then-Else Statements](/images/04-cond/4.7.x.3.nesting.png)

We can also write that program in Python. Here's one possible way to do it:

```python
x = 3
if x < 0:
    print(-1)
else:
    if x == 0:
        print(0)
    else:
        print(1)
```

In this example, we've nested an **If-Else** statement inside of the second block of another **If-Else** statement. So, if the first Boolean expression, `x < 0`, is `True`, we'll output `-1` and end the program. However, if it is `False`, we'll go into the `False` branch of the first statement. Then, we'll see another Boolean expression, `x == 0`. If that expression is `True`, we'll output `0`. Otherwise, we'll output `1`. Once again, this program should produce the correct result.

Of course, we could include a third **If-Else** statement, as shown in this example:

```python
x = 3
if x < 0:
    print(-1)
else:
    if x == 0:
        print(0)
    else:
        if x > 0:
            print(1)
        else:
            print("ERROR!")
```

As we discussed earlier in this chapter, we can safely infer that `x` must be greater than {{< math >}}$ 0 ${{< /math >}} based on the two previous Boolean expressions. However, what if we've made a logic error in our program, and that assumption is not valid? By including the last **If-Else** statement, we can have our program print an error in the unlikely chance that the value of `x` is not properly handled by any other option. 

In fact, here's how easy it is to cause just that sort of logic error. Consider the following example:

```python
x = 3
if x < -1:
    print(-1)
else:
    if x == 0:
        print(0)
    else:
        if x > 1:
            print(1)
        else:
            print("ERROR!")
```

{{% notice tip "Spot The Error" %}}

Can you spot the logic error in the example above? Try running the code with different values for `x` and see what happens. 

{{% /notice %}}

In this example, we've updated the Boolean expression in the first **If-Else** statement to `x < -1`. Similarly, we've changed the Boolean expression in the third statement to `x > 1`. That change seems logical, right?

What if the value of `x` is exactly {{< math >}}$ 1 ${{< /math >}} or {{< math >}}$ -1 ${{< /math >}}? In that case, it will fail all three logic expressions, and the program will output `ERROR!` instead. By including the third **If-Else** statement, we can detect logic errors that may not easily be found otherwise. Without that statement, the program would most likely output `1` even when the input is `-1`, which is clearly a negative number. 

So, in many cases, it may be better to include additional **If-Else** statements to explicitly check all possible cases, instead of relying on assumptions and inferences, which may lead to unintended logic errors. 

## Inline Nesting

Finally, it is desirable to minimize nested **If-Else** statements if the nested statement is exclusively in the `false` branch. Here's an example:

```python
x = 3
if x < 0:
    print(-1)
elif x == 0:
    print(0)
elif x > 0:
    print(1)
else:
    print("ERROR!")
```

Python includes the `elif` keyword as a shortcut for `else if` in this example. Many other programming languages do not support this keyword, and instead just use `else if` in this structure. 

Many programming languages refer to this structure as an **If-Else If-Else** statement. In this program, if the first Boolean expression is `False`, it immediately moves to the next Boolean expression following the first `elif` keyword.  The process continues until one Boolean expression evaluates to `True`, or the final `else` keyword is reached. In that case, we know that none of the Boolean expressions evaluated to `True`, so the final `False` branch is executed. 

