---
title: "If Statements"
pre: "3. "
weight: 30
---

The first type of conditional construct we'll cover is the **If** statement. This type of statement allows us to build a block of code which will only be executed if the given Boolean expression evaluates to `true`. 

Here's a simple flowchart that shows an **If** statement as the conditional construct:

![If Flowchart](/images/04-cond/4.3.ifthen.png)

This flowchart represents a program which will ask the user for a number as input, then print that number as output only if the number is greater than {{< math >}}$ 0 ${{< /math >}}. Then, the program will print `Goodbye` and terminate. So, if the user inputs `-5`, the program will only print `Goodbye`. However, if the user inputs `7`, then the program will first print `7` followed by `Goodbye`. As we can see, the program will execute the section of code that prints the value of the variable if and only if the value of `x > 0` is `true`. Otherwise, it will skip that code and continue with the rest of the program.

Notice that this statement does not include any operations in the case that `x > 0` is `false`. Instead, the `false` branch points downward, and merges with the `true` branch after the program outputs the value of `x`. This is the main difference between an **If** statement and an **If-Else** statement, which we'll cover on the next page.

Most programming languages implement an **If** statement in a format similar to this:

```tex
<before code block>
IF <Boolean expression> {
    <if code block> or <True block>
    }
<after code block>
```

The program is initially executing code in the `<before code block>` section. Once it reaches the `if` keyword, it will then evaluate the `<Boolean expression>` to a value of either `true` or `false`. If the expression is `true`, then it will execute the code in the `<if code block>`, followed by the code in the `<after code block>`. If the expression is `false`, the program will simply continue executing code in the `<after code block>`, bypassing the other block entirely. 

{{% notice note "IF vs. IF-THEN" %}}

You may see the <b>IF</b> statement referred to as the <b>IF-THEN</b> statement.  At the dawn of high level programming languages (1957), there was Fortran.  FORTRAN (original syntax) was the first commercially available high level programming language; it is still in use today in many scientific and mathematics heavy applications.  Its syntax for this structure is

```tex
IF <condition> THEN <action>
```

This follow closely it first order logic representation `<condition> --> <action>` , condition <b>implies</b> action.  In propositional Logic, this is read to mean "if the condition is true, it follows that the action must also be true".

In the early 1970s a new high level programming language, "C", enters the ecosystem and it would come to dominate the programming landscape by the 1990s.  C remains in active development, has a huge industry code base and greatly influenced the syntax and style of later languages.  Notably, C dropped the "THEN". 

```tex
if (condition) { <action> }
```

This sets the stage for one of the enduring arcane debates in computer science -- which form is "correct".  Without arguing for which is best, we have chosen the style that most resembles Java and Python syntax.

{{% /notice %}}