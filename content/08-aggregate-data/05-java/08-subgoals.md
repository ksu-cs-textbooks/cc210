---
title: "Array Subgoals"
pre: "8. "
weight: 80
---

Working with arrays in Java can also be quite complex. Thankfully, we can break each step down into subgoals to make it more manageable. 

## Evaluating Arrays

Here are the subgoals we can use to evaluate statements with arrays:

### 1. Set up Array from 0 to Size - 1

This may be a bit confusing at first, but it will really help us understand arrays. Anytime we are tracing code and see a new array defined, we need to set up an array in our list of variables to store those values. That array will have indexes ranging from 0 to one less than the size of the array. So, if the array has size 5, then we'll need to make an array variable with 5 boxes, and then label them from 0 to 4. We'll use that to keep track of the values in each element of the array.

### 2. Compare Data Type of Statements using Array

Next, we'll need to compare the data types of any statements using the array. This links back to the earlier subgoals we learned for evaluating expressions. For example, if the array's data type is `int[]`, we must make sure that each element is treated as an `int` variable. 

### 3. Trace Statements & Update Slots

Finally, we can trace through the code one line at a time, and update the values of each element in the array as we go. Once again, we'll need to rely on earlier subgoals to evaluate each expression, conditional construct, and loop that uses the array. 

## Writing Arrays

We can also use a few subgoals to help us create new arrays

### 1. Data Type Plus `[]`

To create a new array, we simply determine the data type of each element in the array, and then add square brackets after the data type to create the array data type. So, for an array of `double` values, we'd declare a variable with type `double[]`.

### 2. Initialize with `{Initializer List}` or `new datatype[size]`

Next, we can initialize the array in one of two ways. If we already know what values we want to store in the array, we can use a list of comma separated values inside of curly braces, as in this example:

```java
int[] a = {1, 2, 3, 4, 5};
```

Alternatively, if we don't know the individual elements but we do know the expected size, we can create an empty array of a particular size using this syntax:

```java
int[] a = new int[5];
```

That's it! Once we've initialized the array, we can treat each element in the array as an individual variable and use the subgoals for evaluating expressions to handle assigning and using values stored in the array. 