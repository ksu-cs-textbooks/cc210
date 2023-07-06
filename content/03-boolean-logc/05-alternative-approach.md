---
title: "An Alternative Approach"
pre: "5. "
weight: 50
---

## Venn Diagram Limitations

Not everyone finds the use of Venn diagrams easy or natural. Consider the following problem:

```
Determine if the value of the variable x is greater than 10, less than or equal to 30, and either divisible by both 2 and 3 or by 7.
```

A Venn diagram of this statement would look something similar to this example:

![Venn Diagram](/images/03-bool/3.4.1complicated_Venn.png)

Unfortunately, it does not result in a graphic that is easily translatable to a Boolean logic statement. So, we'll probably have to take another approach.

### Pseudocode

Instead, we can use the original problem statement as the structure to build a pseudocode representation that can eventually be translated to any programming language. We'll begin by breaking down the original problem statement into smaller parts, as shown below:

```
Determine if the value of the variable x is: 
  greater than 10
  less than or equal to 30 
  and either  
    divisible by both 2 and 3
    or by 7.
```

We've also added in a bit of indentation, just to make it easier to see the various parts of the statement.

Clearly the `and`s and `or`s in the original statement can be replaced with their Boolean equivalents. We'll use capitalized `AND`, `OR` and `NOT` operators in text. Also, we can deduce that statements in a comma separated list should also be combined with `AND`, so we can update our statement as follows:

```
Determine if the value of the variable x is: 
  greater than 10
  AND less than or equal to 30 
  AND either  
    divisible by both 2 AND 3
    OR by 7.
```

Next, we should try to make each statement closely resemble a written expression in code by adding in the implied subject of each statement and making them explicit. In most cases, we'll add the variable `x` to the statement, as shown here:

```
Determine if the value of the variable x is: 
  x greater than 10
  AND x less than or equal to 30 
  AND either  
    x divisible by 2 AND x divisible by 3
    OR x divisible by 7.
```

Notice how the statement `divisible by both 2 and 3` was split into two parts. Each Boolean logic comparator requires a variable on each side, so we cannot write `x divisible by 2 AND 3` as a valid statement. Instead, we have to split it into two statements, `x divisible by 2 AND x divisible by 3`. We also have to expand the line `OR by 7` to clarify that it is also checking if `x` is divisible by 7, so we updated it to be `x divisible by 7`. 

Now we can plug in the associated Boolean comparators and mathematical operators. Recall that we can check if a number is divisible by another number using the modulo operator; if that value modulo the divisor is 0, then we know the number is evenly divisible by the divisor. We're also going to use the double equals sign `==` to denote equality, which is used in most programming languages. 

```
Determine if the value of the variable x is: 
  x > 10
  AND x <= 30 
  AND either  
    x % 2 == 0 AND x % 3 == 0
    OR x % 7 == 0.
```

Once we have that, we can go through and add in any missing parentheses. Notice that we originally used some tabs separate the various parts of the original statement, and those should closely align with where we need to add parentheses. 

So, one possible way to interpret this statement is as follows:

```
x > 10 AND x <= 30 AND ((x % 2 == 0 AND x % 3 == 0) OR x % 7 == 0)
```

This line of pseudocode is certainly easier translate into a programming language than using the Venn Diagram!

{{% notice info "Simplifying Boolean Algebra Statements" %}}

There is a technique in computer engineering used to express complicated Boolean expressions in the fewest number of operations.  It is called the K-Map or [Karnaugh Map](https://en.wikipedia.org/wiki/Karnaugh_map) technique. It is typically taught in introductory classes. 

Certain applications areas of computer Science, particularly sub-fields such as artificial intelligence and control systems, end up producing long strings of Boolean algebra. Using both Karnaugh Maps and Boolean algebra techniques are used to reduce those statements. 

{{% /notice %}}

