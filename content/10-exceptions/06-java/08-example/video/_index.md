---
title: "Java Example"
pre: "6.J. "
weight: 60
date: 2019-09-10T00:00:26-05:00
hidden: true
---

{{< youtube j-glHqHHWBQ >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

Now that we've learned about how to catch and handle exceptions in our programs, let's work on creating a full example program to see how working with exceptions affects our thought process when developing code.

As always, here is our problem statement...

Zoinks! That's a pretty complex problem statement. So, let's break it down into smaller parts and see how we can implement each part individually.

First, we'll need to handle user input. Previously in this textbook, we would simply use the skeleton code provided in earlier chapters. However, now that we understand how to work with exceptions, we can improve and simplify that skeleton code a bit. So, let's look at that first.

We can start by creating a class and a main method declaration. Then, we'll need to create a Scanner object to read data from a file. Let's just assume that the user has provided a file as a command-line argument for now. We'll see later how we can use our exception handlers to deal with the cases where the user has provided no file or an invalid file.

Since we are opening a file, we know that this could cause the FileNotFoundException, which is a checked exception in Java. So, we could add a `throws` clause to the main method declaration, but that doesn't match the problem statement, which asks us to catch and handle all common exceptions. Surely a checked exception would count as a common exception. So, instead, we'll need to use a **Try-Catch** statement.

When we catch that exception, we know that the user has provided an invalid file. In that case, we can just use the terminal as our input, so we'll add a line of code to the exception handler to do just that.

In addition, since we are reading from an array, there is a chance that we could run into an ArrayIndexOutOfBoundsException, especially if we don't check the size of the array first. So, we can add one more exception handler to deal with that issue. Again, since the user didn't provide a file as a command-line input, we can just read input from the terminal instead.

That's all the code we need to initialize our scanner to read either from a file, if a valid file is provided, or the terminal if not. Once we've done that, we can use a **Try with Resources** statement to actually handle reading the input. Notice that we are creating a new Scanner variable called reader here, since Java 8 requires us to create a new variable in our **Try with Resources** statement. We'll also add a generic exception handler at the bottom, just in case we reach an IOException or another exception when reading the file. However, these are not common, so we won't worry about handling them directly.

There we go! We've now created a new version of our skeleton code that does a great job of catching and handling lots of common exceptions. For the rest of this program, we'll build the logic and place it where I've highlighted this comment in the code.

So, let's dig into the actual problem statement and build our program. First, we know that we are reading a list of numbers from an input file. So, we can use a simple **While** loop to handle this. Next, we'll see that the problem statement tells us that we could find either integers or floating-point numbers. Thankfully, we can store both of those in a double data type, so we can just use the `nextDouble()` method to read input. Additionally, the problem statement tells us to stop reading input when we read a line that contains a value equal to 0, so we can add a simple **If-Then** statement to deal with that situation.

Now we need to start thinking about exceptions again. If we look at our code so far, we'll see that we are reading a number using the Scanner object. That could cause an InputMismatchException. So, we'll need to surround this code in a **Try-Catch** statement, and add an exception handler to the bottom to handle that exception. We should also realize that reading input from a file using a **While** loop could cause a NoSuchElementException if we run out of input, so we'll add another exception handler for that exception. In that handler, we'll add a `break` statement, since we know we've run out of input to read.

There we go! From here, we just need to add the program logic to keep track of the minimum and maximum values. So, we'll declare two variables before the **While** loop, then use two **If-Then** statements inside of the loop to update them. Since our program will not allow the user to input the value `0`, we can use those values as our defaults for both the minimum and maximum. Otherwise, we'd have to use a different method to update those values.

Finally, we'll add two more print statements after the **While** loop to print the output.

That's all there is to it! As we can see, even though the problem statement is a bit complex, the actual logic for the problem is simple. In addition, by catching and handling several common exceptions, it actually can make our code more straightforward, since we don't need a bunch of **If-Then** statements to validate input before using it. Instead, we can just assume that it works, and if it doesn't we'll use exception handlers to get our program back on track.
