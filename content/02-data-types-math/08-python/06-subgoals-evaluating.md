---
title: "Subgoals - Evaluating Expressions"
pre: "6. "
weight: 60
---

One of the unique parts of this course will be the inclusion of subgoals to help us better understand what is going on in our code. Subgoals are designed to help us structure our thinking process in a way that matches what an experienced developer might have.

A great example is learning how to read. Fluent readers can read whole words at a time, while processing and retaining information from several sentences at once. Novice readers have to sound out words one letter at a time, and can store and retain a few words at a time in memory before being overwhelmed by information. Learning a new language can quickly make this difference very apparent, even for readers who are fluent in many languages.

Writing computer code is very similar. An experienced developer can fluently read and write code, seeing and understanding entire code structures at a glance. Novice developers often have to look at a single line at a time, and break it down into individual parts before it is apparent what the code says. That's just part of the learning process!

To make this process easier, this course will include many pages that describe subgoals we can use to help analyze and write code. In essence, we can treat these subgoals as a set of steps to follow mentally when performing these tasks. Over time, we'll become more comfortable with each task, and the subgoals will quickly become ingrained knowledge. Just like we can easily read both "cat" and "catastrophe" at a glance, with practice we'll be able to read code just as quickly!

{{% notice info "More Information" %}}

For more information on Subgoals, see the work of Dr. Briana Morrison published through the ACM and elsewhere. [Link](https://dl.acm.org/author_page.cfm?id=81100422884)

{{% /notice %}}

## Analyzing Expressions

To analyze an expression involving variables and mathematical operators in code, here are some mental subgoals we can use:

### 1. Check Types

First, we must determine whether the data type of the expression is compatible with the data type of the variable we want to store it in. In Python, we can generally store any value in any variable, since the interpreter will change the type of the variable as needed behind the scenes.  

### 2. Solve Arithmetic Equation

At this point, we can solve the arithmetic equation using the order of operations for our language. This simply involves the process of substituting values for variables and performing the requested operations. However, once again we must be careful to make sure that the operands provided to each operator are valid and produce the desired data type. The example we saw earlier for handling a large equation showed us a great way to work through this process. 

### 3. Confirm Data Type of Result & Store It

Once we've solved the arithmetic equation, we should be left with a variable on the left side of the equals sign and a single value on the right side. So, once again, we should confirm that the value on the right can be stored in the data type of the variable on the left. 

## Examples

Let's walk through an example showing how to use these subgoals to evaluate a few expression statements.

```python
x = 3 + 5
```

We'll break this down by subgoals:

1. We see that the values on the right side of the equation are integers, which can definitely be added together. So, this expression will store an integer value in `x`. 
3. We can now solve the arithmetic equation on the right side of the expression. So, we can easily find that `3 + 5` can be replaced with `8`. 
4. This tells us to once again confirm that the result is a compatible value for the data type of the variable on the left. Since `8` can be stored in any variable, we are just fine. So, we can update the value of `x` to `8`. 

That's all there is to it! While this may seem like quite a bit of information for handling a simple statement, it becomes much more useful as the statements get more complex.

Here's a second example:

```python
x = 5
y = 3.5
z = x + -y
```

Once again, let's break the last line in this code example down by subgoals to evaluate the expression:

1. This is a bit tricky, since the statement includes several variables. However, we can look at the earlier code to see that `x` is an integer type, and `y` is a floating point type. Since this expression is adding them together, the result should be a floating point number, which can be stored back in the variable `z`. So, we should be fine here.
3. Now we can solve the equations. To do this, we'll replace each variable with its value, then calculate the result. So, `x + -y` becomes `5 + -3.5` which results in `1.5`.
4. Once we have the result, we must confirm that it can be stored in the variable to the left. Since `1.5` is a floating point number, it can be stored in the variable `z` without any problems. So, we'll update the value of `z` to {{< math >}}$ 1.5 ${{< /math >}}.

So, at the end of this short code example, we'll see that `x` is {{< math >}}$ 5 ${{< /math >}}, `y` is {{< math >}}$ 3.5 ${{< /math >}}, and `z` is {{< math >}}$ 1.5 ${{< /math >}}. 

Finally, let's look at one more example:

```python
x = 5
y = 8.5
3 = z
```

Here's how we can break down the process of evaluating the last line in this example:

1. Looking at the last line, we see that there is the value `3` on the left side of the equals sign `=`. This is not allowed in Python, so the Python interpreter will give us an error when we try to execute this code. So, we can stop here.

As we can see, by carefully following these subgoals, we can even find errors in our code, just by evaluating it step by step. 