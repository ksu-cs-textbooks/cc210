---
title: "Call by Value & Call by Reference"
pre: "2. "
weight: 20
hidden: true
date: 2019-09-23T00:00:26-05:00
---

{{< youtube 5gyV1KqWaSU >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

One important concept to understand when working with functions is how arguments are given to the functions as parameters. In most languages, it really depends on the type of data provided as a parameter, and there are two common ways that this can be handled: call by value, and call by reference. In this video, we'll look at a couple of examples of each one, using some simple pseudocode functions to help explain what's going on.

In this first example, we'll explore a function that uses parameters in a call by value way. Typically any primitive data types, such as integers, floating point numbers, and boolean values are handled in a call by value way. However, most programming languages do NOT handle strings as call by value, even though they may be considered primitive data types in some cases.

To the left, I've included two boxes - the stack and the heap. While I won't get into too much detail here, when a program runs on your computer, data can be stored in either the stack or the heap, which represent two different locations in memory that are handled in two different ways. It is really this distinction that causes data to be handled either as call by value or call by reference. So, let's explore this sample program and see how it works.

We'll start in the main function. The first line creates a variable `x` and stores the value 5 in it. Each function is given a specific piece of memory in the stack, and any variable created in that function has an entry in the stack. So, when that line runs, we'll make sure there is a section of the stack for the main function, and store the variable `x=5` in one box.

The next line will set the value of the variable `y` to whatever is returned by the addThree function, which uses the variable `x` as an argument. Since we can't store a value in `y` until we've called the function, we'll need to do that first.

So, when that function is called, it creates a new section on the stack to store its variables. The parameter variable, `x`, will be given the same value as the argument provided where the function is called. So, in that portion of the stack, we'll also store another variable `x=5` in that box. That value comes from the variable `x` in the main function's part of the stack, but they are two different values.

Next, the addThree function will add 3 to the value stored in `x`. So, it will update the value for `x` in its portion of the stack, making that square `x=8`.

Finally, the addThree function will return the value stored in `x`. So, that value will be given back to the main function and stored in its slot for the variable `y`.

Once the addThree function is done executing, its space on the stack will be removed, and all of its data will be lost. However, since it returned the value `8` to main, that value is now stored in the variable `y`.

Finally, the main function will print the value of both variables, and we'll get 5 followed by 8. Pretty simple, right?

Things get a bit trickier when we deal with more advanced data types, such as arrays and strings. In a later chapter, we'll also learn about objects, which are handled in the same way. These data types are handled in a call by reference way, as we'll see in this example.

First, the main function creates an array that stores two values, and stores that array in the variable `x`. However, since the array isn't a primitive data type, it can't be stored in the stack. So, instead, the program will allocate some space in the heap to store the array, and then the "address" or "reference" to that location in the heap is stored in the variable `x`. In effect, the variable `x` now says "if you want to find the array I'm supposed to be storing, look at this location in the heap".

What happens when we use that array as an argument for a function? Well, as before, the function will get its own space on the stack. Similarly, the value stored in the variable `x` will be provided to the function as an argument, so that value will also be stored in the variable `x` in the function changeLast. However, in this case, that value is actually the reference to the location in the heap where the array is stored. That is why we say this is "call by reference" since we are giving the function a reference to the data instead of the actual value of the data.

So, when the function updates the last element in the array to be 5, it actually changes the value of that slot in the array that is stored in the heap. So, when the function exits and control returns to the main function, that value is now changed in the array referenced by the variable `x` in main as well. So, when we print those values, we'll get 1 for the first element, and 5 for the second element. So, our function was able to update that array, without even needing to return it back to main.

However, there is one major caveat that we must be aware of. In this example, we can step through the code until it gets to the changeLast function. As before, the reference to the array stored in variable `x` in main is given to changeLast as a parameter, so initially they are both referencing the same array on the heap.

However, inside of changeLast, we are _reassigning_ the value of the variable `x` to a new array. When we do that, we'll create a new array on the heap, and update the reference stored in `x` to point to that new array. When we do that, notice that the value of `x` in the main function's portion of the stack has **not** changed.

So, when the changeLast function has exited and we go back to main, the array is unchanged because we didn't change the value of the array referenced by the variable `x`. So, we would either have to return the reference to the new array from changeLast, or update the values in the existing array within changeLast instead of just creating a new array.

I hope this makes sense! To be honest, learning how to understand call by value and call by reference is one of the trickiest parts of learning to program, and even seasoned veterans sometimes struggle with it. One of the best ways to learn is to simply write lots of functions, and as you do you'll start to get a feel for what works and what doesn't.
