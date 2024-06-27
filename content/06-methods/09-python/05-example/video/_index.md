---
title: "Python Example"
pre: "7.P. "
weight: 71
date: 2019-09-23T00:00:26-05:00
hidden: true
---

{{< youtube H2WN8xxv8Ao >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

Now that we've seen how to add functions to our programs, let's work through a full example program together and explore some of the thought processes and reasoning behind the design decisions made while building a program that uses function.

As always, we should start with our problem statement, which you can find on this page.

Uhhhhh... that's a pretty complex problem. There are so many things going on there. Normally, I'd say we should break the program down into smaller parts and build those first.

However, we've been learning all about functions in this module. So, instead of just breaking it down into parts, we can break it down into _functions_ instead. That's a great way to use our newfound skills and improve our programs!

First, we'll probably need to figure out how to open and read the input file. So, we can create a function called `read_input()`, which accepts a string giving the name of a file as an argument, and returns a list of floating point numbers that we'll read from the input file. In a previous module, we learned all about how to do that. So, we'll go ahead and start with this skeleton code which opens the file in a With statement inside of a Try statement, and it also catches and handles most of the expected exceptions from reading and working with a file. The biggest difference is that we should now return an empty list inside of each catch statement, instead of just ending the program. As we'll see a bit later, we can use that in our `main()` function to determine if we successfully read data from the file.

Now, let's work on the actual code to read data from the file. As always, we'll place this code here, where the comment is in this starter code. As stated in the problem statement, we need to read an unknown number of floating-point values from the input file. So, we can use a while loop to read the numbers themselves until the file is empty, converting the inputs to a floating point value and appending them to the list as we go.

Finally, once we've read all the numbers in the file, we can return that list as the output of this function.

Next, we'll need functions to calculate the maximum and minimum values in each list. We've already seen programs that calculate the maximum and minimum values before, and the code is pretty simple. In each function, we'll start by setting the initial value to the first element in the list. Then, we'll use a for each loop to iterate through each value, and update our minimum or maximum value as needed. This part should be pretty familiar by now.

Likewise, we'll need to create two functions to calculate the sum and average of a set of numbers. Once again, these two functions are very similar. In fact, they are so similar, the nearly all of the code is identical. This is because we actually need the sum of the numbers in order to calculate the average. So, we are really duplicating our code! As we learned earlier in this chapter, we should strive to follow the DRY, or don't repeat yourself, paradigm. So, if we already have a function that will calculate the sum of a list of numbers, we can just call that function from within our function for average. That makes the code even shorter and easier to understand!

Lastly, we'll need to produce our output. The problem statement gives a great example, so all we have to do is create four formatted strings that produce the desired output, rounding each value to a single decimal place.

That covers all of the functions we need to make this program work. Now we just need to put it all together in our `main()` function. To help, I've included the function declarations for each function we've built so far at the bottom of this example, but I've omitted the code. Ideally, just by looking at the function's declaration, we should be able to figure out what it does.

So, in our `main()` function, we start by checking to see if two command-line arguments were provided, the name of the program which is automatically included, as well as the name of the file to open.. If not, we can print an error message and exit the program. Notice that we are calling the `main()` function in our main guard with the command-line arguments in `sys.argv` provided as an argument.

Next, we can pass that command-line argument to the `read_input()` function, which will try to open the file provided as an argument, and then return a list of floating-point numbers that contains the data stored in that file. We can store that returned value in the `numbers` variable.

Earlier, we wrote our `read_input()` function to return an empty list if it is unable to read input from the file for any reason. So, we'll need to add a quick If-Then statement to check that the list isn't empty before continuing. If it is, we can just exit the program using the `return` keyword.

Following that, we can use the four functions we wrote earlier to find the minimum, maximum, sum, and average of the numbers in the list. Each function get the list of numbers as an argument, and returns a value that we can store in a variable.

Finally, we can call the `print_output()` function, and provide it all four of the variables it needs as arguments. That will print the required output to the screen. Since that function doesn't return a value, we don't need to store its output in a variable.

At the very end, we've included a `return` keyword, just to show that we are at the end of the `main()` function. This isn't strictly required, but some coding style guides recommend that we include it.

There we go! We were able to take a very complex problem statement, break it down into several functions, write each function individually, and then call each function from the `main()` function to actually build our program. Now, if we look at just the code in the `main()` function, we see that it is really easy to understand what this program does. It "reads input" from a file, then find the minimum, maximum, sum, and average of a list of numbers, and finally prints the output containing those numbers.

This is a major added bonus to using functions in our code. If we are careful about how we name our functions and how they operate, we can essentially create an outline of our program just by using those function names in the `main()` function. It is a great way to build readable code!
