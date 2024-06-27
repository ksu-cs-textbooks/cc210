---
title: "Java Try-Catch"
pre: "2.J. "
weight: 20
date: 2019-09-10T00:00:26-05:00
hidden: true
---

{{< youtube QvH6BImQxII >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

Let's take a closer look at how we can use a **Try-Catch** statement in Java to detect and handle exceptions that are caused by our program. Specifically want to take a program that looks like this, and update it to look more like this, with code to catch and handle exceptions that are thrown by the program.

To do this, we can start with a simple program. This program is very similar to the skeleton code we've been using throughout the textbook. In this program, we can either accept input from a file if one is provided as a command-line argument. If not, we'll accept input via the terminal. The program will then read a single integer from input, and print that integer to the terminal. Even though this is a very simple program, as we'll soon see, there are lots of ways it can cause an exception.

First, let's look at the general case and just try to catch all possible exceptions in the program. To do that, we must first surround all of the code with a **Try** block. We can omit the variable declaration at the top of the program, since it cannot possibly cause an exception. Of course, when we add a **Try** block, we'll need to make sure we indent everything inside of it as well, just to make our code more readable.

Once we have our **Try** block in place, we must add at least one **Catch** block afterwards. Every **Try** block must include at least one **Catch** block in order to be valid. So, we'll add a **Catch** block to the bottom of our code, outside of the closing curly brace of the **Try** block.

Inside of the **Catch** block, we've chosen to catch the generic Exception, which covers all possible exceptions. We'll also need to remember to import that module using an import statement at the top of the file.

Finally, inside of the **Catch** block, we can add code to handle the exception. In this case, we'll simply print an error message to the screen, alerting the user that an exception has occurred. Later in this chapter, we'll see other ways to handle the exceptions beyond just printing a message, but for now it makes our programs easy to follow.

There we go! We've successfully modified our program to catch and handle any possible exception. However, this may not be very useful, since our program is unable to tell us exactly what type of exception has occurred. Likewise, the only message the user gets is "Error" without any additional context. Can we modify our program to catch and handle more specific exceptions?

We sure can! Let's look at some of the possible exceptions that could occur in this code. First, we notice here that we are opening a file. So, there is always a possibility that the file provided as input doesn't exist. In that case, the program would throw a FileNotFoundException. So, we can modify our existing **Catch** statement to catch a FileNotFoundException instead. When we do that, we'll need to update the import statement at the top of the file, and we may also want to change the error message printed by the program to be a bit more specific.

Next, we might notice that the program is reading input from a file. Whenever we do that, there is a possibility that the program could throw an IOException, especially if the file we are reading from becomes unavailable or is damaged. So, to handle that exception, we can add a second **Catch** statement below the first. This one will catch an IOException. We'll also need to remember to import that exception at the top of the file as well.

At this point, let's take a step back and consider an important question: does the order of these catch statements matter? For example, what if I reverse them, like this? Would that work?

Unfortunately, this would not work the way we want it to. This is because exceptions in Java are hierarchical, meaning that some exceptions are more specific versions of others. In this case, the FileNotFoundException is a more specific version of an IOException. We can find this in the Java documentation, shown here. The link to this documentation can be found in the textbook.

So, whenever a FileNotFoundException is thrown, it will be handled by the first **Catch** statement in this example instead of the second one, which is where we want it to be handled. Therefore, it is recommended to always place the **Catch** statements for the most specific exceptions first, and then the more general ones later. So, we'll need to go back to the way these were ordered previously.

Finally, there is one more important exception we must consider. Since we are telling the Scanner to read an integer, it will throw an InputMismatchException if the Scanner reads anything other than an integer. So, we'll need to add one more **Catch** statement and import statement to handle that exception as well.

There we go! We've taken a simple program, and added a **Try-Catch** statement to handle many different exceptions that could occur while running this code. It is always a good idea to catch and handle exceptions whenever possible in your code so your programs are much more user friendly and don't crash when they run into problems.
