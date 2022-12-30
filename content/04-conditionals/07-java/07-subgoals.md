---
title: "Subgoals"
pre: "7. "
weight: 70
---

Now that we've seen how to work with conditional constructs in Java, let's break down our thought process a bit into subgoals once again.

## Evaluating Conditional Constructs

Here are the subgoals we can use for evaluating conditional constructs:

### 1. Diagram Which Statements Go Together

First, when we see a conditional construct in code, we must determine which statements go together. Specifically, we need to know which statements are in the `true` branch, and which statements are in the `false` branch. This may seem pretty straightforward, but if the code contains many nested statements or poor formatting, it can be very difficult to do.

Here's a quick example:

```java
if(true){
  if(false){
    System.out.println("one");
  }
}else{
  System.out.println("two");
}
```

In this example, we see that there are three distinct branches. First, we have the `true` branch of the outermost **If-Else** statement, which includes the inner **If** statement. That statement itself has a `true` branch that will print `one` to the terminal. The outermost statement also has a `false` branch, which will print `two` to the terminal. 

### 2. Determine if Boolean Expression is `true` or `false`

Once we've identified our conditional construct, the next step is to determine if the Boolean expression inside of the `if` statement is `true` or `false`. Sometimes this step is simple, but other times it can be tricky. Thankfully, we can refer back to the subgoals we've already seen for evaluating expressions if we need a bit of help. 

### 3. Follow the Correct Branch

After we find the value of the Boolean expression, we can simply follow the `true` branch if the Boolean expression evaluated to `true`. If the Boolean expression evaluated to `false`, we can follow the `false` branch if it exists. If the conditional construct is an **If** statement, we can simply ignore the rest of the conditional construct and move on to the next part of the program.

## Writing Conditional Constructs

We can also use subgoals to help us write new conditional constructs. 

### 1. Define How Many Mutually Exclusive Paths are Needed

First, when building a new conditional construct, we must determine how many paths are needed. In effect, this will be one more than the number of conditional constructs we'll end up using in most cases. 

### 2. Order Paths from Most Restrictive/Selective to Least Restrictive

Next, we can reorder the paths from most restrictive to least restrictive. The most restrictive path would be the one that is least likely to occur, while the least restrictive path is the one that will be taken most often. We'll see how this works a bit more clearly in the example on the next page. 

### 3. Write `if` Statement with Boolean Expression

Once we have all of our paths identified and ordered, we can start writing our `if` statements for each path. Each `if` statement will need a Boolean expression to help us determine which branch to follow. Generally, we'll place the most restrictive paths inside of the less restrictive paths, but it all depends on the problem and what order makes the most sense. 

### 4. Write `true` Branch Code

Then, for each conditional construct, we must fill in the code on the inside of the `true` branch. This could be a block of code, or even another conditional construct. 

### 5. Write `false` Branch Code

Similarly, we must fill in the code on the inside of the `false` branch, if needed. This could be a block of code, or even another conditional construct. 

### 6. Repeat 3-5 For All Paths

Finally, once we've created a conditional construct, we may have to repeat these steps again and again for each path that we identified in subgoal 1. 

On the next page, we'll see how we can apply these subgoals in a worked example. 