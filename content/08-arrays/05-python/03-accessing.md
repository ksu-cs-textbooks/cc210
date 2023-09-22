---
title: "Accessing List Elements"
pre: "3. "
weight: 30
---

Once we've created our list, we can access individual list elements by placing the _index_ of that element inside of the _square brackets_ `[]` following the variable name.  You may see `[]` referred to as the indexing or slicing operator.

List indexes in Python start at 0. So, to access the first element of an list named `x`, we would use `x[0]`.

Similarly, the last list index is one less than the total size of the list. If the list named `x` has a size of 5, then the last element would be `x[4]`.

In Python, we can also access the last element using a negative index, as in `x[-1]`, which will work regardless of the list's size.

To add an item to the end of a list, we can use the `append` method. For example, to add the number `5` to the end of a list named `x`, we would use `x.append(5)`. This will change the size of `x` as well. 

Let's take a look at an example in the code below. It will create an empty list, add 5 integers to that list, then sum them up and print the result.

```python
#create an integer array
a = []

#assign array elements
a.append(5)
a.append(10)
a.append(15)
a.append(20)
a.append(25)

#create a sum variable
sum = 0

#add up all the elements in the array
sum = sum + a[0]
sum = sum + a[1]
sum = sum + a[2]
sum = sum + a[3]
sum = sum + a[4]

#print the sum (it should be 75)
print(sum)
```

Feel free to copy this code to `Scratch.py` and modify the code to try other operations with lists.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}
