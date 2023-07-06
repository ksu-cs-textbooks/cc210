---
title: "Logic Operators"
pre: "2. "
weight: 20
---

{{% youtube t6y_dAY-0kg %}}

[Video Materials]({{<relref "./video">}})

Boolean logic contains four operators that perform various actions in a Boolean logic statement. Before we learn about them, let's take a minute to discuss variables in Boolean logic.

As we covered in a previous chapter, most programming languages support a special data type for storing Boolean values. That data type can only contain one of two values, `True` or `False`. So, in a Boolean logic statement, any variable can only be either `True` or `False`

For each of the operators below, we'll see both a _truth table_ and _Venn diagram_ representation of the operation. They both present the same information, but in a slightly different way. In each operation, we'll see all possible values of the variables present in the statement, and the resulting value of the operation on those variables. Since each variable can only have two values, the possibilities are limited enough that we can show all of them.

In the Venn diagrams below, each circle represents a variable.[^1] The variables are labeled in the circles on each diagram. 

[^1]: The Venn diagrams are adapted from ones found on [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Venn0000.svg) 

## Not {{< math >}}$ \neg ${{< /math >}}

The first, and simplest, Boolean logic operator is the **not**, or _negation_, operator. This operator simply negates the given Boolean value, turning `True` into `False` and `False` into `True`. When written, we use the {{< math >}}$ \neg ${{< /math >}} symbol, but most programming languages use an exclamation point `!` instead.

Below is a truth table giving the value of {{< math >}}$ \neg A ${{< /math >}} and {{< math >}}$ \neg B ${{< /math >}}, for all possible values of {{< math >}}$ A ${{< /math >}} and {{< math >}}$ B ${{< /math >}}.

| {{< math >}}$ A ${{< /math >}} | {{< math >}}$ B ${{< /math >}} | {{< math >}}$ \neg A ${{< /math >}} | {{< math >}}$ \neg B ${{< /math >}} |
|:---:|:---:|:--------:|:--------:|
| F | F | T | T |
| F | T | T | F |
| T | F | F | T |
| T | T | F | F |

We can also see the operation visually using a Venn diagram. In these drawings, assume each individual variable is `True`, and the shaded portion shows which parts of the diagram are `True` for the entire statement. 

#### {{< math >}}$ \neg A ${{< /math >}}

![Not A Venn Diagram](/images/03-bool/3.2.nota.png)

As we can see, if {{< math >}}$ A ${{< /math >}} is true, then {{< math >}}$ \neg A ${{< /math >}} represents everything in the diagram outside of the circle labeled {{< math >}}$ A ${{< /math >}}. In fact, it includes the area outside of _any_ circle, which represents the whole universe of items that are neither inside of {{< math >}}$ A ${{< /math >}} nor {{< math >}}$ B ${{< /math >}}. So, the value of {{< math >}}$ \neg A ${{< /math >}} is not affected by the value of {{< math >}}$ B ${{< /math >}} in this instance. 

We can also extend this to three variables, as shown in the truth table below. It gives the values of {{< math >}}$ \neg A ${{< /math >}}, {{< math >}}$ \neg B ${{< /math >}}, and {{< math >}}$ \neg C ${{< /math >}} for all possible values of {{< math >}}$ A ${{< /math >}}, {{< math >}}$ B ${{< /math >}}, and {{< math >}}$ C ${{< /math >}}.

| {{< math >}}$ A ${{< /math >}} | {{< math >}}$ B ${{< /math >}} | {{< math >}}$ C ${{< /math >}} | {{< math >}}$ \neg A ${{< /math >}} | {{< math >}}$ \neg B ${{< /math >}} | {{< math >}}$ \neg C ${{< /math >}} |
|:---:|:---:|:---:|:--------:|:--------:|:--------:|
| F | F | F | T | T | T |
| F | F | T | T | T | F |
| F | T | F | T | F | T |
| F | T | T | T | F | F |
| T | F | F | F | T | T |
| T | F | T | F | T | F |
| T | T | F | F | F | T |
| T | T | T | F | F | F |

The Venn diagram for this instance is very similar:

#### {{< math >}}$ \neg C ${{< /math >}}

![Not C Venn Diagram](/images/03-bool/3.2.notc.png)

As we can see, the not operation is very useful when dealing with Boolean values. 

## And {{< math >}}$ \land ${{< /math >}}

The next Boolean logic operator we'll cover is the **and**, or _conjunction_, operator. This operator works similar to the way we use "and" in our spoken language. If {{< math >}}$ A ${{< /math >}} is `True`, while {{< math >}}$ B ${{< /math >}} is also `True`, then we can say that both {{< math >}}$ A ${{< /math >}} **and** {{< math >}}$ B ${{< /math >}} are `True`. This would be written as {{< math >}}$ A \land B ${{< /math >}}. Most programming languages use two ampersands `&&` to represent the Boolean **and** operator, but some languages also include `and` as a keyword to denote this operator. 

Here is a truth table giving the value of {{< math >}}$ A \land B ${{< /math >}} for all possible values of {{< math >}}$ A ${{< /math >}} and {{< math >}}$ B ${{< /math >}}. 

| {{< math >}}$ A ${{< /math >}} | {{< math >}}$ B ${{< /math >}} | {{< math >}}$ A \land B ${{< /math >}} |
|:---:|:---:|:--------:|
| F | F | F |
| F | T | F |
| T | F | F |
| T | T | T |

As we can see, the only time that {{< math >}}$ A \land B ${{< /math >}} is `True` is when both {{< math >}}$ A ${{< /math >}} and {{< math >}}$ B ${{< /math >}} are `True`. 

Next, we can look at a Venn Diagram that represents this operation

#### {{< math >}}$ A \land B ${{< /math >}}

![A And B Venn Diagram](/images/03-bool/3.2.aandb.png)

As we can see, only the center of the Venn diagram is shaded, representing the parts of the diagram that are both in {{< math >}}$ A ${{< /math >}} and {{< math >}}$ B ${{< /math >}} at the same time.

This operation also easily extends to three variables. This truth table gives the value of {{< math >}}$ A \land B \land C ${{< /math >}} for all possible values of {{< math >}}$ A ${{< /math >}}, {{< math >}}$ B ${{< /math >}}, and {{< math >}}$ C ${{< /math >}}.

| {{< math >}}$ A ${{< /math >}} | {{< math >}}$ B ${{< /math >}} | {{< math >}}$ C ${{< /math >}} | {{< math >}}$ A \land B \land C ${{< /math >}} |
|:---:|:---:|:---:|:--------:|
| F | F | F | F |
| F | F | T | F |
| F | T | F | F |
| F | T | T | F |
| T | F | F | F |
| T | F | T | F |
| T | T | F | F |
| T | T | T | T |

The Venn diagram for this instance is very similar to the one above:

#### {{< math >}}$ A \land B \land C ${{< /math >}}

![A And B and C Venn Diagram](/images/03-bool/3.2.aandbandc.png)

Once again, we see that only the very center of the diagram is shaded, as expected.

## Or {{< math >}}$ \lor ${{< /math >}}

The third Boolean operator is the **or**, or _disjunction_, operator. It is somewhat similar to how we use the word "or" in our spoken language, with a major difference. This operator would be written as {{< math >}}$ A \lor B ${{< /math >}}. Most programming languages use two vertical pipes `||` to represent the Boolean **or** operator, but some languages also include `or` as a keyword to denote this operator. 

Consider ordering food at a restaurant as an example. On the menu, you might see the statement "Soup or Salad" as one of the options for your meal. This means that you must choose either "soup" or "salad" to go with your meal, but usually you aren't allowed to have both (at least, without paying more). 

Now, consider a similar statement, {{< math >}}$ A \lor B ${{< /math >}}. If either {{< math >}}$ A ${{< /math >}} or {{< math >}}$ B ${{< /math >}} are `True`, we would say that {{< math >}}$ A \lor B ${{< /math >}} is also `True`. However, if _both_ {{< math >}}$ A ${{< /math >}} and {{< math >}}$ B ${{< /math >}} are `True`, we would _also_ say that {{< math >}}$ A \lor B ${{< /math >}} is `True`. So, the Boolean **or** operator will return `True` when both inputs are `True`, which differs from how we use it in spoken language.

Here is a truth table giving the value of {{< math >}}$ A \lor B ${{< /math >}} for all possible values of {{< math >}}$ A ${{< /math >}} and {{< math >}}$ B ${{< /math >}}. 

| {{< math >}}$ A ${{< /math >}} | {{< math >}}$ B ${{< /math >}} | {{< math >}}$ A \lor B ${{< /math >}} |
|:---:|:---:|:--------:|
| F | F | F |
| F | T | T |
| T | F | T |
| T | T | T |

As we can see, the only time that {{< math >}}$ A \lor B ${{< /math >}} is `False` is when both {{< math >}}$ A ${{< /math >}} and {{< math >}}$ B ${{< /math >}} are `False`. As long as at least one of the values is `True`, the whole statement is `True`. 

Next, we can look at a Venn Diagram that represents this operation

#### {{< math >}}$ A \lor B ${{< /math >}}

![A Or B Venn Diagram](/images/03-bool/3.2.aorb.png)

As we can see, both circles are completely shaded, showing that {{< math >}}$ A \lor B ${{< /math >}} contains all items in either {{< math >}}$ A ${{< /math >}} or {{< math >}}$ B ${{< /math >}}, or both {{< math >}}$ A ${{< /math >}} and {{< math >}}$ B ${{< /math >}} at the same time. 

This operation also easily extends to three variables. This truth table gives the value of {{< math >}}$ A \lor B \lor C ${{< /math >}} for all possible values of {{< math >}}$ A ${{< /math >}}, {{< math >}}$ B ${{< /math >}}, and {{< math >}}$ C ${{< /math >}}.

| {{< math >}}$ A ${{< /math >}} | {{< math >}}$ B ${{< /math >}} | {{< math >}}$ C ${{< /math >}} | {{< math >}}$ A \lor B \lor C ${{< /math >}} |
|:---:|:---:|:---:|:--------:|
| F | F | F | F |
| F | F | T | T |
| F | T | F | T |
| F | T | T | T |
| T | F | F | T |
| T | F | T | T |
| T | T | F | T |
| T | T | T | T |

The Venn diagram for this instance is very similar to the one above:

#### {{< math >}}$ A \lor B \lor C ${{< /math >}}

![A Or B Or C Venn Diagram](/images/03-bool/3.2.aorborc.png)

Once again, we see that all parts of the Venn diagram are shaded, except for the part outside of all the circles.

## Exclusive Or {{< math >}}$ \oplus ${{< /math >}}

The last Boolean operator we'll cover is **exclusive or**, or _exclusive disjunction_. We'll sometimes see this referred to as **xor** as well. When written, we use the {{< math >}}$ \oplus ${{< /math >}} symbol. However, not all programming languages have implemented this operator, so there is no consistently used symbol in programming.

This operator works in the same way that "or" works in our spoken language. Recall the "Soup or Salad" example from earlier. The **exclusive or** operation is `True` if only one of the inputs is `True`. If both inputs are `True`, the output is `False`.

Here is a truth table giving the value of {{< math >}}$ A \oplus B ${{< /math >}} for all possible values of {{< math >}}$ A ${{< /math >}} and {{< math >}}$ B ${{< /math >}}. 

| {{< math >}}$ A ${{< /math >}} | {{< math >}}$ B ${{< /math >}} | {{< math >}}$ A \oplus B ${{< /math >}} |
|:---:|:---:|:--------:|
| F | F | F |
| F | T | T |
| T | F | T |
| T | T | F |

As we can see, the result is `True` when either {{< math >}}$ A ${{< /math >}} or {{< math >}}$ B ${{< /math >}} are `True`, but it is `False` if both of them are `True`, or if both of them are `False`. 

As a Venn diagram, it would look like this:

#### {{< math >}}$ A \oplus B ${{< /math >}}

![A Xor B Venn Diagram](/images/03-bool/3.2.axorb.png)

As we can see, the parts of the diagram in {{< math >}}$ A ${{< /math >}} and {{< math >}}$ B ${{< /math >}} are shaded, but the center part, which is in both {{< math >}}$ A ${{< /math >}} and {{< math >}}$ B ${{< /math >}}, is _not_ shaded. 

This operation is most interesting when extended to three variables. This truth table gives the value of {{< math >}}$ A \oplus B \oplus C ${{< /math >}} for all possible values of {{< math >}}$ A ${{< /math >}}, {{< math >}}$ B ${{< /math >}}, and {{< math >}}$ C ${{< /math >}}.

| {{< math >}}$ A ${{< /math >}} | {{< math >}}$ B ${{< /math >}} | {{< math >}}$ C ${{< /math >}} | {{< math >}}$ A \oplus B \oplus C ${{< /math >}} |
|:---:|:---:|:---:|:--------:|
| F | F | F | F |
| F | F | T | T |
| F | T | F | T |
| F | T | T | F |
| T | F | F | T |
| T | F | T | F |
| T | T | F | F |
| T | T | T | T |

The Venn diagram for this instance is as follows:

#### {{< math >}}$ A \oplus B \oplus C ${{< /math >}}

![A Xor B Xor C Venn Diagram](/images/03-bool/3.2.axorbxorc.png)

In this instance, we see the parts of the diagram representing items that are just in {{< math >}}$ A ${{< /math >}}, {{< math >}}$ B ${{< /math >}}, and {{< math >}}$ C ${{< /math >}} alone are shaded, as we'd expect. However, we also see the center of the diagram, representing items in {{< math >}}$ A \land B \land C ${{< /math >}} is also shaded. Interesting, isn't it? Let's see if we can break it down.

Just like we hopefully remember from mathematics, when we have multiple operations chained together, we must respect the order of operations. So, we can insert parentheses into the original statement to show how it would actually be calculated:

{{< math >}}$ ((A \oplus B) \oplus C) ${{< /math >}}

Now, let's assume that all three of our variables are `True`, represented by {{< math >}}$ T ${{< /math >}}. So, we can reduce the first part as follows:

{{< math >}}$$((A \oplus B) \oplus C) $${{< /math >}}
{{< math >}}$$((T \oplus T) \oplus T) $${{< /math >}}
{{< math >}}$$(F \oplus T) $${{< /math >}}

As we can see, since {{< math >}}$ A ${{< /math >}} and {{< math >}}$ B ${{< /math >}} are both `True`, we find that {{< math >}}$ A \oplus B ${{< /math >}} is `False`, as expected. Now, we can continue to reduce the expression:

{{< math >}}$$ (F \oplus T) $${{< /math >}}
{{< math >}}$$ T $${{< /math >}}

In this case, since only one of the two operands is `True`, the result of **exclusive or** would also be `True`. Therefore, {{< math >}}$ A \oplus B \oplus C ${{< /math >}} is `True` when all three variables are `True`. In short, a string of **exclusive ors** is `True` if an _odd_ number of the variables are `True`, and it is `False` if an _even_ number of variables are `True`. 

Not all languages support an logical **exclusive or**. Alternate forms are {{< math >}}$ ( A \lor B) \land \lnot (A \land B) ${{< /math >}} or {{< math >}}$ (\lnot A \land B) \lor (A \land \lnot B) ${{< /math >}}.

{{% notice note "Soup, Salad, or Breadsticks?" %}}

At some restaurants, you are given a choice of not just two, but three items to go with your meal. Of course, the intent is for you to choose just one of the three items listed. 

However, now that you understand how **exclusive or** works, you might see how you could get all three items instead of just one! Logic is pretty powerful, isn't it?

{{% /notice %}}

## Comparators

Finally, it is worth discussing other operators that can result in a Boolean value. The most important of these operators are the _comparators_, which compare two values and return a result that is either `True` or `False`. We've definitely seen these operators before in mathematics, but may not have actually realized that they result in a Boolean value. 

Below is a table giving the common comparators used in programming, along with an example of how they might be used:

| Name | Operator | Symbol | `True` Example | `False` Example |
|:----:|:--------:|:------:|:--------------:|:---------------:|
| Equal                    | {{< math >}}$ = ${{< /math >}}    | `==` | `1 == 1` | `1 == 2` |
| Not Equal                | {{< math >}}$ \neq ${{< /math >}} | `!=` | `1 != 2` | `1 != 1` |
| Greater Than             | {{< math >}}$ > ${{< /math >}}    | `>`  | `2 > 1`  | `1 > 2`  |
| Greater Than or Equal To | {{< math >}}$ \geq ${{< /math >}} | `>=` | `1 >= 1` | `1 >= 2` |
| Less Than                | {{< math >}}$ < ${{< /math >}}    | `<`  | `1 < 2`  | `2 < 1`  |
| Less Than or Equal To    | {{< math >}}$ \leq ${{< /math >}} | `<=` | `1 <= 1` | `2 <= 1` |

That covers all of the basic operators and symbols in Boolean logic. On the next page, we'll learn how to combine them together and create logical statements using the rules of Boolean algebra.
