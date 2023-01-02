---
title: "Java Example"
pre: "5.J. "
weight: 50
hidden: true
date: 2019-09-09T00:00:26-05:00
---

{{< youtube OFE9NpUkJXo >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

To really get experience working with string in our programs, let's do a quick example together. First, we need to examine our problem statement. Ready?

Here it is!

Yikes! That is a pretty complex problem statement. So, just like we've done with our previous programs, let's break this problem statement down into smaller parts and see if we can build our program one piece at a time.

As always, we'll start with the same program skeleton that allows us to read input from either a file or the terminal. Nothing has changed here.

Now, let's start going through our problem statement. First, we notice that it tells us how to read the input, so we'll start there. The first line of the input contains the weights for each assignment as floating point numbers, separated by commas. So, we can write the code to read the first line of input. Then, we can split that input using a comma as the delimiter, allowing us to access each token in the input individually.

We also see that the weights will be given to us as floating-point numbers, so we can create an array of doubles called `weights` to store those values. We know that the size of the array is the same size as the number of tokens on the first line of input, so that makes it simple.

Next, we can use a simple **For** loop to iterate through the tokens in the `weightParts` array, storing them in the `weights` array. However, we might realize that the data types aren't compatible, since `weightParts` is storing strings, while `weights` should be storing floating-point numbers. So, we'll need to use the `Double.parseDouble()` method to convert the strings to the correct data type.

Lastly, the input tells us that the first entry should be ignored. So, we can simply change the starting index of our **For** loop from 0 to 1 to account for that. That should handle the first line of input.

After that, we'll have to parse each following line of input to find the data for a particular student. So, let's see if we can write that part of the program. First, since we don't know how many lines we are going to read, we can use a **While** loop to read until we run out of input. Inside of that loop, we can read the line, and we know we'll have to parse it later, so I'll mark that spot in our code with a comment for now. We also know that we may need to handle the case where we receive a blank line of input from the terminal. So, we can add a quick **If** statement to handle that.

Now we can look at the format of each of these lines of input. First, we notice that each item is separated by commas, so once again we can use the `split()` method to split the input into a number of tokens. Then, we can use another **For** loop to iterate over each of those tokens and find the score. Once again, we're going to ignore the name for now, so we'll use 1 as the starting index in our **For** loop.

Inside of the loop, once again we'll need to convert the token to an integer value, so we can use the `Integer.parseInt()` method to do that.

Now we get to the tricky part of the problem - actually calculating the weighted grade. The problem statement doesn't give us the formula for that, so we have to think a little. However, if you remember your basic algebra, you can calculate a weighted score by multiplying each score by the corresponding weight. Here's the formula. So, we can apply that formula in our code using the `weights` array we created earlier.

Of course, we'll also need a place to store the result, so we can create a `totalScore` variable and update it inside the loop, keeping a running sum of the scores as we calculate them.

Finally, we need to output this data to the user. Going back to our problem statement, we get a pretty good description of the output format desired. Of course, first we know that we need to print output, so we'll use a `System.out.println()` method. Since we don't have much space on our slides, I'm going to replace this method with an ellipsis, or three periods, just to save space.

Next, we see that the problem statement has a pretty strict format for our output, so that gives us a clue that we should probably use a formatted string for output, instead of just concatenating.

In the output itself, we must include the student's name, so we can add a placeholder of `"%s"` to the output, and then use the first entry in the `parts` array to get the name. Recall that the `parts` array contains the input for each student, and the first entry would be the student's name at the beginning of the line of input.

Following that, we'll output the student's score. Since it is a floating-point number, we'll use the placeholder `"%f"` in our formatted string, and use the `totalScore` variable as its value.

However, if we read closer, we realize that we must make sure the score is outputted exactly 5 characters wide, with 2 characters after the decimal point. So, we'll change our placeholder to `"%5.2f"` to account for that.

There we go! That should complete a program to perform the work specified in the problem statement. As an exercise, see if you can manually step through the code using the sample inputs provided in the textbook, just to make sure that it works correctly before you run it.
