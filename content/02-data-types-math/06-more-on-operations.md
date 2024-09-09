---
title: "More on Operations"
pre: "6. "
weight: 60
---

# Operation

Computer Science, and therefore programming, has its roots in mathematics and uses a lot technical terms and jargon from math.  Unfortunately this means that most programmers need to be familiar with some of this jargon.

An **operation** is a fancy math term for "do something", but carries with it its own set of vocabulary. An operation is composed of:

1. an **operator** (one or more symbols) 
2. **operands** (one or more pieces of data)
3. a semantic meaning (i.e. what the operator does)

## Binary Operations

Binary operations operate on two inputs. This class of operations should be familiar from arithmetic.  Its format is 

```tex
    operand1 operator operand2
        2     +        4
        x     +        y
```

where the operator is typically some type of symbol.

{{% notice info "Binary Operations" %}}

Note that in this case the term **binary** refers to the fact that the operation is performed on exactly 2 operands, and not that the data is stored in a base-2 (binary) data format. 

This can lead to some confusion among programmers when referring to bitwise operators, which are operators that perform actions on individual bits in a piece of data. Many programmers mistakenly call these "binary" operators since they operate on data at the binary level, but the proper term is "bitwise" operators.

{{% /notice %}}

Operator symbols are typically overloaded in programming languages, which means that they can do different things based on the types of the operands.  For example, a typical language might do any of the following operations when the plus sign `+` is used as the operator, depending on the types of the individual operands:

|  Type Operand 1 |  Type Operand 2 |  Result Type|
|-------|---------|-----------|
|int <br> 2 |int <br> 4| int <br> 6|
|int <br> 2 |float <br> 4.0| float <br> 6.0|
|float <br> 1.1 |float <br> 3.7| float <br> 4.8|
|String <br> "2" |String <br> "4"| String <br> "24"|
|String <br> "2" |int <br> 4| **Error** operation not defined for an operand of type String and int|

We will have to refer to our language's documentation for how each operator functions. Operator behavior, particularly in the presence of mixed-type operands varies from language to language.

{{% notice info "Infix vs. Prefix" %}}

The form `operand1 operator operand2` is called infix notation.  However, there is another construct called prefix, that looks like `operator operand1 operand2` or `  + 2 4`.  For technical reasons it is easier to write programming languages that use prefix notation.  In OOP, we may see prefix notations used for methods and classes, which were adapted from a functional programming language where prefix notation is more common.
 
{{% /notice %}}

## Unary Operations

There are some operations that have just one operand, these are called unary operations.  The typical form is `operator operand` or  `operand operator`.  A fairly common unary operator is `!` for the logical operation "not".  `!True` is the same as `False`. We'll introduce more of these operators in a later chapter.

