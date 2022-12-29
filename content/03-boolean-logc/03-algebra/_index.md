---
title: "Boolean Algebra"
pre: "3. "
weight: 30
---

Of course, one of the major goals of George Boole's work was not only to create a system of logic that _looked_ like math, but also to be able to apply some of the same techniques from math within that system. _Boolean Algebra_ is a form of algebra that can be done on _boolean expressions_, and it contains many of the same laws and operations that we've already learned from algebra. 

## Boolean Expressions

A Boolean expression is any expression that results in a Boolean value. They consist of the values `True` and `False`, sometimes denoted as {{< math >}}$ T ${{< /math >}} and {{< math >}}$ F ${{< /math >}}, literal values, and variables which are usually lower-case letters, combined using the operations discussed on the previous page. Here are a few examples:

{{< math >}}$$ T \land x $${{< /math >}}
{{< math >}}$$ (\neg x \land y) \oplus z $${{< /math >}}
{{< math >}}$$ (5 < x) \land (y > 8) $${{< /math >}}

## Laws of Boolean Algebra

Boolean algebra contains many of the same laws found in algebra. Here is a table listing some of these laws with an example for each. If the law does not list a specific operation, then in general it will work for all operations. 

| Name | Example |
|:----:|:-------:|
| Associative | {{< math >}}$ x \land (y \land z) \iff (x \land y) \land z ${{< /math >}} |
| Commutative | {{< math >}}$ x \land y \iff y \land x ${{< /math >}} |
| Idempotence | {{< math >}}$ x \land x \iff x ${{< /math >}} |
| Distributive {{< math >}}$ \land ${{< /math >}} over {{< math >}}$ \lor ${{< /math >}} | {{< math >}}$ x \land (y \lor z) \iff (x \land y) \lor (x \land z) ${{< /math >}} |
| Distributive {{< math >}}$ \lor ${{< /math >}} over {{< math >}}$ \land ${{< /math >}} | {{< math >}}$ x \lor (y \land z) \iff (x \lor y) \land (x \lor z) ${{< /math >}} |
| Identity {{< math >}}$ \land ${{< /math >}} | {{< math >}}$ x \land T \iff x ${{< /math >}} |
| Identity {{< math >}}$ \lor ${{< /math >}} | {{< math >}}$ x \lor F \iff x ${{< /math >}} |
| Eliminate {{< math >}}$ \land ${{< /math >}} | {{< math >}}$ x \land F \iff F ${{< /math >}} |
| Eliminate {{< math >}}$ \lor ${{< /math >}} | {{< math >}}$ x \lor T \iff T ${{< /math >}} |
| Complement {{< math >}}$ \land ${{< /math >}} | {{< math >}}$ x \land \neg x \iff F ${{< /math >}} |
| Complement {{< math >}}$ \lor ${{< /math >}} | {{< math >}}$ x \lor \neg x \iff T ${{< /math >}} |
| Double Negative | {{< math >}}$ \neg(\neg x) \iff x ${{< /math >}} |
| Or Absorption | {{< math >}}$ x \lor (x \land y) \iff x ${{< /math >}} |
| And Absorption | {{< math >}}$ x \land (x \lor y) \iff x ${{< /math >}} |

## De Morgan's Laws

{{% youtube chH10DQfbOc %}}

[Video Materials]({{<relref "./video">}})

![Augustus De Morgan](/images/03-bool/3.3.demorgan.wikimedia.jpg)[^1]

[^1]: File:De Morgan Augustus.jpg. (2018, January 1). Wikimedia Commons, the free media repository. Retrieved 19:51, January 10, 2019 from https://commons.wikimedia.org/w/index.php?title=File:De_Morgan_Augustus.jpg&oldid=275794962.

There is one rule, not listed above, where Boolean Algebra differs greatly from other forms of algebra. That is how it deals with the negation, or inverse, of an entire statement. For this, we refer to the work of Augustus De Morgan, pictured above. De Morgan was expanding upon the work of George Boole, and published some additional laws for Boolean Algebra, which we collectively refer to as De Morgan's Laws. 

In Algebra, when we negate an entire statement, we must change the signs of each number in the statement. Consider the example below:

{{< math >}}$$ -(x + y) \iff -x + -y $${{< /math >}}

However, in Boolean Algebra, the same rules does not quite work:

{{< math >}}$$ \neg(x \land y) \neq (\neg x) \land (\neg y) $${{< /math >}}

For example, if we assign the value `True` to {{< math >}}$ x ${{< /math >}} and `False` to {{< math >}}$ y ${{< /math >}}, we would be able to reduce the expression in this way:

{{< math >}}$$ \neg(x \land y) \neq (\neg x) \land (\neg y) $${{< /math >}}
{{< math >}}$$ \neg(T \land F) \neq (\neg T) \land (\neg F) $${{< /math >}}
{{< math >}}$$ \neg(F) \neq F \land T $${{< /math >}}
{{< math >}}$$ T \neq F $${{< /math >}}

As we can see, the two statements are not equal. Instead, De Morgan's Laws tell us that we must also invert the operation, changing {{< math >}}$ \land ${{< /math >}} to {{< math >}}$ \lor ${{< /math >}} and vice-versa. Let's look at a corrected version of the above example:

{{< math >}}$$ \neg(x \land y) \iff (\neg x) \lor (\neg y) $${{< /math >}}
{{< math >}}$$ \neg(T \land F) \iff (\neg T) \lor (\neg F) $${{< /math >}}
{{< math >}}$$ \neg(F) \iff (F) \lor (T) $${{< /math >}}
{{< math >}}$$ T \iff T $${{< /math >}}

So, we must add the following two laws to our table above:

| Name | Example |
|:----:|:-------:|
| De Morgan's Law {{< math >}}$ \land ${{< /math >}} | {{< math >}}$ \neg(x \land y) \iff (\neg x) \lor (\neg y) ${{< /math >}} |
| De Morgan's Law {{< math >}}$ \lor ${{< /math >}}  | {{< math >}}$ \neg(x \lor y) \iff (\neg x) \land (\neg y) ${{< /math >}} |

That gives us a full suite of laws we can use when working in Boolean algebra. 

{{% notice info "Daily Use of DeMorgan's Law" %}}

We use DeMorgan's all the time.  When we say x is between 1 and 10, we mean `(x ≥ 1  AND x ≤ 10) OR NOT (x < 1 OR x >10) `.  DeMorgan's law provides the mathematical proof of this.

{{% /notice %}}