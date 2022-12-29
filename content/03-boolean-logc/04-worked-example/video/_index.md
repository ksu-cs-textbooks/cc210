---
title: "A Worked Example"
pre: "4. "
weight: 40
date: 2019-02-07T10:53:26-05:00
hidden: true
---

{{< youtube AwXThNJOSEo >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

Let's work through an example problem to see in depth how we take a real world problem statement and translate it into a Boolean logic expression that we can use in our programs.

Here's our problem statement: A program should turn the lights on if the light switch in the room is in the "ON" position. Similarly, it should turn on the lights if it detects there are people in the room using a motion sensor, regardless of whether the light switch is "ON" or "OFF". However, it should respect a master switch, such that if the master switch is off, the lights can not be turned on at all.

So, how can we translate this into a Boolean logic statement. First, we can try to make a truth table to help understand our inputs and outputs. Looking at our problem statement, we can identify three inputs: the light switch, a motion sensor, and a master switch. We also have a single output, which is whether the light is on or not.

Also, we know that the light can only be on when the master switch is turned on, and if either the light switch is on or the motion sensor detects motion. So, we can fill out the appropriate entries in the output column. As we can see here, there are three cases where we should make sure the light is on.

Now that we have our truth table, how can we convert that information to a Boolean logic statement? There are two approaches we can follow. First, we can use our truth table to build Venn diagrams. So, let's look at that.

First, we can fill in the parts of the Venn diagram for each line in the truth table where the output is true. So, if the Master Switch is C, we would shade in this part to show that the light should be on when the motion sensor and the master switch are true and the light switch is false.

Similarly, we'd shade this portion for when the master switch and light switch are on, but the motion detector is not sensing any motion.

Finally, we also must fill in this center section for when all three are true.

So, these three sections correspond to the three lines in the truth table where the output is true. Now, how can we take this Venn diagram and create a Boolean logic expression from it?

One of the easiest ways to do this is to figure out what simple parts of the diagram can be combined together to achieve the desired result. So, for example, we could start with this section, which represents A and C.

We can also highlight this potion, which represents B and C.

If we combine them together somehow, we can get the part we want. What symbol should we use to combine then? Well, we want the shaded part to include parts that are in each side, as well as the part that is in both. So, we'd use the Or operation. Therefor, the overall statement is (A and C) or (B and C).

If we replace those variables with the original sources, we get the statement (light switch and master switch) or (motion sensor and master switch). That statement nearly exactly matches the original problem statement. So, we've solved it!

Now, there's another way to go about this as well. Let's go back to the original truth table. Here, we can see the three lines that are true highlighted. If we look at just those three lines, we can easily come up with the Boolean expression that represents each line.

If we combine all of those statements together using the OR operation, we get this second Boolean expression. In actuality, this Boolean expression does exactly express the result we want. However, it is quite long and hard to understand, and we probably don't want to write this in our program. Thankfully, we can use the rules of Boolean algebra to simplify it.

First, we can use the law of idempotence to duplicate one of the terms. In effect, if we know that A is true, then we also know that A or A is true. So, we can do this to get a new statement.

Next, we can use the commutative property a couple of times to rearrange terms. First, we'll move our new term up a bit, then we'll rearrange terms inside of a couple of the later terms as well. This will make the next step easier.

In addition, we'll use the associative property to add a few extra parentheses to help better see the structure of the expression.

Next, we see that the first two terms have a repeated portion. So, we can use the inverse of the distributive property to pull that portion out, leaving B and C and NOT A or A as the first two terms.

We can also do the same to the second two terms, factoring out (A and C).

Next, we notice that each set of terms ends with a term like these - Not A or A, and Not B or B. Using the complement law, we know that these can reduce to True, since either value of the variable would result in True.

Similarly, we see that each set or terms ends with AND True. Using the law of identity, we can simply remove those terms, since they are not needed.

So, we are left with B and C or A and C, which is exactly the same result that we saw previously. Therefore, we can use either approach to find the answer.

Finally, we can continue to simplify this expression one more level, using the inverse of the distributive property to factor out the (master switch) variable in each term. So, we can also show that the result master switch and (light switch or motion sensor) would also produce the same result.
