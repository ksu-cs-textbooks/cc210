---
title: "Theory"
pre: "2. "
weight: 20
---

{{% youtube 9rzcp1hw_kg %}}

[Video Materials]({{<relref "./video">}})

## In Theory

Arrays are a special type of variable that can store multiple items of the same type, so 'int' or 'bool(ean)'. Some programming languages, such as Java, comes with support for arrays built into the language. While other languages, such as Python, require us to adapt other aggregate data types to build arrays. 

In general, we will stick with storing items of the same type in each array.

A great way to think of an array is like a set of post office boxes that we might see at our local post office, as shown in the image below. Each box has a number that uniquely identifies it. So, if we know which number is ours, we can easily receive our mail. 

![Post Office Boxes](/images/08-array/6.2.postofficeboxes.wikimedia.jpg)[^1]

[^1]: File:USPS Post office boxes 1.jpg. (2017, May 17). Wikimedia Commons, the free media repository. Retrieved 18:17, November 5, 2018 from https://commons.wikimedia.org/w/index.php?title=File:USPS_Post_office_boxes_1.jpg&oldid=244476438.

Similarly, the post office can look at the address line on the letter to find the post office box number it should go to, and then they can place it in the correct place.

An array works in a very similar fashion. Arrays consist of a set of boxes with sequential numbers, starting at 0. So, an array that has 5 boxes, or _elements_, would have 5 boxes, numbered 0 through 4. The number for a particular element is called its _index_. 

For example, let's consider an array that contains 5 elements, and each element is one of the first five letters of the alphabet as shown in the image below. 

![Array Indexes and Elements](/images/08-array/6.2.array.russfeld.png)

In this array, we'd say that the _element_ at _index_ 0 is `a`. 

## Multidimensional Arrays

One of the most powerful features of arrays is the ability to create a _multidimensional array_. A multidimensional array is an array that contains another array within each element, sometimes many layers deep. This is very useful when we need to store data in a grid layout, for example.

The image below shows how data might be represented in a 2-dimensional array. The element `x` is located in row 1, column 3. So, it would be part of the array stored in index 1 in the primary array, and the element itself is at index 3 in the array stored there. 

![2-Dimensional Array](/images/08-array/6.2.2darray.russfeld.png)

We'll learn how to work with arrays in a specific programming language later in this chapter. 
