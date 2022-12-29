---
title: "The Laws of Thought"
pre: "1. "
weight: 10
---

{{% youtube TdYV9-Vdzuc %}}

[Video Materials]({{<relref "./video">}})

In this chapter, we're going to step away from computer programming for a bit to discuss a more foundational topic: logic. Logic and reasoning are core concepts at the heart of any level of education, and they are one of the major ways we are able to understand the world around us. Without logic and reasoning, we cannot build upon information we learn to create deeper meaning. Instead, all we are left with are facts, without any knowledge or wisdom gained from them. 

## Aristotelian Logic

![Aristotle](/images/03-bool/3.1.aristotle.wikimedia.jpg)[^1]

[^1]: File:Aristotle Altemps Inv8575.jpg. (2018, November 23). Wikimedia Commons, the free media repository. Retrieved 20:49, January 9, 2019 from https://commons.wikimedia.org/w/index.php?title=File:Aristotle_Altemps_Inv8575.jpg&oldid=328967130.

The earliest approach to formal logic comes from the work of Aristotle, seen above. His work established rules by which further information could be _inferred_, or _deduced_, from a set of truths about the world known as _premises_. 

For example, in Aristotelian logic, we might find the following premises to be true:

> Socrates is a man
> All men are mortal

Using Aristotle's rules for logic, we can infer from those premises the following _conclusion_:

> Socrates is mortal

This becomes a powerful system for inferring additional information based on facts in the world. By supporting each conclusion with premises and rules, it is possible to build a great wealth of knowledge. 

## Boolean Logic

![George Boole](/images/03-bool/3.1.boole.wikimedia.jpg)[^2]

[^2]: File:George Boole color.jpg. (2018, November 19). Wikimedia Commons, the free media repository. Retrieved 21:02, January 9, 2019 from https://commons.wikimedia.org/w/index.php?title=File:George_Boole_color.jpg&oldid=328260467.

In the 1800s, there was a great interest in using the rules of mathematics to understand the world as well. Mathematics contains a well understood set of rules and operations, and many thinkers hoped to find a way to apply those rules in the world of logic as well. By doing so, they could move away from using an imprecise spoken language to reason about the world, and instead use the very precise language of mathematics. 

In 1854, George Boole, seen above, published _[An Investigation of the Laws of Thought on Which are Founded the Mathematical Theories of Logic and Probabilities](https://www.gutenberg.org/files/15114/15114-pdf.pdf)_, a book which described exactly how to combine mathematics and logic into a single system. Using the system he proposed, it became very easy to use mathematical expressions and rules to perform the same logical inferences that Aristotle first used nearly 2000 years prior.

In Boolean logic, we may understand the following premises to be true:

{{< math >}}$$  A \land B $${{< /math >}}
{{< math >}}$$  B \land C $${{< /math >}}

In this instance, the {{< math >}}$ \land ${{< /math >}} symbol is used to denote the word "and". We'll learn more about these symbols later in this chapter. Using a rule from Boolean logic, we can reach the following conclusion:

{{< math >}}$$  A \land C $${{< /math >}}

If we compare the example from Aristotelian logic above to this example from Boolean logic, we can quickly see that they are very similar in structure. The first premise establishes a relationship between two items. The second premise establishes another relationship between the second item in the first premise, and a third item. The conclusion states that there must be a relationship between the first and third items. This is very similar to the _transitive_ property of some mathematical operators.^[This is not a perfect translation from Aristotelian logic to Boolean logic, but it fits well within the scope of this textbook. A more appropriate translation would use implication ({{< math >}}$ \implies ${{< /math >}}), but we won't be using that concept, so it has been substituted with "and" instead.] 

In programming, we use Boolean logic to control many aspects of how our computer programs function. In this chapter, we'll learn all about how Boolean logic works so we can apply it correctly in our programs. 
















