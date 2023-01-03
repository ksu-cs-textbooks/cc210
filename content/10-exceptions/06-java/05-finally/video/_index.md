---
title: "Java Finally"
pre: "4.J. "
weight: 40
date: 2019-09-10T00:00:26-05:00
hidden: true
---

{{< youtube gW3Ntj0TqQc >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

There are some situations where we might need to be sure a particular piece of code always executes, even if our program reaches an exception. For example, if we are reading or writing to a file, we should always close that file when we are done, even if we encounter an error. To do that, we can add a **Finally** block to our programs in Java.

Consider this sample program. It includes a **Try-Catch** statement already. To add a **Finally** block, we simply add it at the end of the **Catch** statements, just like any other. Inside of that **Finally** block, we can include any code needed. In this case, we're just going to print a message showing that we've executed the code in that block. You'll also notice that we've included another print statement outside of the **Try-Catch** block as well, just so we know that we've completely exited that block of code.

To really understand how a **Finally** block works, let's step through this program with several different values provided as input, and see what happens. First, we can provide the input of "5" to the program. In this case, it is able to successfully read the input and store it in an integer. Then, it will check to see if the input is less than 0. Since it isn't, we'll move forward, and eventually reach the end of the **Try-Catch** block. So, it will now execute the code in the **Finally** block, and print that output to the screen, and then it will exit the block and print the "After Try" message as well. This is a pretty simple case, since we didn't reach any exceptions.

Let's try it again, but this time we'll provide the input -5. Once again, it is able to read that input and store it as an integer just fine. However, once it reaches the **If-Then** statement, it realizes that the input is less than 0, so it will enter the block and throw a new IllegalArgumentException. When that happens, the **Try-Catch** block will immediately catch and try to handle the exception. So, we'll jump down a bit to the exception handler for IllegalArgumentException, which will print the error message contained in the exception. Once we've handled the exception, the code will then move into the **Finally** block and print that output. So, as we can see, the **Finally** block will be executed regardless of whether the **Try-Catch** block encountered an exception or not. At the very end, it will print the output outside of the block before exiting the program.

Here's one more input we can trace. This time, we'll provide some text instead of a number. So, when we use the Scanner to try and read an integer, we'll immediately cause an InputMismatchException. That will move our execution down to the exception handler for InputMismatchException, so we'll print the error there. Once again, we'll immediately move to the **Finally** block and then the code outside the **Try-Catch** block.

So, as we have seen through these examples, the **Finally** block is a very handy addition to a **Try-Catch** block that allows us to add additional code that will execute at the end of the block, regardless of whether we've encountered an exception or not. We'll see this used in many cases to handle closing files or resources used in our **Try-Catch** statements, though later in this chapter we'll learn about the **Try with Resources** statement, which is another way to handle this situation.
