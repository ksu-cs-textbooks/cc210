---
title: "Java Chaining & Nesting"
pre: "2.J. "
weight: 20
date: 2019-02-07T10:53:26-05:00
hidden: true
---

{{< youtube -W3FohcKLvI >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

One of the most powerful features of the conditional statements we've covered in this chapter is the ability to chain them together or nest them within one another to achieve more complex program structures. Let's walk through a couple of examples to see how we can go from a program structure to the appropriate code in Java.

The program we are writing is fairly simple. Given an integer as input, our program should output -1 if it is negative, 0 if it is exactly equal to 0, or 1 if it is a positive number.

One possible flowchart for this program is shown here. In effect, we have three separate conditional statements to test the three conditions of this program, and we produce the appropriate output within each one.

Let's see what this would look like in Java.

First, we'll need to create our class declaration and method declaration. I've omitted the class declaration here, but we'll use the standard main method declaration to contain this code.

Next, we'll need to accept input from the user. For now, we'll just hard-code this input into our program. We'll learn how to handle user input later in this chapter.

Now we have reached the first conditional statement. This decision node in the flowchart checks to see if the input is less than 0. So, to create this same structure in code, we'll use an **If-Then** statement, as seen here in code.

On the true branch, we should output -1, so we'll put that print statement inside the curly braces that mark the body of the **If-Then** statement.

Next, we'll do pretty much the same thing for the other two conditional statements. First we have the statement that handles the case where the input is exactly equal to 0.

Then we can include the conditional statement for the case where x is positive, including the appropriate output.

There we go. This code in Java represents the program that matches the flowchart shown to the left. It's a pretty simple program, but it works very well.

Let's look at another approach to this program. Here we see a flowchart that is not quite as linear. So, what would that look like in code?

As before, we'll start with our main method declaration and setting the value of `x` to some value.

Next, we'll reach the first decision node, once again checking to see if `x` is less than 0. In this case, however, we'll be using an **If-Then-Else** statement, since the False branch contains its own code.

In the True branch, once again we'll simply print "-1" to the screen.

On the False branch, we notice that we reach another decision node. So, in this case, we'll place another **If-Then-Else** statement _inside_ of the False branch of the first statement, like so.

In this statement, if the condition `x == 0` is True, we'll output 0. If it is false, we can assume that x must be positive, so we can just output 1 without an additional conditional statement.

Is there another way to do this? As it turns out, we can. Since the False branch of the outermost **If-Then-Else** statement contains another conditional statement, we can remove one layer of the curly braces, making the structure resemble an **If-Else-If** statement, like so.

Finally, in the text on this page, we discuss why you might want to include another conditional statement here in some cases. I encourage you to check that out and make sure you understand why that statement might be important to include.
