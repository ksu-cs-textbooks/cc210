---
title: "Operators"
pre: "4. "
weight: 40
---

Now that we've learned how to create our own variables, we can use them to perform a wide variety of mathematical operations. For most of these, we'll use the same operator symbols that we've used before in math, but a few of them are unique to programming languages like Java. 

For each of the examples below, we'll assume that we have already created two `int` variables, `x` and `y`, as follows:

```java
int x = 5;
int y = 8;
```

## Addition `+`

Using the plus `+` symbol, we can add two numbers together and find their sum:

```java
int z = x + y;
System.out.println(z); // 13
```

Since {{< math >}}$ 5 + 8 = 13 ${{< /math >}}, this program would output `13`. 

When writing our code, it is always good practice to put spaces between operators and operands unless otherwise noted, just to make it easier to read our code. 

The plus symbol can also be use to _concatenate_ or link multiple strings together. We'll learn how to do that in the project for this chapter. 

{{% notice note "Code Comments" %}}

We can add _comments_ to our code to help us describe it to others or simply understand it better ourselves. These comments are simply text that is added to the source code, but they are marked in a way that tells the compiler to ignore it when compiling the program.

In Java, we can use two forward slashes `//` to tell the compiler that everything on that line following those symbols should be treated as a comment, as we can see in the examples on this page. 

We can also use a forward slash followed by an asterisk `/*` to start a _multiline comment_ in Java. The compiler will ignore everything after that symbol until a closing asterisk followed by a forward slash `*/` is found. 

Finally, Java also uses a forward slash followed by two asterisk `/**` to denote special comments that can be used to automatically generate documentation for the code. Again, this comment section is closed by an asterisk followed by a forward slash `*/`.

Traditionally, each additional line in these multiline comments will be prefixed by an asterisk to make them easier to read. In fact, the Codio editor will do that for us!

Here are some examples in code showing how those comments can be used.

```java
/**
 * This is a comment at the beginning of a class that gives
 * information about the class contained in this file
 * 
 * @author Username
 * @version 1.0
 */

public class Example{
  
  /**
   * This is a comment at the beginning of a method. 
   * It can give information about the inputs and outputs 
   * of that method
   * 
   * @param args - the command-line arguments
   */
  public static void main(String[] args){
    /*
     * This is a simple multi-line comment
     * It can have multiple lines
     * and ends with the slash below
     */
    
    int x = 0;
    
    //This is a single line comment
    int y = 0; //Comment after code on the same line
  }
}

```

Feel free to use comments anywhere in your source code to help you understand what the code does! It is always better to include too many comments than too few, especially in larger programs. 

{{% /notice %}}

## Subtraction `-`

Likewise, we can use the minus `-` symbol to subtract two values and find their difference:

```java
int z = x - y;
System.out.println(z); // -3
```

This program would output `-3`, since {{< math >}}$ 5 - 8 = -3 ${{< /math >}}. It is important to remember that these operations can result in negative numbers, so the order of operands we use matters when subtracting.  

We can also use the minus symbol to find the additive inverse of a number, or change the sign of a variable from positive to negative and vice-versa:

```java
int z = -x - y;
System.out.println(-z); // 13
```

In this example, we use `-x` to denote the inverse of `x`. In this case, we don't include a space between the minus symbol and the variable it is attached to. So, this expression will calculate {{< math >}}$ -5 - 8 = -13 ${{< /math >}} and store that value in `z`. Then, when we print that variable, we invert it again, so it will actually print `13` to the screen instead of the value {{< math >}}$ -13 ${{< /math >}} stored in `z`. 

## Multiplication `*`

We can also use the asterisk `*` or star symbol for multiplication to find the product of two numbers:

```java
int z = x * y;
System.out.println(z); // 40
```

We know that {{< math >}}$ 5 * 8 = 40 ${{< /math >}}, so this program would output `40` as expected.

## Division `/`

Division is a bit different. Most programming languages use the forward slash `/` symbol for division, making the statement look like a fraction. That is probably the easiest way to think about division in a programming language - it makes a fraction of the dividend and the divisor.

Earlier in this chapter we discussed that strange things may happen when we try to divide two whole numbers. Let's look at a few examples:

```java
int z = x / y;
System.out.println(z); // 0
```

This first example will calculate {{< math >}}$ 5 / 8 ${{< /math >}} but store it in an `int` variable. We expect the answer to be {{< math >}}$ 0.625 ${{< /math >}}, but since an `int` variable can only store a whole number, the result is _truncated_ by removing the decimal portion. So, our program just outputs `0`. 

Here's another example:

```java
int z = -x / y;
System.out.println(z); // 0
```

We know that {{< math >}}$ -5 / 8 = -0.625 ${{< /math >}}, but once again the result is _truncated_ and the decimal part is removed. So, this program will also output `0`. 

Let's look at another division example:

```java
double z = x / y;
System.out.println(z); // 0.0
```

Here we are storing the result in a `double` variable. We'd expect the output to be `0.625`, but we actually just get `0.0` when we run this program. That's strange, isn't it?

Earlier we discussed some of the rules for how a programming language calculates numbers. One of those rules states that an operation performed on two whole numbers will result in a whole number, which is exactly what is happening here. The processor calculates {{< math >}}$ 5 / 8 = 0 ${{< /math >}} as a whole number using truncated division, then converts the value {{< math >}}$ 0 ${{< /math >}} to a floating point value before storing it in `z`. So, even though it appears we should be storing {{< math >}}$ 0.625 ${{< /math >}}, we aren't able to due to the data types of our two operands. This is a very common mistake made by programmers of all skill levels, so it is very important to understand what is going on.

So, how can we solve this issue? The answer lies in the use of a _cast_ operation to convert the data type of one of our operators to a floating point value. Here's an example showing how to accomplish that:

```java
double z = (double) x / y;
System.out.println(z); // 0.625
```

In this example, we are casting the value stored in `x` to be of type `double`. Then, the division operation is performed, this time between a floating point number and a whole number, which will result in a floating point number. Finally, that result will be stored in `z`, and the program will output `0.625`, which is the correct answer. 

In short, we need to make sure we pay special attention when dividing numbers in our programs, just to make sure we are getting the result we expect. 

## Modulo `%`

The modulo operator uses the percent sign `%` to calculate the remainder of a division operation. Let's look at an example:

```java
int z = x % y;
System.out.println(z); // 5
```

Here, we are calculating the remainder of the division {{< math >}}$ 5 / 8 ${{< /math >}}. Since {{< math >}}$ 8 ${{< /math >}} does not go into {{< math >}}$ 5 ${{< /math >}} at all, we are left with {{< math >}}$ 5 ${{< /math >}} as the remainder of that division. 

If we reverse the operands, we can get a different result:

```java
int z = y % x;
System.out.println(z); // 3
```

Here, we are calculating the remainder of {{< math >}}$ 8 / 5 ${{< /math >}}. Since {{< math >}}$ 5 ${{< /math >}} will go into {{< math >}}$ 8 ${{< /math >}} once, we can perform {{< math >}}$ 8 - 5 = 3 ${{< /math >}} to find the remainder of that division. 

{{% notice warning "Modulo & Negative Numbers" %}}

In Java, the modulo operation is treated like a true remainder operation. So, when applied to negative numbers, it will perform the expected division and return the remainder, which may be a negative number, depending on the signs of the operands. It follows the same sign rule as multiplication and division. 

Here are some examples:

```java
System.out.println(-8 % 5);  // -3
System.out.println(-8 % -5); // -3
System.out.println(8 % -5);  // 3
```

We already know that {{< math >}}$ 8 \% 5 = 3 ${{< /math >}}. In this case, the negative sign is applied if just one operand is negative. Otherwise, the result is positive if both operands are negative. 

{{% /notice %}}

## Increment `++` & Decrement `--`

Increment `++` and decrement `--` are two special operators in Java. They are used to add or subtract {{< math >}}$ 1 ${{< /math >}} from an existing variable. Let's look at a couple of examples:

```java
int z = x++;
System.out.println(x); // 6
System.out.println(z); // 5
```

Here, the increment operator will increase the value stored in `x` by {{< math >}}$ 1 ${{< /math >}}. In this case, we don't include a space between the operator and the variable it is attached to. However, since the operator is _after_ the variable, it will happen at the end of the operation. So, the value {{< math >}}$ 5 ${{< /math >}} will be stored in `z` first, then `x` will be incremented by {{< math >}}$ 1 ${{< /math >}} afterwards. So, the program will output `6` as the value of `x`, and `5` as the value of `z`. 

By placing the increment operator in front of the variable, we can see a different outcome:

```java
int z = ++x;
System.out.println(x); // 6
System.out.println(z); // 6
```

As we'd expect, here the increment operation will be performed first, and then the new value stored in `x` will also be stored in `z`, so both variables will contain the value {{< math >}}$ 6 ${{< /math >}} in this program. 

The decrement operator works similarly, subtracting {{< math >}}$ 1 ${{< /math >}} instead of adding {{< math >}}$ 1 ${{< /math >}}. 

In practice, these operators are only used in a few scenarios, most notably within loops to increment or decrement a counter variable. In general, they can make our code more complex and difficult to read due to the variety of different ways these operators can be used. 

## Assignment Shortcuts

Finally, many operators in Java also have combined operation and assignment operators. These will perform the operation specified and store the value in the first variable, all in a single statement. 

| Operator | Example | Equivalent |
|:--------:|:-------:|:----------:|
| `+=` | `x += y;` | `x = x + y;` |
| `-=` | `x -= y;` | `x = x - y;` |
| `*=` | `x *= y;` | `x = x * y;` |
| `/=` | `x /= y;` | `x = x / y;` |
| `%=` | `x %= y;` | `x = x % y;` |

As with the increment and decrement operators, some of these shortcuts are rarely used in practice since they can make our code more difficult to read and understand. However, in some scenarios they can be quite helpful. 

## Order of Operations

{{% youtube P9v4yJrow9A %}}

[Video Materials]({{<relref "./video">}})

We are already familiar with the order of operations in mathematics, using mnemonics such as "PEMDAS" to refer to the following order:

1. Parentheses
1. Exponents
1. Multiplication & Division
1. Addition & Subtraction

Programing languages work very similarly, but there are many more operators to deal with. Here's a quick list of the order of operations, or _operator precedence_ of the operators we've covered so far:

1. Parentheses
1. _Postfix:_ Increment `++` & Decrement `--` after variable*
1. _Prefix:_ Inverse `-`, Increment `++` & Decrement `--` before variable* 
1. _Multiplicative_: Multiplication `*`, Division `/`, and Modulo `%`
1. _Additive_: Addition `+`, Subtraction `-`
1. _Assignment_: `=`, `+=`, `-=`, `*=`, `/=`, `%=`

_* The increment and decrement operations will be calculated either before or after the rest of the operation is performed, depending on where they are placed in relation to the associated variable. This lists what order they will be analyzed by the compiler to determine which variable they are attached to._

Here's a quick example to show how this works:

```java
int x = 1;
int y = ++x + x - x / x * x % x--;
System.out.println(x); 
System.out.println(y); 
```

Can we determine what the output should be? Let's try to break it down!

Based on the operator precedence table above, we know that the `x--` will be evaluated first. However, since it is after the variable, it won't be calculated until after the rest of the operation is complete. So, we can just remember that step for now, and we'll actually perform that calculation last.

Next, we know that `++x` will be evaluated. This step must be performed before any other operation since it is before the variable, so we must immediately increment the value of `x` by {{< math >}}$ 1 ${{< /math >}}. So, `x` is now {{< math >}}$ 2 ${{< /math >}}. 

Now we can perform all of the multiplicative operations, going from left to right. So, by adding the appropriate parentheses, we'd calculate the following:

{{< math >}}$$ x + x - x / x * x \% x $${{< /math >}}
{{< math >}}$$ 2 + 2 - 2 / 2 * 2 \% 2 $${{< /math >}}
{{< math >}}$$ 2 + 2 - (2 / 2) * 2 \% 2 $${{< /math >}}
{{< math >}}$$ 2 + 2 - ((2 / 2 * 2) \% 2 $${{< /math >}}
{{< math >}}$$ 2 + 2 - (((2 / 2) * 2) \% 2) $${{< /math >}}
{{< math >}}$$ 2 + 2 - ((1 * 2) \% 2) $${{< /math >}}
{{< math >}}$$ 2 + 2 - (2 \% 2) $${{< /math >}}
{{< math >}}$$ 2 + 2 - 0 $${{< /math >}}

Following that, we can perform any additive operations. Once again, we can add parentheses as appropriate to find the following:

{{< math >}}$$ 2 + 2 - 0 $${{< /math >}}
{{< math >}}$$ (2 + 2) - 0 $${{< /math >}}
{{< math >}}$$ ((2 + 2) - 0) $${{< /math >}}
{{< math >}}$$ (4 - 0) $${{< /math >}}
{{< math >}}$$ 4 $${{< /math >}}

Once we've calculated all of the operations on the right-hand side of the assignment operator, we can then perform the assignment operation to store the final value {{< math >}}$ 4 ${{< /math >}} in `y`. 

Finally, we must remember to go back and decrement the value in `x` by {{< math >}}$ 1 ${{< /math >}}, so `x` once again is just {{< math >}}$ 1 ${{< /math >}}.

So, the final output from this program would be:

![Operators Example](/images/02-data/image_6.png)

However, as any good math teacher will tell us, it is always better to use additional parentheses to make sure our operations are performed in the correct order instead of relying on the order of operations. So, we should definitely avoid writing code as ambiguous as the example given above.


