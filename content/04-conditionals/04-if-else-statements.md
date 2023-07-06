---
title: "If-Else Statements"
pre: "4. "
weight: 40
---

Next, let's look at the **if-else** statement. This statement allows us to choose between two different blocks of code, one to be executed when the Boolean logic expression evaluates to `true`, and a different block if the expression evaluates to `false`. 

Here's a simple flowchart that shows an **if-else** statement as the conditional construct:

![If-Else Flowchart](/images/04-cond/4.4.ifthenelse.png)

This program is very similar to the one shown on the previous page, with one major difference. Once again, this program will ask the user for a number as input, then print that number as output if the number is greater than or equal to {{< math >}}$ 0 ${{< /math >}}. However, if the input value is less than {{< math >}}$ 0 ${{< /math >}}, the program will instead print the inverse of that value by multiplying it by {{< math >}}$ -1 ${{< /math >}} before printing. Finally, the program will print `Goodbye` and terminate. 

So, if the user inputs `7`, the program will just print `7` followed by `Goodbye`. However, if the user inputs `-5`, then the program will calculate {{< math >}}$ -1 * -5 ${{< /math >}} and print `5`, followed by `Goodbye`. As we can see, the program will choose which block of code to execute depending on the Boolean value that results from evaluating `x >= 0`. Once it has executed one of those two blocks, then the program will continue with the rest of the code. 

Most programming languages implement an **if-else** statement in a format similar to this:

```tex
<before code block>
if (Boolean expression) { 
    <if code block> or <True code block>
}
else {
    <else code block> or <False code block>
}
<after code block>
```

The program is initially executing code in the `<before code block>` section. Once it reaches the `if` keyword, it will then evaluate the `<Boolean expression>` to a value of either `true` or `false`. If the expression is `true`, then it will execute the code in the `<then code block>`, followed by the code in the `<after code block>`. If the expression is `false`, the program will execute code in the `<else code block>`, followed by the code in the `<after code block>`. 

It is important to note that it is impossible for the program to execute both the `<True code block>` and the `<False code block>` during any single execution of the program. It must choose one block or the other, but it cannot do both. So, if we want each block to perform the same action, we'll have to include the appropriate code in both blocks. 