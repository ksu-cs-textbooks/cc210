---
title: "Handling Exceptions"
pre: "1. "
weight: 10
hidden: true
date: 2019-09-10T00:00:26-05:00
---

{{< youtube Tp9jbKRVqQI >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

So far in this chapter we've learned all about how our programs can run into exceptions while executing code. For example, consider the program shown here in this flowchart. It appears to be a very simple program, right? We get the name of a file as input, then open and read the file, and finally print the contents of the file to the terminal. Surely a program like this doesn't have any hidden exceptions.

What if the file we are supposed to open doesn't exist? What should our program do in that case?

Or what if the computer is unable to read the file itself? Can our program handle that error?

Thankfully, most programming languages include a construct that we can use to detect and handle these exceptions in our program. First, we must identify where the exceptions can occur. I've updated the flowchart with a box that highlights steps in the program that are known to cause exceptions. In many languages, this is known as a **Try** block, since we want to _try_ and run this code, but we might run into an exception.

 Then, we can add another statement to define which exceptions we'd like to catch. In this case, we'll just catch all exceptions. That means that whenever an exception occurs inside of this box, we'll be able to do something about it.

 Finally, we can create an _exception handler_ that tells our program what to do when an exception occurs and is caught. In this program, we'll just print an error message and exit the program.

 So, now, if we execute the program and provide a file that doesn't exist as input, our program can detect the exception, catch it, and execute the code in the exception handler instead.  

 This is the simplest version of exception handling in our program, but it is one that we'll see over and over again in our programs going forward. As we move on in this chapter, we'll expand on this simple case with more features and techniques to make our programs even more powerful and robust.
