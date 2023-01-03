---
title: "Python Example"
pre: "6.P. "
weight: 61
date: 2019-09-10T00:00:26-05:00
hidden: true
---

{{< youtube XaDEahMnjgU >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

Now that we've learned about how to catch and handle exceptions in our programs, let's work on creating a full example program to see how working with exceptions affects our thought process when developing code.

As always, here is our problem statement...

Zoinks! That's a pretty complex problem statement. So, let's break it down into smaller parts and see how we can implement each part individually.

First, we'll need to handle user input. Previously in this textbook, we would simply use the skeleton code provided in earlier chapters. However, now that we understand how to work with exceptions, we can improve and simplify that skeleton code a bit. So, let's look at that first.

First, we'll need to import the `sys` module. Then, we can create a reader by trying to open a file provided as the first command-line argument. Let's just assume that the user has provided a valid file for now. We'll see later how we can use our exception handlers to deal with the cases where the user has provided no file or an invalid file.

Since we are opening a file, we know that this could cause the FileNotFoundError, So, we'll need to use a **Try-Except** statement and add an exception handler to deal with that exception.

When we catch that exception, we know that the user has provided an invalid file. In that case, we can just use the terminal as our input, so we'll add a line of code to the exception handler to do just that.

In addition, since we are reading from an list, there is a chance that we could run into an IndexError, especially if we don't check the size of the list first. So, we can add one more exception handler to deal with that issue. Again, since the user didn't provide a file as a command-line input, we can just read input from the terminal instead.

That's all the code we need to initialize our reader to read either from a file, if a valid file is provided, or the terminal if not. Once we've done that, we can use a **With** statement to actually handle reading the input.

There we go! We've now created a new version of our skeleton code that does a great job of catching and handling lots of common exceptions. For the rest of this program, we'll build the logic and place it where I've highlighted this comment in the code.

So, let's dig into the actual problem statement and build our program. First, we know that we are reading a list of numbers from an input file. So, we can use a simple **While** loop to handle this. Next, we'll see that the problem statement tells us that we could find either integers or floating-point numbers. Thankfully, we can store both of those in a double data type, so we can just use the `float()` method to convert input to the correct data type. Additionally, the problem statement tells us to stop reading input when we read a line that contains a value equal to 0, so we can add a simple **If-Then** statement to deal with that situation.

Now we need to start thinking about exceptions again. If we look at our code so far, we'll see that we are converting the input we read to a floating-point number. That could cause an ValueError if the input can't be converted to that data type. So, we'll need to surround this code in a **Try-Except** statement, and add an exception handler to the bottom to handle that exception. We should also realize that reading input from a file using a **While** loop could raise an EOFError when we try and read more data after reaching the end of a file. However, when reading from the terminal, that may cause us to read an empty line if we run out of input. To deal with that, we'll raise a new EOFError there as well, and then add another exception handler for that exception. In that handler, we'll add a `break` statement, since we know we've run out of input to read.

There we go! From here, we just need to add the program logic to keep track of the minimum and maximum values. So, we'll declare two variables before the **While** loop, then use two **If-Then** statements inside of the loop to update them. Since our program will not allow the user to input the value `0`, we can use those values as our defaults for both the minimum and maximum. Otherwise, we'd have to use a different method to update those values.

Finally, we'll add two more print statements after the **While** loop to print the output.

That's all there is to it! As we can see, even though the problem statement is a bit complex, the actual logic for the problem is simple. In addition, by catching and handling several common exceptions, it actually can make our code more straightforward, since we don't need a bunch of **If-Then** statements to validate input before using it. Instead, we can just assume that it works, and if it doesn't we'll use exception handlers to get our program back on track.
