---
title: "Ternary Statement"
pre: "6. "
weight: 60
---

Java also includes the **Ternary Conditional Operator**, which can be used as a shortcut for an **If-Else** statement. 

First, consider the flowchart we saw earlier in this chapter:

![Ternary Operator Flowchart](/images/04-cond/4.5.ternary.png)

In Java, this flowchart could be represented by the following code:

```java
public static void main(String[] args){
  int x = 3;
  int y = 5;
  int z = (x > y) ? x : y;
  System.out.println(z);
}
```

In this program, the expression `(x > y) ? x : y;` is the **Ternary Conditional Operator**. It first calculates the value of the Boolean expression `(x > y)`. If that expression is `true`, then the entire expression evaluates to `x`. If it is `false`, then the expression evaluates to `y`. So, if we compile and run this program, it should output `5`. 

We can also include the **Ternary Conditional Operator** anywhere we'd normally use a value. This is because, just like any other operator, the **Ternary Conditional Operator** results in a single value when evaluated. For example, it could be used directly within the `println()` method:

```java
public static void main(String[] args){
  int x = 3;
  int y = 5;
  System.out.println((x > y) ? x : y);
}
```
