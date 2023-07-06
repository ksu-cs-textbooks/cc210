---
title: "Subgoals Review"
pre: "3. "
weight: 30
---

Working with Boolean expressions in Java is the same as working with any other type of expression. So, we can use the same subgoals we learned in a previous chapter to help us evaluate and write new Boolean logic expressions. Here's a quick review of those subgoals.

## Analyzing Expressions

To analyze an expression involving variables and mathematical operators in code, here are some mental subgoals we can use:

### 1. Check Types

First, we must determine whether the data type of the expression is compatible with the data type of the variable we want to store it in. In Java, we must be very careful to make sure we are only storing whole numbers in the integer data type, and floating point values in the double data type. 

### 2. Perform Prefix Operations

Next, we should look at the expression to determine if there are any prefixed operations that must occur first. In Java, for example, we could find a prefixed increment operator like `++x`, so we'll need to update the value of `x` before moving to the next step.

### 3. Solve Arithmetic Equation

At this point, we can solve the arithmetic equation using the order of operations for our language. This simply involves the process of substituting values for variables and performing the requested operations. However, once again we must be careful to make sure that the operands provided to each operator are valid and produce the correct data type. The example we saw earlier for handling a large equation showed us a great way to work through this process. 

### 4. Confirm Data Type of Result & Store It

Once we've solved the arithmetic equation, we should be left with a variable on the left side of the equals sign and a single value on the right side. So, once again, we should confirm that the value on the right can be stored in the data type of the variable on the left. 

### 5. Perform Postfix Operations

Finally, if the original expression included any postfix operations, such as a postfixed decrement like `x--` in Java, we'll need to update the value of `x` before moving on to the next line. 

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

Let's look at an example to see how we can use these steps to create an evaluate a Boolean expression to match a problem statement.

Consider the following problem statement:

> Create a program to determine if a user has exactly 5 apples, or fewer oranges than bananas. If so, the program should output `true`, otherwise it should output `false`. For this program, assume the user has 4 apples, 6 oranges, and 8 bananas. 

Let's go through the subgoal steps above to write this program. 

1. First, we can read the problem statement to see that we should have at least three variables - one for apples, oranges, and bananas. In addition, we may need a fourth variable to store the Boolean result that we'd like to output. 

2. The second subgoal is pretty straightforward. We can easily create three integer variables, `apples`, `oranges`, and `bananas` for each type of fruit, and a Boolean variable `result` to store the result of our Boolean logic expression.

3. Next, we'll need to build our arithmetic equation. For this program, we need to determine if the user has exactly 5 apples, or `apples == 5`. We also need to know if the user has fewer oranges than bananas, or `oranges < bananas`. Finally, we can put those together using the **or** operator as indicated in the problem statement, so the final equation would be `(apples == 5) || (oranges < bananas)`. 

4. Now we can build our program itself. Here's one possible solution:

```java
int apples = 4;
int oranges = 6;
int bananas = 8;

boolean result = (apples == 5) || (oranges < bananas);

System.out.println(result);
```

5. Finally, we can verify that the operators and operands are compatible. Specifically, on either side of the **or** operator `||`, we see that each side is a smaller expression that will result in a Boolean value, so the data type of each operand will be correct. 

Using subgoals makes it very easy to work through this process, one step at a time.