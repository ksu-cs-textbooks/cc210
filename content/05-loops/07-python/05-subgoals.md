---
title: "Loop Subgoals"
pre: "5. "
weight: 50
---

Of course, we can identify some subgoals for working with loops in Python as well. Let's take a look at them and see how we can use them to help understand loops a little bit better.

## Evaluating Loops

Here are the subgoals for evaluating a loop in Python:

### 1. Identify Loop Parts

The first and most important part of evaluating a loop is to identify each part of the loop structure. Here is a list of things to look for:

1. **Start Condition** - variables that are initialized when the loop is first reached 
1. **Update Condition** - variables that are updated after each loop iteration 
1. **Loop (termination) Condition** - the Boolean expression that will terminate the loop when it becomes `False`
1. **Loop Body** - the lines of code which will be repeated on each loop iteration

Depending on which type of loop we are looking at, we may not find all of the parts listed above. 

### 2. Trace the Loop

Once we've identified all of the parts of the loop, we can then trace the loop to see how it updates values on each iteration. The easiest way to do this is to write down the values of each variable before the loop starts, and then update those values as the loop iterates. We've already seen a few examples for how to trace a loop in this chapter, and we'll do one more on the next page.

## Writing Loops

We can also use subgoals to help write loops. Here are the subgoals we'll use:

### 1. Determine Purpose of the Loop

Before writing a loop, we must decide what we're using it for. Once we know that, then we can determine which type of loop would be best. For example, if we are using the loop to repeat steps until a particular Boolean condition is `False`, we'll probably want to use a **While** loop. 

### 2. Define and Initialize Variables

Once we've determined which loop structure we're going to use, we'll need to define and initialize any variables needed by the loop. Specifically, we may want to define the initial value of our iterator variable to some value if we are using one.

### 3. Determine Termination Condition

Next, we'll need to determine the Boolean condition that should cause the loop to terminate. For example, we may want the loop to repeat until our iterator variable `i` becomes 5. So, we'll want to invert that Boolean statement to find the statement that can be used inside the loop to determine whether it should continue. 

Therefore, the termination condition `i == 5` should become the continuation condition `i < 5`. We could also use `i != 5`, but we could run into an issue where the value of `i` skips over 5 for some reason in our code, creating an infinite loop. By using `i < 5` instead, the loop will terminate as soon as `i` becomes 5 _or greater_, which is safer overall.

### 4. Write Loop Body

Once we've set up the loop itself, we can write the code we'd like repeated inside of the loop body. One thing we must be very careful about is making sure we are properly updating our loop's iteration variable toward the termination condition. If we forget to do that, we may run into a condition where the loop will not terminate at all, causing our programs to lock up. In a later chapter, we'll discuss concepts such as _loop invariants_ that will help us with this step. 