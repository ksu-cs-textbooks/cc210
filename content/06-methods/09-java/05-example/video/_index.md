---
title: "Java Example"
pre: "7.J. "
weight: 70
hidden: true
date: 2019-09-23T00:00:26-05:00
---

{{< youtube rvGRghgcCZM >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

Now that we've seen how to add functions to our programs, let's work through a full example program together and explore some of the thought processes and reasoning behind the design decisions made while building a program that uses function.

As always, we should start with our problem statement, which you can find on this page.

Uhhhhh... that's a pretty complex problem. There are so many things going on there. Normally, I'd say we should break the program down into smaller parts and build those first.

However, we've been learning all about functions in this module. So, instead of just breaking it down into parts, we can break it down into _functions_ instead. That's a great way to use our newfound skills and improve our programs!

First, we'll probably need to figure out how to open and read the input file. So, we can create a function called `readInput()`, which accepts a string giving the name of a file as an argument, and returns an array of floating point numbers that we'll read from the input file. In a previous module, we learned all about how to do that. So, we'll go ahead and start with this skeleton code which opens the file in a Try with Resources statement, and it also catches and handles most of the expected exceptions from reading and working with a file. The biggest difference is that we should now return an empty array inside of each catch statement, instead of just ending the program. As we'll see a bit later, we can use that in our `main()` function to determine if we successfully read data from the file.

Finally, we need to do a little trick to figure out how many line are in the input file. There are many ways to do this, but one of the simplest is to open the file twice. So, we'll create a second scanner object inside of our Try with Resources statement, and use that inside of this code.

Now, let's work on the actual code to read data from the file. As always, we'll place this code here, where the comment is in this starter code. As stated in the problem statement, we need to read an unknown number of floating-point values from the input file. Unfortunately, since we don't know how many, we can't actually create our array. We could give it some large size, such as 100 or 1000, but what if we get an input file even bigger than that? Hard-coding a value like that is a very poor idea, since it could lead to problems. Instead, we could just see how many lines there are in the file, and use that value.

So, we'll just create a simple While loop that reads the each line in the input file and updates a counter variable to keep track of how many lines are read.

Once we've done that, we can use the counter variable to initialize our array of floating point values to the correct size. Then, we'll use a second While loop to read the numbers themselves. Notice that this While loop is using the second scanner object, `scanner2`. This is because the first scanner object is now at the end of the file, and there isn't a good way to reset it. So, we'll just use a second one to read the file from the beginning again.

Finally, once we've read all the numbers in the file, we can return that array as the output of this function.

Next, we'll need functions to calculate the maximum and minimum values in each array. We've already seen programs that calculate the maximum and minimum values before, and the code is pretty simple. In each function, we'll start by setting the initial value to the first element in the array. Then, we'll use an enhanced for loop to iterate through each value, and update our minimum or maximum value as needed. This part should be pretty familiar by now.

Likewise, we'll need to create two functions to calculate the sum and average of a set of numbers. Once again, these two functions are very similar. In fact, they are so similar, the nearly all of the code is identical. This is because we actually need the sum of the numbers in order to calculate the average. So, we are really duplicating our code! As we learned earlier in this chapter, we should strive to follow the DRY, or don't repeat yourself, paradigm. So, if we already have a function that will calculate the sum of an array of numbers, we can just call that function from within our function for average. That makes the code even shorter and easier to understand!

Lastly, we'll need to produce our output. The problem statement gives a great example, so all we have to do is create four formatted strings that produce the desired output, rounding each value to a single decimal place.

That covers all of the functions we need to make this program work. Now we just need to put it all together in our `main()` function. To help, I've included the function declarations for each function we've built so far at the bottom of this example, but I've omitted the code. Ideally, just by looking at the function's declaration, we should be able to figure out what it does.

So, in our `main()` function, we start by checking to see if a single command-line argument was provided. If not, we can print an error message and exit the program.

Next, we can pass that command-line argument to the `readInput()` function, which will try to open the file provided as an argument, and then return an array of floating-point numbers that contains the data stored in that file. We can store that returned value in the `numbers` variable.

Earlier, we wrote our `readInput()` function to return an empty array if it is unable to read input from the file for any reason. So, we'll need to add a quick If-Then statement to check that the array isn't empty before continuing. If it is, we can just exit the program using the `return` keyword.

Following that, we can use the four functions we wrote earlier to find the minimum, maximum, sum, and average of the numbers in the array. Each function get the array of numbers as an argument, and returns a value that we can store in a variable.

Finally, we can call the `printOutput()` function, and provide it all four of the variables it needs as arguments. That will print the required output to the screen. Since that function doesn't return a value, we don't need to store its output in a variable.

At the very end, we've included a `return` keyword, just to show that we are at the end of the `main()` function. This isn't strictly required, but some coding style guides recommend that we include it.

There we go! We were able to take a very complex problem statement, break it down into several functions, write each function individually, and then call each function from the `main()` function to actually build our program. Now, if we look at just the code in the `main()` function, we see that it is really easy to understand what this program does. It "reads input" from a file, then find the minimum, maximum, sum, and average of an array of numbers, and finally prints the output containing those numbers.

This is a major added bonus to using functions in our code. If we are careful about how we name our functions and how they operate, we can essentially create an outline of our program just by using those function names in the `main()` function. It is a great way to build readable code!
