---
title: "Handling Exceptions"
pre: "4. "
weight: 40
---

{{% youtube Tp9jbKRVqQI %}}

[Video Materials]({{<relref "./video">}})

Now that we've learned a bit about what exceptions are, let's take a look at an example to see how we might encounter exceptions in our programs and how we can possibly handle them. 

Consider the following program:

![Exceptions Example Flowchart](/images/10-except/8.4.handle.png)

In this program, we first get the name of a file to open from the user. Then, we open that file and create a reader to allow us to read data from the file. After that, we read the first item of the file into a variable, and finally we print that variable to the screen. It's a very simple program, but there are several places where an exception could occur.

### File Not Found

First, when we try to open the file, we could find out that the file does not exist. In most programming languages, that situation would cause an exception when this line is executed:

![File Not Found Exception Flowchart](/images/10-except/8.4.nofile.png)

### IO Error

In addition, at any time we try to read data from a file, we could get an IO (input/output) error from the operating system. This can happen if the file suddenly becomes inaccessible, or if the system is unable to read the data correctly from the storage device it is stored on. In that case, we'll get an exception from executing this line of code:

![IO Exception Flowchart](/images/10-except/8.4.ioerror.png)

## Handling Exceptions

To handle these exceptions, we can simply mark the section of our code where an exception may occur. Each programming language does this a bit differently, but the idea is the same. In the flowchart below, I've drawn a box around several parts of the program that we know may cause an exception. Then, along with that section, we can specify _exception handler_ code to be executed in the case that an exception occurs. So, in this example, our program will simply print `Error` and terminate instead of trying to open and read the file. 

![Handle Exception Flowchart](/images/10-except/8.4.try.png)

So, let's go back and revisit one of the exceptions listed above. Now, when the user provides an invalid file as input, our program would execute the highlighted steps in the flowchart below:

![Handled File Not Found Exception Flowchart](/images/10-except/8.4.catch.png)

As we can see in this flowchart, when our program reaches an exception, it immediately switches over to the exception handler code to handle that exception. 

Of course, there are many different ways we can structure this program to achieve the same outcome. Later in this chapter we'll learn how to handle exceptions in our chosen programming language. 