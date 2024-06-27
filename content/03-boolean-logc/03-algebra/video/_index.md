---
title: "De Morgan's Laws"
pre: "3. "
weight: 30
date: 2019-02-07T10:53:26-05:00
hidden: true
---

{{< youtube chH10DQfbOc >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

One of the biggest missing things in the original version of Boolean logic is how to handle the application of the Not operator to a larger statement. The solution to that problem was added by Augustus De Morgan, who was using George Boole's new format for formal logic to express rules already present in older forms of logic.

Specifically, these rules deal with how to handle a situation such as this, where the NOT operator has been applied to a larger expression in Boolean algebra. How can we handle this?

Let's go back to the truth table and see if we can figure it out. So, we know from earlier that the truth table for A AND B looks like this. So, if we want to find the truth table for NOT A AND B, we'd just invert those values. Notice that this column on the right includes three True values and one False value. That gives us a clue about how to solve this. Can you remember which other Boolean operator results in three True values and one False value?

That would be the OR operation. If we look closely, we notice that the rightmost column is true if either A or B are false, or if both of them are false. So, we can guess that NOT A AND B is roughly the same as NOT A OR NOT B

That's exactly what De Morgan's law is about. According to De Morgan's Laws, the inverse of A AND B is NOT A OR NOT B. In fact, the same process works for the inverse of A OR B as well.

So, in summary, De Morgan's law states that whenever we want to find the inverse of a Boolean logic expression, we first distribute the not symbol to all parts inside of the expression, then we invert the ANDS and ORS. That's all there is to it!

Being able to understand these complex Boolean logic expressions is a really handy skill in computer programming. Make sure you take a minute to fully understand these rules!