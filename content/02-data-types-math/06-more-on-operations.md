---
title: "More on Operations"
pre: "6. "
weight: 60
---

# Operation

Computer Science, thus programming, has its roots in Mathematics and uses a lot math technical jargon.  Unfortunately this means you need to be familiar with some of this jargon.

An operation is a fancy math term for "do something", but carries with it its own set of vocabulary. An operation is composed of:

1. an operator (one or more symbols) 
2. operands (one or more pieces of data)
3. a semantic meaning (i.e. what the operator does)

## Binary Operations

Binary operations operate on two inputs. This class of operations should be familiar from arithmetic.  Its format is 

```tex
    operand1 operator operand2
        2     +        4
        x     +        y
```

where the operator is typically some type of symbol.

Operator symbols are typically overloaded in programming languages; they do different things based on the types of the operands.  For example, a typical language might do the following base on the plus sign.

|  Type Operand 1 |  Type Operand 2 |  Result Type|
|-------|---------|-----------|
|int <br> 2 |int <br> 4| int <br> 6|
|int <br> 2 |float <br> 4.0| float <br> 6.0|
|float <br> 1.1 |float <br> 3.7| float <br> 4.8|
|String <br> "2" |String <br> "4"| String <br> "24"|
|String <br> "2" |int <br> 4| **Error** operation not defined for an operand of type String and int|

You must refer to your language's documentation for how each operator functions. Operator behavior, particularly in the presence of mixed-type operands varies from language to language.

{{% notice info "Infix vs. Prefix" %}}

The form `operand1 operator operand2` is called infix notation.  However, there is another construct called prefix, that looks like `operator operand1 operand2` or `  + 2 4`.  For technical reasons it is easier to write programming languages that use prefix notation.  In OOP, you may see prefix notations used for methods and classes which were adapted from a functional programming language where prefix notation is more common.
 
{{% /notice %}}

## Unary Operations

There are some operations that have just one operand, these are called unary operations.  The typical form is ` operator operand` or ` operand operator`.  A fairly common unary operator is `!` for the logical operation "not".  `!True` is the same as `False`, more on this in the chapter on Boolean Logic.

