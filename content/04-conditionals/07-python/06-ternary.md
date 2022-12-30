---
title: "Ternary Statement"
pre: "6. "
weight: 60
---

Python also includes the **Ternary Conditional Operator**, which can be used as a shortcut for an **If-Then-Else** statement. 

First, consider the flowchart we saw earlier in this chapter:

![Ternary Operator Flowchart](/images/04-cond/4.5.ternary.png)

In Python, this flowchart could be represented by the following code:

```python
x = 3
y = 5
z = x if x > y else y
print(z)
```

In this program, the expression `x if x > y else y` is the **Ternary Conditional Operator**. It first calculates the value of the Boolean expression `x > y`. If that expression is `True`, then the entire expression evaluates to `x`. If it is `False`, then the expression evaluates to `y`. So, if we run this program, it should output `5`. To best understand this operator, we can simply read aloud what it says: "Set `z` to `x` if `x > y`. If not, set `z` to `y` instead."

We can also include the **Ternary Conditional Operator** anywhere we'd normally use a value. This is because, just like any other operator, the **Ternary Conditional Operator** results in a single value when evaluated. For example, it could be used directly within the `print()` method:

```python
x = 3
y = 5
print(x if x > y else y)
```

