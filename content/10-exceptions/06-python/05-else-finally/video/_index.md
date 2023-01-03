---
title: "Python Else & Finally"
pre: "4.P. "
weight: 41
date: 2019-09-10T00:00:26-05:00
hidden: true
---

{{< youtube L7hep4SmBpo >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

There are some situations where we might need to be sure a particular piece of code always executes , even if our program reaches an exception. For example, if we are reading or writing to a file, we should always close that file when we are done, even if we encounter an error. To do that, we can add a **Finally** block to our programs in Python.

Consider this sample program. It includes a **Try-Except** statement already. To add a **Finally** block, we simply add i t at the end of the **Except** statements, just like any other. Inside of that **Finally** block, we can include any code needed. In this case, we're just going to print a message showing that we've executed the code in that block. You'll also notice that we've included another print statement outside of the **Try-Except** block as well, just so we know that we've completely exited that block of code.

To really understand how a **Finally** block works, let's step through this program with several different values provided as input, and see what happens. First, we can provide the input of "5" to the program. In this case, it is able to successfully read the input and convert it to an integer. Then, it will check to see if the input is less than 0. Since it isn't, we'll move forward, and eventually reach the end of the **Try-Except** block. So, it will now execute the code in the **Finally** block, and print that output to the screen, and then it will exit the block and print the "After Try" message as well. This is a pretty simple case, since we didn't reach any exceptions.

Let's try it again, but this time we'll provide the input -5. Once again, it is able to read that input and store it as an integer just fine. However, once it reaches the **If-Then** statement, it realizes that the input is less than 0, so it will enter the block and throw a new ValueError. When that happens, the **Try-Except** block will immediately catch and try to handle the exception. So, we'll jump down a bit to the exception handler for ValueError, which will print the error message contained in the exception. Once we've handled the exception, the code will then move into the **Finally** block and print that output. So, as we can see, the **Finally** block will be executed regardless of whether the **Try-Except** block encountered an exception or not. At the very end, it will print the output outside of the block before exiting the program.

Here's one more input we can trace. This time, we'll provide some text instead of a number. So, when we try to convert the input to an integer, we'll immediately cause a ValueError. That will move our execution down to the exception handler for ValueError again, so we'll print the error there. Once again, we'll immediately move to the **Finally** block and then the code outside the **Try-Except** block.

So, as we have seen through these examples, the **Finally** block is a very handy addition to a **Try-Except** block that allows us to add additional code that will execute at the end of the block, regardless of whether we've encountered an exception or not. We'll see this used in many cases to handle closing files or resources used in our **Try-Except** statements, though later in this chapter we'll learn about the **With** statement, which is another way to handle this situation.

There is one other block we can add to our **Try-Except** statements in Python, which is the **Else** block. We can add it to our code just like we did for the **Finally** block. Note that the **Else** block should always be placed after the exception handlers, but before the **Finally** block. In addition, we can also place any code we want inside of the block, but once again we'll use a print statement so we can see when that code is executed.

So, let's go back to our earlier examples and see how this changes things. First, we'll provide 5 as input once again. So, we can successfully read the input, and find that it is greater than 0. After that, since we got all the way through the **Try** block without an exception, we can executed the code in the **Else** block, printing that output to the screen, followed by the **Finally** block and then the code after the **Try-Except** statement.

However, when we provide -5 as input, we'll run into an exception. So, the code will move into the exception handler, then immediately following that it will reach the **Finally** block and exit the **Try-Except** statement. Since there was an exception that was caught by the **Try-Except** statement, the program will skip the **Else** statement entirely.

The **Else** block can be used in a variety of interesting ways. For example, we can accept and read user input in the **Try-Except** block, but only save the data when we reach the **Else** block, since we know that the data collected didn't cause any exceptions. It can be a very powerful feature of the Python programming language.
