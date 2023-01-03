---
title: "What is an Exception?"
pre: "2. "
weight: 20
---

An _exception_ is an error caused by some problem in a computer program. It could be due to invalid input from the user, an issue with the system that the code is running on, or even a bug or unintended situation written into the code itself.

For example, we know from mathematics that we cannot divide a number by {{< math >}}$ 0 ${{< /math >}}. Specifically, the result of dividing any number by zero is _undefined_, so we have no way of expressing that value. In a computer program, we can cause an exception by attempting to divide any number by 0, since even a computer has no way to handle that situation and store the result in a variable. So our program would crash, unless we wrote code to handle that situation and correct the error.

Another common cause of an exception would be trying to read data from a file that doesn't exist. Let's assume that the user is asked to enter a filename, but accidentally spells the name incorrectly. When our program asks the underlying operating system to open that file, the operating system will tell our program that the file doesn't exist, so we can't open it and read the data. That will cause an exception in our program! In this case, we could easily write code that handles that exception and asks the user to input the file name again, preventing the user from having to restart the program just to recover from such a simple error.

In this chapter, we'll see how to handle many common exceptions in our programs, as well as how to create our own exceptions when we detect errors in our own code. 