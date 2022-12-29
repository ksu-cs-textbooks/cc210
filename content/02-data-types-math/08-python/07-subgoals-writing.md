---
title: "Subgoals - Writing Expressions"
pre: "7. "
weight: 70
---

We can also use subgoals to help us write new expressions in our code. These subgoals help us understand each part of the process of building a new expression, and they also help us avoid many common errors. 

## Writing Expressions

Here are the subgoals for writing a new expression:

### 1. Find Variable in Problem Statement

The first step is to determine which part of the problem statement will be represented by a variable. Sometimes this is obvious, and other times it is not. This may be a new variable that we are creating, or it could be an update to an existing variable. 

### 2. Determine Name and Data Type of Variable

Once we've found a variable to work with, we must also determine the variable's name and data type. Once again, this may be obviously found in the problem statement, but other times we must think a bit more about what type of data will be stored in the variable. Of course, we should also make sure the variable has a descriptive and memorable name if we are creating a new one. 

### 3. Build Arithmetic Equation with Operators

Now that we've isolated our variable, we must build an arithmetic equation and operators required to produce the desired value. This may involve using additional variables in our equations as well. 

### 4. Build Expression

Once we have our arithmetic equation, we can then build the overall expression. This usually consists of three parts: the variable on the left, an assignment operator in the middle, and the arithmetic equation on the right. 

### 5. Make sure Operators and Operands are Compatible

Finally, once we've constructed the overall expression, we should check and make sure that all operators and operands are compatible. This means making sure we are using the correct operators and conversions to produce the desired data type as output. 

## Example

Here's a quick example to show how this process works. Consider the following problem statement:

> Given two whole numbers as command line inputs, find the remainder of dividing the first number by the second number.  The command line would be `python3 Types.py 2 3`. 

Let's use the subgoals listed above to build an expression for this problem statement

1. First, we must identify our variables. Looking at this problem statement, we see that it expects us to be given two whole numbers. So, we'll probably need two integer variables to represent those two numbers. Then, we'll need a third variable to store the remainder. In total, we can easily identify three variables that we'll need to create for this program. 
2. Next, we must determine the name and type of each of these variables. To make it very clear, I'm going to label the two input variables `inputA` and `inputB`, and the remainder variable `remainder`. We can also determine that each of them should be integers, since we are only dealing with whole numbers. So, our code might begin with these three variable declarations:

```python
inputA = args[1]
inputB = args[2]
remainder = 0
```

3.  But `args` is a list of Strings so we need to convert inputs into integers.

```python
inputA = args[1]
inputB = args[2]
remainder = 0
intA = int(inputA)
intB = int(inputB)
```

4. Now we can assemble our arithmetic equation. We need to calculate the remainder of dividing `inputA` by `inputB`, so we can use the modulo operation `%` to find this value. So, our arithmetic equation could be `intA % intB`.
5. Then, we can build the overall expression itself. Since we want to store the result of the arithmetic equation in `remainder`, we'll build the line `remainder = intA % intB` as our entire expression. So, we can add that to our code:

```python
inputA = args[1]
inputB = args[2]
intA = int(inputA)
intB = int(inputB)
remainder = intA % intB
```

5. Finally, we must make sure our operators and operands are all compatible. Since we know that both `intA` and `intB` are integers, the result of the modulo operation would also be an integer. So, this line is valid.


Using these subgoals is a very great way to learn how to build programs one step at a time. As we learn more about programming and get more experience, many of these steps will become automatic. This is very similar to how we write sentences by hand. We typically don't think about each letter as we write it once we are fluent with the language, but instead we think of entire words and our brain is able to send the correct commands to produce the desired output. With time and practice, writing code will be very similar.