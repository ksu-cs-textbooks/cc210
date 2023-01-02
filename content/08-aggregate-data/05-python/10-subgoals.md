---
title: "List Subgoals"
pre: "10. "
weight: 100
---

Working with lists in Python can also be quite complex. Thankfully, we can break each step down into subgoals to make it more manageable. 

## Evaluating Lists

Here are the subgoals we can use to evaluate statements with lists:

### 1. Set up List from 0 to Size - 1

This may be a bit confusing at first, but it will really help us understand lists. Anytime we are tracing code and see a new list defined, we need to set up a list in our variables to store those values. That list will have indexes ranging from 0 to one less than the size of the list. So, if the list has size 5, then we'll need to make a list variable with 5 boxes, and then label them from 0 to 4. We'll use that to keep track of the values in each element of the list.

### 2. Compare Data Type of Statements using List

Next, we'll need to compare the data types of any statements using the list. This links back to the earlier subgoals we learned for evaluating expressions. However, in Python, we can actually store any data type in a list, and each element in a list can have a different data type if we desired. While we won't be doing that in this course, it is still very important to make sure we understand the data types involved in each statement in our code. 

### 3. Trace Statements & Update Slots

Finally, we can trace through the code one line at a time, and update the values of each element in the list as we go. Once again, we'll need to rely on earlier subgoals to evaluate each expression, conditional construct, and loop that uses the list. 

In addition, anytime we see methods such as `append` that change the number of elements in the list, we'll need to update the number of boxes we're using to keep track of the values in the list. 

## Writing Lists

We can also use a few subgoals to help us create new lists

### 1. Initialize with `[Initializer List]` or `[]`

We can create a list in one of two ways. If we already know what values we want to store in the list, we can use a list of comma separated values inside of square braces, as in this example:

```python
a = [1, 2, 3, 4, 5]
```

Alternatively, if we don't know the individual elements we can create an empty list using this syntax:

```python
a = []
```

Then we can use methods such as `append` to add new elements to the end of the list.

That's it! Once we've initialized the list, we can treat each element in the list as an individual variable and use the subgoals for evaluating expressions to handle assigning and using values stored in the list. 