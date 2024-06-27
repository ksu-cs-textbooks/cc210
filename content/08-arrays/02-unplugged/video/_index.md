---
title: "Arrays Unplugged"
pre: "1. "
weight: 10
date: 2019-02-21T00:00:26-05:00
hidden: true
---

{{< youtube 9rzcp1hw_kg >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

So far, we've built programs that store data in single variables. That approach works for simple programs, but in the real world we are faced with large amounts of related data. Think about all of the tables, spreadsheets, and databases that power the world today. How can we use that data in our programs?

Most programming languages support a special type of variable called an array. Arrays allow us to store multiple items using a single variable name.

One good way to think about an array is a post office. We can refer to the whole post office using a single address, or variable name, so it is easy to find.

However, inside of the post office are a bunch of post office boxes, like these seen here. Those boxes are numbered, and each box can store an item (or, in this case, mail).

So, to access a particular post office box, you'd just need to know which post office it was in, and then the number of the box.

Arrays work in a very similar way. Each array is stored in a single variable. Then, inside of the array, we can store a number of elements, where each element is an individual value such as an integer or floating point number. Those elements are given an index, which is just like the post office box numbers in the post office that tell us where that particular element is stored.

For example, we could use an array such as this to store a list of numbers that we'd like to sort, or even the responses to a true/false quiz.

Beyond that, we are able to create multidimensional arrays in our programs. Again, each multidimensional array uses a single variable name, but now we can use two indices to refer to the **row** and **column** of the item we'd like to access. So, in this example, the x is in the second row and fourth column, so we'd use the index 1 to refer to the row and 3 to refer to the column. This is because array indices begin at 0 instead of 1. Similarly, we'd say that y is at row 4, column 2, of the multidimensional array.

Multidimensional arrays are a great way to store structured data in our programs. For example, we could use this array to represent a chess board, a gradebook, or even a bitmap image.

In this chapter, we'll learn all about how to use arrays such as these in our programs. Let's get started!
