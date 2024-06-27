---
title: "Operators"
pre: "4. "
weight: 40
---

Now that we've learned how to create our own variables, we can use them to perform a wide variety of mathematical operations. For most of these, we'll use the same operator symbols that we've used before in math, but a few of them are unique to programming languages like Python. 

For each of the examples below, we'll assume that we have already created two `int` variables, `x` and `y`, as follows:

```python
x = 5
y = 8
```

## Addition `+`

Using the plus `+` symbol, we can add two numbers together and find their sum:

```python
z = x + y
print(z) # 13
```

Since {{< math >}}$ 5 + 8 = 13 ${{< /math >}}, this program would output `13`. 

When writing our code, it is always good practice to put spaces between operators and operands unless otherwise noted, just to make it easier to read our code. 

The plus symbol can also be use to _concatenate_ or link multiple strings together. We'll learn how to do that in the project for this chapter. 

{{% notice note "Code Comments" %}}

We can add _comments_ to our code to help us describe it to others or simply understand it better ourselves. These comments are simply text that is added to the source code, but they are marked in a way that tells the compiler to ignore it when compiling the program.

In Python, we can use the number sign or hash symbol `#` to tell the compiler that everything on that line following those symbols should be treated as a comment, as we can see in the examples on this page. 

We can also use three quotation marks `"""` before and after a block to text to create a _multiline comment_. However, these are not precisely the same as comments, since the interpreter treats the block as a value that is not assigned to any variable. 

That said, Python uses these mutliline comments to create _docstrings_ that describe the actions of a file or method. We'll learn more about creating those docstrings later in this course.  

Here are some examples in code showing how those comments can be used.

```python
"""
This is a docstring comment at the beginning of a file that gives
information about the code contained in this file
"""

# This is a single line comment
x = 0

y = 5 # Comments can even go after a line of code

```

Feel free to use comments anywhere in your source code to help you understand what the code does! It is always better to include too many comments than too few, especially in larger programs. 

{{% /notice %}}

## Subtraction `-`

Likewise, we can use the minus `-` symbol to subtract two values and find their difference:

```python
z = x - y
print(z) # -3
```

This program would output `-3`, since {{< math >}}$ 5 - 8 = -3 ${{< /math >}}. It is important to remember that these operations can result in negative numbers, so the order of operands we use matters when subtracting.  

We can also use the minus symbol to find the additive inverse of a number, or change the sign of a variable from positive to negative and vice-versa:

```python
z = -x - y
print(-z) # 13
```

In this example, we use `-x` to denote the inverse of `x`. In this case, we don't include a space between the minus symbol and the variable it is attached to. So, this expression will calculate {{< math >}}$ -5 - 8 = -13 ${{< /math >}} and store that value in `z`. Then, when we print that variable, we invert it again, so it will actually print `13` to the screen instead of the value {{< math >}}$ -13 ${{< /math >}} stored in `z`. 

## Multiplication `*`

We can also use the asterisk `*` or star symbol for multiplication to find the product of two numbers:

```python
z = x * y
print(z) # 40
```

We know that {{< math >}}$ 5 * 8 = 40 ${{< /math >}}, so this program would output `40` as expected.

## Exponent `**`

Python also includes a special operator to perform the exponentiation, or power, operation. It is a set of two asterisks `**` or stars. We can use it as follows:

```python
z = x ** y #alternate z = pow(x,y)
print(z) # 390625
```

While it may take some work, we can verify the result of {{< math >}}$ 5^{8} = 390625 ${{< /math >}} is correct.  

## Division `/`

Division is a bit different. Most programming languages use the forward slash `/` symbol for division, making the statement look like a fraction. That is probably the easiest way to think about division in a programming language - it makes a fraction of the dividend and the divisor.

Earlier in this chapter we discussed that strange things may happen when we try to divide two whole numbers. Let's look at a few examples:

```python
z = x / y
print(z) # 0.625
```

This first example will calculate {{< math >}}$ 5 / 8 ${{< /math >}} but store it in an `float` variable. So, even though both `x` and `y` are of type `int`, the result will always be of type `float`. 

Of course, we can always convert the result to an `int` using the built-in `int()` method, as shown in this example:

```python
z = int(x / y)
print(z) # 0
```

This will output `0`, since `z` is now of type `int`. Remember that the `int()` function will _truncate_ the decimal portion of the result. 

In short, we need to make sure we pay special attention when dividing numbers in our programs, just to make sure we are getting the result we expect. 

## Floor Division `//`

Python also includes another special operator for floor division, which is two forward slashes `//`. This operator will round the result of a division down to the next smallest whole number. Let's look at a couple of examples:

```python
z = x // y
print(z) # 0
```

This first example will output `0`, since the result of {{< math >}}$ 5 / 8 = 0.625 ${{< /math >}} will be floored down to {{< math >}}$ 0 ${{< /math >}}.

However, this example shows what is unique about this operation:

```python
z = -x // y
print(z) # -1
```

We can calculate the result of {{< math >}}$ -5 / 8 = -0.625 ${{< /math >}}, just as we'd expect. However, since the floor operation will round down toward negative infinity, the output here is `-1`, which is the next smallest integer. It can be a bit confusing at first, but hopefully it makes sense. 

## Modulo `%`

The modulo operator uses the percent sign `%` to calculate the remainder of a division operation. Let's look at an example:

```python
int z = x % y
print(z) # 5
```

Here, we are calculating the remainder of the division {{< math >}}$ 5 / 8 ${{< /math >}}. Since {{< math >}}$ 8 ${{< /math >}} does not go into {{< math >}}$ 5 ${{< /math >}} at all, we are left with {{< math >}}$ 5 ${{< /math >}} as the remainder of that division. 

If we reverse the operands, we can get a different result:

```python
int z = y % x
print(z) # 3
```

Here, we are calculating the remainder of {{< math >}}$ 8 / 5 ${{< /math >}}. Since {{< math >}}$ 5 ${{< /math >}} will go into {{< math >}}$ 8 ${{< /math >}} once, we can perform {{< math >}}$ 8 - 5 = 3 ${{< /math >}} to find the remainder of that division. 

{{% notice warning "Modulo & Negative Numbers" %}}

In Python, the modulo operation is performed as a floor division remainder. So, if the division operation is {{< math >}}$ a // b = q ${{< /math >}} with remainder {{< math >}}$ r ${{< /math >}}, the remainder must satisfy the equation {{< math >}}$ b * q + r = a ${{< /math >}}. Therefore, the result may be different depending on the signs of the operands.

Here are some examples:

```python
print(int(-8 % 5))  # 2
print(int(8 % -5))  # -2
print(int(-8 % -5)) # -3
```

In the first example, we would perform {{< math >}}$ -8 // 5 = -2 ${{< /math >}}, since {{< math >}}$ -2 ${{< /math >}} is the next smallest whole number. Then, to find the remainder, we must satisfy the equation {{< math >}}$ 5 * -2 + r = -8 ${{< /math >}}. So, to solve that equation, we would find that {{< math >}}$ x = 2 ${{< /math >}}. 

In the second example, we'd perform a similar division first, which is {{< math >}}$ 8 // -5 = -2 ${{< /math >}}. However, when we fill in the equation, we would get {{< math >}}$ -5 * -2 + r = 8 ${{< /math >}}, which would yield {{< math >}}$ x = -2 ${{< /math >}}. 

Finally, the third example would find the result of the division {{< math >}}$ -8 // -5 = 1 ${{< /math >}}. Then, we can use the second equation to find {{< math >}}$ -5 * 1 + r = -8 ${{< /math >}}, where {{< math >}}$ r = -3 ${{< /math >}} in that case.

In short, the value itself may change depending on the signs of the operands, so you must be careful when using the modulo operation on negative numbers. 

{{% /notice %}}

## Assignment Shortcuts

Finally, many operators in Python also have combined operation and assignment operators. These will perform the operation specified and store the value in the first variable, all in a single statement. 

| Operator | Example | Equivalent |
|:--------:|:-------:|:----------:|
| `+=` | `x += y` | `x = x + y` |
| `-=` | `x -= y` | `x = x - y` |
| `*=` | `x *= y` | `x = x * y` |
| `**=` | `x **= y` | `x = x ** y` |
| `/=` | `x /= y` | `x = x / y` |
| `//=` | `x //= y` | `x = x // y` |
| `%=` | `x %= y` | `x = x % y` |

Some of these shortcuts are rarely used in practice since they can make our code more difficult to read and understand. However, in some scenarios they can be quite helpful. 

## Order of Operations

{{< youtube FI9XFlFOtSQ  >}}

[Video Materials]({{% relref "./video" %}})

We are already familiar with the order of operations in mathematics, using mnemonics such as "PEMDAS" to refer to the following order:

1. Parentheses
1. Exponents
1. Multiplication & Division
1. Addition & Subtraction

Programing languages work very similarly, but there are many more operators to deal with. Here's a quick list of the order of operations, or _operator precedence_ of the operators we've covered so far:

1. Parentheses
1. _Exponentiation:_ `**`
1. _Prefix:_ Inverse `-` 
1. _Multiplicative_: Multiplication `*`, Division `/`, Floor Division `//`, and Modulo `%`
1. _Additive_: Addition `+`, Subtraction `-`
1. _Assignment_: `=`, `+=`, `-=`, `*=`, `**=`, `/=`, `//=`, `%=`

Here's a quick example to show how this works:

```python
x = 2
x += -x + x - x / x * x ** x % x // x
print(x) 
```

Can we determine what the output should be? Let's try to break it down!

Based on the operator precedence table above, we know that the exponentiation will be evaluated first. So, let's perform that step:

{{< math >}}$$ -x + x - x / x * x ^ x \% x // x $${{< /math >}}
{{< math >}}$$ -2 + 2 - 2 / 2 * 2 ^ 2 \% 2 // 2 $${{< /math >}}
{{< math >}}$$ -2 + 2 - 2 / 2 * (2 ^ 2) \% 2 // 2 $${{< /math >}}
{{< math >}}$$ -2 + 2 - 2 / 2 * 4 \% 2 // 2 $${{< /math >}}

Next, we can perform the inverse operation on the first number:

{{< math >}}$$ (-2) + 2 - 2 / 2 * 4 \% 2 // 2 $${{< /math >}}

Now we can perform all of the multiplicative operations, going from left to right. So, by adding the appropriate parentheses, we'd calculate the following:

{{< math >}}$$ (-2) + 2 - 2 / 2 * 4 \% 2 // 2 $${{< /math >}}
{{< math >}}$$ (-2) + 2 - (2 / 2) * 4 \% 2 // 2 $${{< /math >}}
{{< math >}}$$ (-2) + 2 - ((2 / 2) * 4) \% 2 // 2 $${{< /math >}}
{{< math >}}$$ (-2) + 2 - (((2 / 2) * 4) \% 2) // 2 $${{< /math >}}
{{< math >}}$$ (-2) + 2 - ((((2 / 2) * 4) \% 2) // 2) $${{< /math >}}
{{< math >}}$$ (-2) + 2 - (((1.0 * 4) \% 2) // 2) $${{< /math >}}
{{< math >}}$$ (-2) + 2 - ((4.0 \% 2) // 2) $${{< /math >}}
{{< math >}}$$ (-2) + 2 - (0.0 // 2) $${{< /math >}}
{{< math >}}$$ (-2) + 2 - 0.0 $${{< /math >}}

Notice that the first division operation created a floating point value. From then on, any operation containing that floating point value would also result in a floating point value, even floor division. 

Following that, we can perform any additive operations. Once again, we can add parentheses as appropriate to find the following:

{{< math >}}$$ (-2) + 2 - 0.0 $${{< /math >}}
{{< math >}}$$ ((-2) + 2) - 0.0 $${{< /math >}}
{{< math >}}$$ (((-2) + 2) - 0.0) $${{< /math >}}
{{< math >}}$$ (0 - 0.0) $${{< /math >}}
{{< math >}}$$ 0.0 $${{< /math >}}

Once we've calculated all of the operations on the right-hand side of the assignment operator, we can then perform the assignment operation. Since we used the `+=` assignment operator, we will add the value {{< math >}}$ 0.0 ${{< /math >}} to the existing value in `x`. So, we'd calculate {{< math >}}$ 2 + 0.0 = 2.0 ${{< /math >}}, which will store the value {{< math >}}$ 2.0 ${{< /math >}} in `x`. 

So, the final output from this program would be:

![Operators Example](/images/02-data/2.6.p.3.ops.png)

Notice that the final type of `x` is now `float`, since we added a floating point value to the original `int` value. 

However, as any good math teacher will tell us, it is always better to use additional parentheses to make sure our operations are performed in the correct order instead of relying on the order of operations. So, we should definitely avoid writing code as ambiguous as the example given above.

Human readable code is the goal of any programming activity.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}