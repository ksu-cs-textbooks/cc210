---
title: "Operators"
pre: "2. "
weight: 20
date: 2019-02-07T10:53:26-05:00
hidden: true
---

{{< youtube t6y_dAY-0kg >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

Let's review the four major operators in Boolean logic.

First, and probably simplest, is the Not operator. When written, it usually looks like this sideways L symbol.

There are a couple of different ways to understand how these operators work. First and foremost is through the use of a "truth table." In a truth table, we see all possible combinations of values, both true and false for the Boolean variables in a statement. So, a statement with two variables, A and B, would have 4 possible combinations of values in a truth table. Then, we can add a column to show the result of each operation on those variables. In this example, we have a column for the result of "NOT A" and "NOT B"

As we can see, anytime that A is true, the result of Not A is false. The same goes for the values of B and Not B. As expected, the Not operation simply makes a true value false, and a false value true. In effect, it is the same as the negative sign in mathematics.

The other way to think about these Boolean logic operations is using a Venn diagram. In these diagrams, anything inside of the circle labelled with that variable represents that variable being true, whereas everything outside of that circle is where that variable is false. So, the shaded part of this diagram shows where Not A would be true. Notice that it not only includes the part of B that isn't in A, but it includes the part of the diagram outside all other circles too.

We can also expand this view to include more variables. The textbook page below this video includes truth tables for these three-variable diagrams, but they are hopefully pretty easy to follow. In this diagram, the shaded portion represents Not C.

Next, let's look at the AND operation. The AND operation is true if both operands are true. It is very similar to how we use the word and in our spoken language. When written, we use this upward angle symbol.

In a truth table, we can see that the result of A and B is only true when both A and B are true. If you think about it, it totally makes sense, right? We want to know if A AND B are true, so the result should only be true if both A and B are true.

As a Venn diagram, we see that the only shaded portion is the part included in the circles for both A and B. Once again, that should fit pretty well with what we expect.

If we expand out to three variables, the Venn diagram still includes just the part that is inside the circle for all three variables.

The next operation we can review is the OR operation. The OR operation is true if at least one of the operands is true. So, this is very similar to how we would phrase the question in our spoken language: "Are either A or B true?"

As a truth table, we can see that the only time the value of A or B is false is when both A and B are false. Otherwise, since at least one of the variables is true, the overall statement is true as well.

So, when we view this as a truth table, we see that it includes all parts of the diagram in at least one circle.

If we expand it out to three variables, we see that it still includes all of the diagram, just like we'd expect.

Finally, the last operation is the exclusive or, or XOR operation. This operation is true if either one side or the other is true, but not both. In essence, this is similar to the way a restaurant might use "or" on a menu, when it says you can have either "soup or salad." In most cases, you can't have both (at least, without paying a bit extra).

As a truth table, we see that A xor B is false if A and B are the same value, either both true or both false. It is only true if either A or B are true, but not both at the same time.

As a Venn diagram, we see that it only includes the parts of the diagram exclusively in one circle or the other.

However, something strange happens when we expand this operation to three variables. First, let's look at A xor B in a three variable diagram. This is the same as before.

Now, imagine that we want to calculate the XOR of that diagram with the diagram that has just C highlighted. Notice that we'll still highlight the part of C that isn't in any other diagram. Likewise, the parts that would be shaded in both diagrams are not shaded in the result. However, notice that since the very center is not shaded by A xor B, it WOULD get shaded when that result is xored with C. So, the resulting diagram looks something like this.

This leads to some pretty fun results. For example, next time you are at an Italian restaurant and they offer you the choice of soup, salad, or breadsticks to go with your meal, try to convince the server that you should be able to get all three by the rules of Boolean logic!
