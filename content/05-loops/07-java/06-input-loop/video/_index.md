---
title: "Java User Input"
pre: "3.J. "
weight: 30
hidden: true
date: 2019-02-08T00:00:26-05:00
---

{{< youtube KSRvAtEqPbk >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

We've completed several projects that involve user input at this point, but we really haven't discussed how to build programs that can read input from the user, either via the terminal or from a file. Now that we've learned a bit about Java, let's take some time to review that code and explain how it works, so you can begin to use more user input in your programs.

Here is the sample code that we've already seen in several projects. Let's break it down and discuss what each part does.

First, in order to read input in Java, we need to import a couple of additional classes that are provided as part of the Java Development Kit. Those classes handle reading input from a file, and then parsing that input into data types that we can use in our programs. We'll spend an entire chapter learning how to use classes like this later in this course, but for now we'll just include the ones we need. So, at the top of every program where you'll be handling user input, you'll need to include these two lines. They go at the very top, before the class declaration.

If you forget to include them, the Java compiler gives us a handy error message. If you see a message like this, most likely you forgot to include these import statements at the top of your code.

Next, we need to add a short statement to the end of the main method declaration that tells the compiler that this method could _throw_ an exception. In short, that means that the code here could result in an unhandled error, so we have to declare that before compiling the code. Again, we'll spend an entire chapter on how to detect and handle these error messages later in this course.

Of course, if we forget to add that statement, the compiler will once again give us a helpful error message. So, if you see this message, you'll need to go back and add that statement to the main method declaration.

Inside the method, we'll need to declare a new variable using the type Scanner. I typically name this variable `reader` in my code, but you can name it whatever you'd like. This Scanner variable is used to read and parse input from the user, and we'll use it over and over again in our programs. Of course, since we are actually giving this variable a value inside of our **If-Then-Else** statement, we'll need to declare it here so we can access it later due to how Java handles variable scope.

Now, let's look at the **If-Then-Else** statement. What we are doing here is checking to see if the user provided any command-line arguments to this program. If so, we'll assume that the argument was the name of a file we'd like to read input from. So, this first part of the statement checks to see if the length of the arguments list is greater than 0. If it is, we know that we can initialize our Scanner to read input from that file.

If the arguments list is empty, we use the False branch to just initialize the Scanner to read from `System.in`. Just like we use `System.out` to print output to the terminal, we can use `System.in` to read input from the terminal that is entered by the user.

Finally, once we've created the Scanner, we can use it to read input. Thankfully, the Scanner class includes methods we can use to read all of the basic data types we've already learned. This example shows how we could read a single integer from the input.

For reference, here are all of the methods include in the Scanner class that could be used to read data into each of the primitive data types we've learned about so far. In a later chapter, we'll learn how to read entire sentences, or Strings, of data as well.

In summary, we really only have to add a few lines to our program to read input from the user, either via the terminal or from a file. I highly recommend learning this code very well, since you'll use it over and over again in your programs.
