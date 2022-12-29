---
title: "Boolean Operators"
pre: "2. "
weight: 20
---

Java also supports most of the Boolean operators discussed earlier in the chapter. Let's look at a few examples.

## Not `!`

In Java, the **not** operator is the exclamation point `!`, placed before a Boolean value. It will invert the value of the variable, changing `true` to `false` and `false` to `true`. 

Here is a quick example:

```java
boolean b = true;
boolean c = !b;
System.out.println(c); // false
```

This program will output `false`, which is the inverted value of `b`. 

## And `&&`

To perform the **and** operation, Java uses two ampersands `&&` placed between Boolean values. Let's look at an example:

```java
boolean a = true;
boolean b = true;
boolean c = false;
System.out.println(a && b); // true
System.out.println(b && c); // false
```

This program will output `true` on the first line, since we know that both `a` and `b` are `true`. On the second line, it will output `false`, since `c` is `false`, even though `b` is `true`. 

## Or `||`

Similarly, Java uses two vertical pipes `||` to represent the **or** operator. On most keyboards, we can find that key above the Enter key. Here's an example of how it can be used in code:

```java
boolean a = true;
boolean b = false;
boolean c = false;
System.out.println(a || b); // true
System.out.println(b || c); // false
```

Once again, this program will output `true` on the first line, since `a` is `true`, even though `b` is `false`. On the second line, it will output `false`, since both `b` and `c` are `false`. 

{{% notice info "Short-Circuit Operators" %}}

According to the Java documentation, Java also supports using a single `&` for **and**, and a single `|` for **or** when dealing with Boolean values. Why shouldn't we just use these operators instead?

It turns out that there is a fundamental difference in how the Java compiler handles these operators. The double-character operators `&&` and `||` are called _logical operators_ and _short-circuit operators_. In some scenarios, the system only needs to look at the first value in the statement to determine the result. For example, the statement `x || (y || z)` will always be `true` if `x` is `true`, without needing to consider the values in `y` or `z`. The same works for `x && (y && z)` when `x` is `false`, which will result in the entire statement being `false`. For larger Boolean expressions, the use of these short-circuit operators can make our programs run much faster and more efficiently. 

The single-character operators `&` and `|` bit-wise comparison operators and are not short-circuited. So, the system will evaluate each part of the statement before determining the outcome. For boolean values, the bit-wise operators will evaluate to the same answer as the logical operators.

However you should not use them for this purpose.  First, because they will slow your programs executions.  Second, because it will obscure your intent to future readers of your program.  At some distance point in the future, a programmer will see you used a bit-wise operator, assume there must be a reason you did not using the logical one, and lose valuable time trying to figure out **why** you did not use the logical operator.    

You can read more about [Bitwise Operations](https://en.wikipedia.org/wiki/Bitwise_operation) on Wikipedia. We will not use them in CC 210.

{{% /notice %}}

## Exclusive Or 

Java does not support a logical **exclusive or**.  

```java
boolean a = true;
boolean b = false;
boolean c = true;
System.out.println((a || b) && !(a && b)); // true
System.out.println((a || c) && !(a && c)); // false
```

In this example, the first line will be `true`, since `a` is `true` but `b` is `false`. However, the second line will output `false`, since both `a` and `c` are `true` .

## Comparison Operators

We can also use the comparison operators `==`, `!=`, `<`, `<=`, `>`, and `>=` to compare variables containing numbers, which will result in a Boolean value. Here's an example showing those operators in action:

```java
int x = 1;
int y = 2;
double z = 3.0;

System.out.println(x < y);  // true
System.out.println(x <= 1); // true
System.out.println(x > 2);  // false
System.out.println(x >= z); // false

System.out.println(x == 1); // true
System.out.println(x != y); // true
```

As we can see, each of the comparison operators works just as we'd expect, and outputs a Boolean value of either `true` or `false`, depending on the result of the comparison.

{{% notice warning "Chaining Operators is Not Allowed" %}}

Like most high level languages, Java does not allow the chaining of comparison operators.  `10 <= x <=20`, which is a pretty standard math notation for x is between 10 and 20, will not work.  First the compiler will evaluate 10 <=x as a boolean, then it will throw a fit about trying to compare a `boolean` and and `int` for the `<= 20` part.

You will need to write this as `10 <= x && x <= 20`.

{{% /notice %}}

## Order of Operations

Now that we've introduced some additional operators, we should also see where they fit in with the other operators in Java. Here is an updated list giving the appropriate _operator precedence_ for Java, with new entries in **bold**:

1. Parentheses
1. _Postfix:_ Increment `++` & Decrement `--` after variable*
1. _Prefix:_ Inverse `-`, **Not `!`**, Increment `++` & Decrement `--` before variable* 
1. _Multiplicative_: Multiplication `*`, Division `/`, and Modulo `%`
1. _Additive_: Addition `+`, Subtraction `-`
1. **_Relational_: `<`, `>`, `<=`, `>=`**
1. **_Equality_: `==`, `!=`**
1. **_Logical And_: `&&`**
1. **_Logical Or_: `||`**
1. _Assignment_: `=`, `+=`, `-=`, `*=`, `/=`, `%=`
