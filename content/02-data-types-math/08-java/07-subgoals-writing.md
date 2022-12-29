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

Once we've found a variable to work with, we must also determine the variable's name and data type. Once again, this may be obviously found in the problem statement, but other times we must think a bit more about what type of data will be stored in the variable. If we are working with an existing variable, we'll need to make sure that the data type of that variable is compatible with the type of data we'd like to store in it. Of course, we should also make sure the variable has a descriptive and memorable name if we are creating a new one. 

### 3. Build Arithmetic Equation with Operators

Now that we've isolated our variable, we must build an arithmetic equation and operators required to produce the desired value. This may involve using additional variables in our equations as well. 

### 4. Build Expression

Once we have our arithmetic equation, we can then build the overall expression. This usually consists of three parts: the variable on the left, an assignment operator in the middle, and the arithmetic equation on the right. 

### 5. Make sure Operators and Operands are Compatible

Finally, once we've constructed the overall expression, we should check and make sure that all operators and operands are compatible. This means making sure that we aren't trying to assign a floating point value to an integer, or dividing two integers and expecting a floating point number as a result. 

## Example

Here's a quick example to show how this process works. Consider the following problem statement:

> Given two whole numbers, find the remainder of dividing the first number by the second number. 

Let's use the subgoals listed above to build an expression for this problem statement

1. First, we must identify our variables. Looking at this problem statement, we see that it expects us to be given two whole numbers. So, we'll probably need two integer variables to represent those two numbers. Then, we'll need a third variable to store the remainder. In total, we can easily identify three variables that we'll need to create for this program. 
2. Next, we must determine the name and type of each of these variables. To make it very clear, I'm going to label the two input variables `inputA` and `inputB`, and the remainder variable `remainder`. We can also determine that each of them should be the `int` type, since we are only dealing with whole numbers. So, our code might begin with these three variable declarations:

```java
int inputA;
int inputB;
int remainder;
```

3. Now we can assemble our arithmetic equation. We need to calculate the remainder of dividing `inputA` by `inputB`, so we can use the modulo operation `%` to find this value. So, our arithmetic equation could be `inputA % inputB`.
4. Then, we can build the overall expression itself. Since we want to store the result of the arithmetic equation in `remainder`, we'll build the line `remainder = inputA % inputB` as our entire expression. So, we can add that to our code:

```java
int inputA;
int inputB;
int remainder;
remainder = inputA % inputB;
```

5. Finally, we must make sure our operators and operands are all compatible. Since we know that both `inputA` and `inputB` are integers, the result of the modulo operation would also be an integer. So, this line is valid.

Of course, the part we are missing is the values for `inputA` and `inputB`. At this point, we haven't covered how to accept user input yet, so we can assume that those values are hard-coded into the program. So, our final program might look something like this:

```java
int inputA;
int inputB;
int remainder;

inputA = 5;
inputB = 8;
remainder = inputA % inputB;
```

Using these subgoals is a very great way to learn how to build programs one step at a time. As we learn more about programming and get more experience, many of these steps will become automatic. This is very similar to how we write sentences by hand. We typically don't think about each letter as we write it once we are fluent with the language, but instead we think of entire words and our brain is able to send the correct commands to produce the desired output. With time and practice, writing code will be very similar.