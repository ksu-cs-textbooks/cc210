---
title: "Other Branching Statements"
pre: "6. "
weight: 60
---

Many programming languages also provide other conditional constructs that perform these same operations in different ways. However, each of these constructs can also be built using just **If** and **If-Else** statements, so it is not necessary to use these constructs themselves to achieve the desired result. In many cases, they are simply provided as a convenience to the programmer in order to make the code simpler or easier to understand. 

## Jump Tables

In assembly and machine-code there are control structures known as jump- or <a href="https://en.wikipedia.org/wiki/Branch_table">branch-tables</a>. Conceptually, when the program arrives at a branch table, it looks at the current value of a variable and then executes exactly one row of the table based on that value. Each row of the table is an independent "code block", and only on row can be executed.  Kind of like trains entering a rail-yard^[Actual assembly/machine level implementation is done with off-sets and unconditional jumps, hence the name jump table.].

![Rail yard](/images/04-cond/Railyard.png)

The key concept is each value follows exactly one path.

### Switch

Some programming languages, such as C and Java, include a special type of conditional construct known as a **Switch Statement**, sometimes referred to as a **Case Statement**. Instead of using a Boolean value, which can only be `true` or `false`, a **Switch Statement** allows our program to choose a block of code to execute based on the many possible values of a variable, traditionally an integer value. 

This flowchart shows what a switch statement might look like in a program:

![Switch Statement Flowchart](/images/04-cond/4.5.switch.png)

In this example, the program will examine the value of the variable `x` and use it to choose a **case**, which is a code block that would be executed. Here, it would simply output a different response, depending on the value of `x`. Notice that the flowchart is essentially using several **If** statements to accomplish this task, which is essentially what the computer would do when executing this program. In addition, the program includes a special **default** case, which is executed if the value of `x` does not match any of the other cases. 

In code, a **Switch Statement** may have this general structure:

```tex
switch <variable>:
  case <value 1>: <code block 1>
  case <value 2>: <code block 2>
  case <value 3>: <code block 3>
  ...
  default: <default code block>
```

Depending on the programming language used, it _is_ possible to execute multiple code blocks inside a **Switch Statement**, so we may need to consult the documentation for our chosen programming language to understand how these statements work. 

### IF-ELSE-IF

The Switch flow chart can also be implemented with nested IF statements.

![Switch Statement Flowchart](/images/04-cond/SwitchIF.png)

```
x <- Input
IF (x == 1){
    DISPLAY(A)
    }
ELSE {
   IF (x == 2){
        DISPLAY(B)
   }
   ELSE{
       IF (x ==3){
           DISPLAY(C)
       }
       ELSE {
           DISPLAY(Error!)
       }
   }
}

```

Using IF-ELSE-IF allows more flexibility (like ranges of values) in the jumps.

An important feature of the jump table is every possible value is assigned an execution path.  This is the purpose of the "default"-case or final "ELSE".  These paths often display some type error message indicating that an unexpected value was encountered.

{{% notice info "Convention & Jump Tables" %}}

<b>ALWAYS</b> include a default-case or final ELSE which contains the logic for what to do when a value is not in the expected range.  Often time you will terminate the program if this happens.

It is always acceptable to use IF-ELSE-IF.  This communicates clearly that the original programmer expected a mutually exclusive branching, and comprehensively dealt with all expected outcomes.  If some future modifier of the code reaches this statement, they  know they too must deal with every possible case; i.e. leave no "holes" in the logic.

Use of Switch is more language idiosyncratic.  In some language implementations, the "case" statements are not always mutually exclusive, and this can make the original programmer's intent unclear.  Not all language bother to implement a "Switch" statement.  

{{% /notice %}}

## Ternary Conditional Operator

Many programming languages also include a special operator, known as a **Ternary Conditional Operator**, sometimes referred to simply as a **Ternary Operator**, that is effectively a shortcut for a simple **If-Else** statement that produces a single value. Here's a flowchart showing an example:

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

The appropriate use of the ternary operator is hotly debated--this may be a sad commentary on what passes for excitement in the programming field. If it is used, it should be used to make reading the code more clear.  The code `a = a if a>0 else -a` can be understood to find the absolute value of `a`. 

Some monstrosity like `a = foo(b) >= bar (c) ? f(b>c?2.0 * c:b+1) : g(c)!=1 ? ++c:c+1;` is better written in if-else statements.  

We suggest that if you use the ternary operator, be very judicious in its application. You may want to read the article in [Agile Software Craftsmanship](https://agiletribe.wordpress.com/2011/11/01/21-avoid-ternary-conditional-operator/) for more discussion.

Remember the goal is readable, understandable code  -- not diabolically clever code.

{{% /notice %}}