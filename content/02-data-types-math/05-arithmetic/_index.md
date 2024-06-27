---
title: "Arithmetic"
pre: "5. "
weight: 50
---

Once we have data stored in our programs, there are a number of ways we can manipulate that data. Let's look at a few of them here.

## Basic Operations

At its core, a computer is capable of performing all of the basic arithmetic operations, so we can write programs that can _add_, _subtract_, _multiply_ and _divide_ numbers. However, there is one big caveat that must be dealt with.

As discussed on the previous page, computer programs can store numbers as both integers and floating point numbers. What happens when we perform operations on two different types of numbers? For example, if an integer is added to a floating point number, would the resulting number be an integer or a floating point number, as in {{< math >}}$ 1 + 1.5 ${{< /math >}}? 

As our intuition suggests, performing the operation gives us {{< math >}}$ 1 + 1.5 = 2.5 ${{< /math >}}, which is a floating point number. **In general**, when performing an operation on either two integers or two floating point numbers, the result will match the type of the two operands. However, when performing an operation on both an integer and a floating point number, the result is a floating point number. 

There are two notable exceptions to this rule:

1. In a strongly-typed programming language, such as Java, the result may be converted to match the type of the variable it is being stored in, if allowed by the language.
1. When dividing two integers, the result may be either a floating point number or an integer, depending on the language.

We'll discuss both of these exceptions later in this chapter when we dig into the details for each programming language. 

## New Operations

{{< youtube rn262DJeOaE  >}}

[Video Materials]({{% relref "./video" %}})

In addition to the basic operations listed above that we are all familiar with from our mathematics class, there are a few new operations we should be aware of as well.

### Modulo

The first new operation, the _modulo operation_, finds the remainder after dividing two numbers. It is typically written as {{< math >}}$ 9 \bmod 5 ${{< /math >}} when printed, but most programming languages use the percent sign `%`, as in `9 % 5` to refer to this operation. 

To calculate the result of the modulo operation, we must look back to long division. In the example above, we can calculate {{< math >}}$ 9 \bmod 5 ${{< /math >}} by first calculating {{< math >}}$ 9 / 5 ${{< /math >}}, which is {{< math >}}$ 1 ${{< /math >}} with a remainder of {{< math >}}$ 4 ${{< /math >}}. So, the result of {{< math >}}$ 9 \bmod 5 ${{< /math >}} is {{< math >}}$ 4 ${{< /math >}}. 

Another way to think about the modulo operation is to simply find the largest multiple of the second operand that is smaller than the first, and then subtract the two, just like you do when performing long division. So, we can find {{< math >}}$ 42 \bmod 13 ${{< /math >}} by first calculating the largest multiple of {{< math >}}$ 13 ${{< /math >}} that is smaller than {{< math >}}$ 42 ${{< /math >}}, which is {{< math >}}$ 39 ${{< /math >}}, or {{< math >}}$ 13 * 3 ${{< /math >}}. Then, we can subtract {{< math >}}$ 42 - 39 = 3 ${{< /math >}}, so {{< math >}}$ 42 \bmod 13 = 3 ${{< /math >}}. 

The modulo operation is very important in many areas of programming. In fact, it is one of the core operations for most modern forms of encryption!

{{% notice warning "Modulo & Negative Numbers" %}}

The modulo operation is not consistently defined when applied to negative numbers. Therefore, each programming language may return a slightly different result when performing this operation on a negative number. Make sure you carefully consider how this operation is used, and consult the official documentation for your programming language or test the operation if you aren't sure how it will work.

{{% /notice %}}

### Truncated & Floor Division

As discussed a bit earlier, one of the stranger things in programming is dealing with division. When dividing two integers, it is possible to end up with a result that is a floating point number, as in {{< math >}}$ 9 / 8 = 1.125 ${{< /math >}}. So, how should we handle this?

It turns out that each programming language may handle it a bit differently. For example, Java would _truncate_ the result by removing everything after the decimal point to make the result an integer. So, in Java, the statements `99 / 100` and `-99 / 100` would both usually evaluate to `0`. However, we can force the result to be a floating point number by making sure that at least one of the operands is a floating point number, as well as the variable we are storing the result in. 

Python, on the other hand, would store the result as a floating point number by default if needed. However, Python also includes a special operator, known as _floor division_ or `//`, that would round the result down. For positive numbers, this means that the result would be rounded _toward_ 0, while negative numbers would be rounded _away from_ 0. So, in Python, the statement `99 // 100` would evaluate to `0` since it is rounded toward 0, while `-99 // 100` would evaluate to `-1` since it is rounded away from 0. 

In short, we just need to pay special attention when we use the division operation to make sure we get the result we expect. 

### Assignment & Equality

Lastly, we should briefly discuss the assignment operator. We've already come across it earlier in this chapter. In mathematics, we usually use the equals sign `=` to denote _equality_, as in {{< math >}}$ x + 5 = 10 ${{< /math >}}. 

In programming, we use the single equals sign `=` to perform _assignment_. This allows us to store a value into a variable, as in `x = 5`. This would store the value {{< math >}}$ 5 ${{< /math >}} into the variable `x`. We could also say that we _assign_ the value {{< math >}}$ 5 ${{< /math >}} to x. 

However, it is very important to note that the variable we are assigning a value to goes first, on the left side of the equals sign. So, we cannot say `5 = x` in most programming languages.

{{% notice note "Equality" %}}

Most programming languages use a double equals sign, or `==` to denote equality. We'll learn more about equality and other comparison operators in a later chapter.

{{% /notice %}}