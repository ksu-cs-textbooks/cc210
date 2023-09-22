---
title: "Introduction"
pre: "1. "
weight: 10
---

So far, we've learned how to store many different types of data in **variables**. We can then use those variables in our programs to receive user input, store the results of calculations and so much more.

However, we have to individually declare and maintain each variable in our code. As we build larger programs, we'll have to deal with a commensurately large amount of variables, and it can be hard to keep track of all of them.

At the same time, we may also want to store many related items together. For example, if we are building a program to calculate student grades, we may want to be able to store each grade a student has received. With what we've learned so far, we might have to create variables named `assignment1`, `assignment2`, `assignment3`, and so on, to store this information. This can quickly become very difficult to manage, and it is difficult to write code that can perform calculations on those variables. Each time a new variable is added, every location in the code that references those variables would need to be changed.

Is there a better way to do it? **YES!**

Nearly every programming language supports special types which aggregate, or collect data in a single variable.  In languages which support objects, these types are instance classes which may have methods and attributes.


### Chapter References

- [Arrays in Java](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html)