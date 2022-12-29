---
title: "Boolean Operators"
pre: "2. "
weight: 20
---

Python also supports most of the Boolean operators discussed earlier in the chapter. Let's look at a few examples.

## Not

In Python, the **not** operator is the keyword `not`, placed before a Boolean value. It will invert the value of the variable, changing `True` to `False` and `False` to `True`. 

Here is a quick example:

```python
b = True
c = not b
print(c) # False
```

This program will output `False`, which is the inverted value of `b`. 

## And

To perform the **and** operation, Python uses the `and` keyword, placed between Boolean values. Let's look at an example:

```python
a = True
b = True
c = False
print(a and b) # True
print(b and c) # False
```

This program will output `True` on the first line, since we know that both `a` and `b` are `True`. On the second line, it will output `False`, since `c` is `False`, even though `b` is `True`. 

## Or

Similarly, Python uses the `or` keyword to represent the **or** operator. Here's an example of how it can be used in code:

```python
a = True
b = False
c = False
print(a or b) # True
print(b or c) # False
```

Once again, this program will output `True` on the first line, since `a` is `True`, even though `b` is `False`. On the second line, it will output `False`, since both `b` and `c` are `False`. 

## Exclusive Or

Python does not directly support a logical **exclusive or**, or **xor**, operation. 

```python
a = True
b = False
c = True
print((a or b) and not (a and b)) # True
print((a or c) and not (a and b)) # False
```

In this example, the first print will be `True`, since `a` is `True` but `b` is `False`. However, the second line will output `False`, since both `a` and `c` are `True` and the **xor** operation will output `False` when an even number of operands are `True`.


## Comparison Operators

We can also use the comparison operators `==`, `!=`, `<`, `<=`, `>`, and `>=` to compare variables containing numbers, which will result in a Boolean value. Here's an example showing those operators in action:

```python
x = 1
y = 2
z = 3.0

print(x < y)  # True
print(x <= 1) # True
print(x > 2)  # False
print(x >= z) # False

print(x == 1) # True
print(x != y) # True
```

As we can see, each of the comparison operators works just as we'd expect, and outputs a Boolean value of either `True` or `False`, depending on the result of the comparison.

{{% notice note "Pythonic Ways" %}}

Unlike most languages, Python allows the chaining of comparison operators.  `10 <= x <= 20` evaluates as `10<=x and x <=20`. 

You should write your code so that a broad programmer audience can understand what is going on--so there is an argument to avoid `10 <= x <= 20`.  

HOWEVER, I feel that `10 <= x <= 20` is a pretty standard math notation so I would use it.

Avoid statements like `0 < 3*(x//3) == x <7`, which checks to see if x is between 0 an 7 AND that x is evenly divisible by 3.  It is too hard to read and understand. 

{{% /notice %}}

## Order of Operations

Now that we've introduced some additional operators, we should also see where they fit in with the other operators in Python. Here is an updated list giving the appropriate _operator precedence_ for Python, with new entries in **bold**:

1. Parentheses
1. _Exponentiation:_ `**`
1. _Prefix:_ Inverse `-` 
1. _Multiplicative_: Multiplication `*`, Division `/`, Floor Division `//`, and Modulo `%`
1. _Additive_: Addition `+`, Subtraction `-`
1. **_Relational_: `<`, `>`, `<=`, `>=`, `==`, `!=`**
1. **_Logical Not_: `not`**
1. **_Logical And_: `and`**
1. **_Logical Or_: `or`**
1. _Assignment_: `=`, `+=`, `-=`, `*=`, `**=`, `/=`, `//=`, `%=`

