---
title: "An Alternative Approach"
pre: "5. "
weight: 50
---

## Limitations of the Venn Diagram

Not everyone finds the use of Venn diagrams easy or natural. Consider the following problem:

```
Determine if the value of the variable x is greater than 10, less than or equal to thirty and either divisible by both 2 and 3 or by 7.
```

If we Venn diagram this 

![Venn Diagram](/images/03-bool/3.4.1complicated_Venn.png)

It does not result in a graphic that is easily translatable to a line of code.

### Write the Equation in Pseudocode

Another approach would be to write this in pseudocode, lets start by adding the obvious logical statements to :

```
Determine if the value of the variable x is :  
greater than 10,  
less than or equal to thirty  
and either  
divisible by both 2 and 3  
or by 7.
```

Clearly the `and`s and `or`s represent their logical operations.  Also we know that comma separated listed are really just `and`s so 

```
Determine if the value of the variable x is :
greater than 10 AND 
less than OR equal to thirty 
AND either 
divisible by both 2 AND 3 
OR by 7.
```
Next we need to get rid of the implied subjects and make them explicit.  

```
Determine if the value of the variable x is :
x greater than 10 AND 
x less than thirty OR x equal to thirty 
AND either 
x divisible by 2 AND x divisible by 3 
OR x divisible by 7.
```

Now we plug in the math symbols.  First recall that if number_1 is divisible by number_2, number_1 % number_2 is zero.  Next, recall that most languages use `==` to mean 'equal to'.  This is because, as we learned in chapter 2, `=` is used for assigning a value to a variable.

```
Determine if the value of the variable x is :
x > 10 AND 
x < 30 OR x == 30 
AND either 
x % 2 == 0 AND x % 3 ==  0 
OR x % 7 == 0.
```
Now lets pause to see if we missed any parenthesis.  "Less than or equal to" is a math term that that always goes together,  most languages will have an operator for this, so so we probably should group those together.  Also, "by both 2 and 3" should be grouped.


```
Possible pseudocode is 
x > 10 AND (x < 30 OR x == 30) AND (x % 2 == 0 AND x % 3 == 0)  OR x % 7 == 0
```

This line of pseudocode is certainly easier translate into a programming language than the Venn Diagram

## Operations tree

One way to check if your pseudo code is correct is to build a "operations tree".  You may be familiar with the technique from your earlier math career. You find the first operation which will be done and build "up" from there.

![Basic Operations Tree](/images/03-bool/3.4.1ot1_7.png)

Logical operators follow their order of precedence, then flow from left to right.  Since we have 2 sets of parenthesis, we will write those operations first.

![Parenthesis First](/images/03-bool/3.4.1ot1_2.png)

Next we have 2 `AND`s and an `OR`, so we work those in from left to right.

![x<10 AND ...](/images/03-bool/3.4.1ot1_3.png)
---

![... x == 30)AND (x % 2 ...)](/images/03-bool/3.4.1ot1_4.png)
---

![ ... == 0) OR x % 7 ...](/images/03-bool/3.4.1ot1_5.png)

Next we can "desk check" this tree.  We know the number 7 should be rejected.  However, our equation will accept it:

![Equation is in error](/images/03-bool/3.4.1ot1_8.png)

Our mistake is that " ... and divisible by both 2 and 3 or by 7" actually required another set of parenthesis to carry the English meaning into the equation.  The correct pseudo code is :

```
Correct pseudocode is 
x > 10 AND (x < 30 OR x == 30) AND ((x % 2 == 0 AND x % 3 == 0)  OR x % 7 == 0)
```

You may want to try and make an operations tree for this code.

{{% notice info "Simplifying Boolean Algebra Statements" %}}

There is a technique in Computer Engineering used to express complicated Boolean expressions in the fewest number of operations.  It is called the K-Map or <a href ="https://en.wikipedia.org/wiki/Karnaugh_map">Karnaugh map</a> technique.  It is typically taught in introductory classes. 

Certain applications areas of Computer Science, particularly sub-fields in Artificial Intelligence and Control Systems, end up producing long strings of Boolean algebra.  <b>IF</b> you find yourself drawn to one of the areas, I recommend picking up this technique.  An approachable explanation is provided in chapters 2 and 3 of M Mano and M Ciletti's book "Digital Design". An edition is probably available on-line or used.  Look for the chapters on "Logic Gates" and "Gate Minimization".

{{% /notice %}}

