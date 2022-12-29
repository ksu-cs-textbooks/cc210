---
title: "Variables"
pre: "1. "
weight: 10
hidden: true
date: 2019-02-05T10:53:26-05:00
---

{{< youtube nk4XkiGKick >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

Variables can be one of the trickier concepts in programming to get used to. Let's review some quick information about variables to help us develop our programs.

You've probably already seen variables in mathematics, such as in this equation. Here, the variable `x` stands for an _unknown_ value, or one that we'd like to solve for. The important thing to know is that `x` is a placeholder for a value, and we can always replace `x` with its value and get the same result.

Variables in programming are similar, but they have one important difference: we always know what value they store. Or, stated differently, the value of our variables should never be unknown.

In effect, we can think of variables in programming just like a cardboard box. When we create a variable, we are creating a new box to store something, and we give it a name, such as `height`. Then, we can store a value in that box, like `42`. Finally, anytime we want to use that value, we can just use the name of the variable to retrieve that value from the box and use it in our code. We can even update the value stored in the box to a new value at any time.

Let's look at an example. Here's some source code similar to Python that deals with variables. In this code, we have created three variables, `x`, `y`, and `z`. Let's step through this code one line at a time, just like a computer would do when it executes this code, and see how the values of our variables change.

First, we create the variable `x`, and store the value 5 in that variable.

Then, we create the value `y`, and store the current value of `x + 3` in that variable. So, now we know the variable `x` still stores 5, but `y` now stores the value 8. Notice that the value stored in `y` does not reference the value stored in `x` at all. This is because we _access_ the value in `x` anytime we use it, but the value in `y` isn't affected by any changes to the value in `x`.

In fact, the next line clearly demonstrates this fact. This line adds the value 1 to the current value stored in `x`. So, we access the current value in `x`, which is 5, add 1 to it to get 6, then store that value back in the box for variable `x`.

Following that, we create a third variable, `z`. Can you figure out what value should be stored in `z`?

Looking at the code, we see that `z` is the sum of the current values of `x` and `y`. So, we'd access 6 and 8 and add them together, resulting in 14 stored in `z`.

Finally, the last line updates the value of `y` to the sum of `y` and `z`. So, we'd access the value 8 stored in `y` and 14 stored in `z`, then add them together to get 22 before storing that value back in `y`.

So, the important things to remember about variables in a programming language: we can always determine their current value, and anytime we access the variable we just use the currently stored value at that time.

I hope this helps you understand variables a bit better. The rest of this chapter deals quite a bit with variables and storing data, so you'll get plenty of practice working with them.
