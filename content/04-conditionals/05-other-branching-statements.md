---
title: "Other Branching Statements"
pre: "5. "
weight: 50
---

Many programming languages also provide other conditional constructs that perform these same operations in different ways. However, each of these constructs can also be built using just **if** and **if-else** statements, so it is not necessary to use these constructs themselves to achieve the desired result. In many cases, they are simply provided as a convenience to the programmer in order to make the code simpler or easier to understand. 

### Switch

Some programming languages, such as C and Java, include a special type of conditional construct known as a **switch statement**, sometimes referred to as a **case statement**. Instead of using a Boolean value, which can only be `true` or `false`, a **switch statement** allows our program to choose a block of code to execute based on the many possible values of a variable, traditionally an integer value. 

This flowchart shows what a switch statement might look like in a program:

![Switch Statement Flowchart](/images/04-cond/4.5.switch.png)

In this example, the program will examine the value of the variable `x` and use it to choose a **case**, which is a code block that would be executed. Here, it would simply output a different response, depending on the value of `x`. Notice that the flowchart is essentially using several **if** statements to accomplish this task, which is essentially what the computer would do when executing this program. In addition, the program includes a special **default** case, which is executed if the value of `x` does not match any of the other cases. 

In code, a **Switch Statement** may have this general structure:

```tex
switch <variable>:
  case <value 1>: <code block 1>
  case <value 2>: <code block 2>
  case <value 3>: <code block 3>
  ...
  default: <default code block>
```

Depending on the programming language used, it _is_ possible to execute multiple code blocks inside a **switch statement**, so we may need to consult the documentation for our chosen programming language to understand how these statements work. 

## Ternary Conditional Operator

Many programming languages also include a special operator, known as a **ternary conditional operator**, sometimes referred to simply as a **ternary operator**, that is effectively a shortcut for a simple **if-else** statement that produces a single value. Here's a flowchart showing an example:

![Ternary Operator Flowchart](/images/04-cond/4.5.ternary.png)

In this example, the program accepts two variables, `x` and `y`, as input. Then, it will set the value of a third variable, `z`, to the maximum value of `x` and `y`. It does so by testing if `x > y`. If so, it will set `z = x`; otherwise it will set `z = y`. 

In general, there are two different ways that this operator is implemented. In Java and other programming languages similar to C, it looks like this example:

```tex
<variable> = <boolean expression> ? <true expression> : <false expression>
```

In Python, the ternary conditional operator looks just a bit different:

```python
<variable> = <true expression> if <boolean expression> else <false expression>
```

{{% notice info "Convention & The Ternary Operator" %}}

The appropriate use of the ternary operator is hotly debated. If it is used, it should be used to make reading the code more clear.  The code `a = a if a > 0 else -a` can be understood to find the absolute value of `a`. 

Some monstrosity like `a = foo(b) >= bar (c) ? f(b>c?2.0 * c:b+1) : g(c)!=1 ? ++c:c+1;` is better written in if-else statements.  

We suggest that if you use the ternary operator, be very judicious in its application. You may want to read the article in [Agile Software Craftsmanship](https://agiletribe.wordpress.com/2011/11/01/21-avoid-ternary-conditional-operator/) for more discussion.

Remember the goal is readable, understandable code, not diabolically clever code.

{{% /notice %}}