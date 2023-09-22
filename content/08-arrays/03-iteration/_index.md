---
title: "Iteration"
pre: "3. "
weight: 30
---

{{% youtube 11R9oFjc008 %}}

[Video Materials]({{<relref "./video">}})

Of course, once we've created an array of data, we need some way to access its elements easily in our code. Thankfully, we can use the loop structures we've learned in a previous chapter to _iterate_ across our arrays. _Iteration_ is the term we use to describe accessing each element in the array and possibly performing some repeated action using that element. 

For example, consider the flowchart below, showing a simple program that uses loops and arrays:

![Array Iteration Flowchart](/images/08-array/6.3.iteratearray.png)

This program begins by accepting a single input from the user, stored in the variable `x`. That input is used to determine the size of an array, denoted by the `array(x)` block. Each programming language has its own way of creating an array, but we'll use this simplified form in these flowcharts. 

Next, the program reaches a **For** loop which uses `i` as its iterator variable. That variable will include all values from 0 up to, but not including, the value stored in `x`. Notice that there is a parenthesis to the right of `x`, showing that it is not included in the sequence denoted by `[0, x)`. 

Inside of that loop, we receive another input from the user, stored in the variable `y`. Then, we store that value into the array, using our iterator variable `i` as the index in the array. So, the first input we receive and store in `y` will be stored in `a[0]`, the first element of the array. In most programming languages, we use square brackets `[]` after an array variable to denote a specific element in the array, with the index of that element shown inside of the square brackets. When the loop repeats, the next value will be stored in `a[1]`, and so on, until the array contains `x` values.

Once the first **For** loop terminates, we create a new variable named `sum` and set it initially equal to 0. We'll use this variable to add up all of the numbers in the array in the next **For** loop. However, that loop is defined a bit differently. In the flowchart we see that the loop is defined as `j : a`, which means that we are using `j` as our iterator variable, but instead of getting values from a mathematical sequence such as `[0, x)` from the first loop, we are taking the items directly from our array, `a`, instead. These special **For** loops are sometimes known as **For Each** loops or **Enhanced For** loops, depending on the language. In essence, they repeat the loop one time _for each_ element in the array given. So, we'd say "for each `j` stored in `a`, add `j` to `sum`" to describe this loop. 

The first time we run the code inside of that loop, the variable `j` will be storing the _value_ of the some element in array `a`. So, we could say that `j` has the same value as `a[0]`. We'll add that value to the `sum` variable, then repeat the loop. In the next iteration, the variable `j` will then store a different value in `a`, or `a[1]`. We'll continue to repeat the loop until each element in `a` has been used--the loop ensures we have seen all the elements exactly once.

At the end, when we output the `sum` variable, it should be the sum of all of the elements in the array. 

Of course, we can easily rewrite these loops as **While** loops instead, or we could use the standard form of the **For** loop as the second loop, using the iterator variable to refer to the index of the element inside of the array instead of the element itself. 

{{% notice info "While, For, and For Each" %}}

As a general rule:
1. Use a **While** loop when the decision to "loop again" depends on the calculations and logic of the loop body.  
1. Use a **For** loop when the number of loops you are going to make is fixed.
1. Use a **For-Each** loop when <u>all</u> the following are true:
    1. the language supports it;
    1. you do not care what order the data is looped through;
    1. you want to ensure every element of the aggregated variable is examined;
    1. you <b>do not change any data </b> in the aggregate variable (look but don't touch).

Consider taking one egg at a time out of full egg carton.
1. If you were going to crack eggs until you had at least one cup of egg-goop, that is a while loop.
2. If you are going take 3-eggs for an omelet (a fixed number of eggs), that is a for loop.
3. If you are going to swap the eggs around in the carton, or maybe draw faces on them, that is also a for loop (there are a dozen eggs).  Here you are changing the "elements" in the carton.
4. If you are going to weigh each egg, then put it back where it came from--that is a for-each loop,

{{% /notice %}}

