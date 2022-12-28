---
title: "Java Compile & Run"
pre: "3.J. "
weight: 30
date: 2019-02-05T10:53:26-05:00
hidden: true
---

{{< youtube x6bEKqhiZHY >}}

#### Resources

#### Video Script

Let's review how to compile and run a program written in Java using Codio. There are several ways we can accomplish this task.

First, we can always use the built-in Linux Terminal to compile and run any programs we create. In fact, we could follow very similar steps to compile and run Java code on just about any computer!

In Codio, there are several ways to access the Terminal. We can go to the **Tools** menu and find it there. Or, we can press <kbd>SHIFT</kbd> + <kbd>ALT</kbd> + <kbd>T</kbd> anytime to open it using a keyboard shortcut. Finally, we can always click on the Terminal icon at the top of the filetree. In addition, most of the Codio books and projects in this course will have an **Open Terminal** option available on the **Run Menu** as well. So, there are lots of ways we can get to the Terminal, so take your pick.

On the Terminal itself, we should review a few basic Linux commands that will help us get around the filesystem. If you are completely new to Linux, there is another video on this page that gives a great overview of the Linux Terminal and how to use it.

First, we can always find our current location by using the `pwd` command. That stands for "present working directory", and should give you output similar to this. In our case, we are in the "home" folder, then inside the "codio" folder, and finally the "workspace" folder. That is the default location where all of our code is stored in Codio, so we'll always start in that folder.

To see the files and folders inside that folder, we can use the `ls` command. It is short for "list" and it will give us a list of all of the things inside of our present working directory. When we are in the Codio tutorials, we'll see folders here for each chapter. So, we'll need to open the folder for our current chapter. You can find the folder for the current chapter in the filetree to the far left of the screen.

So, to enter that folder, we'll use `cd` followed by the name of the folder we'd like to open. In this case, we'll do `cd 1j-hello`.

Once we are in that folder, we can do `ls` once again to see the files it contains. We should hopefully see `HelloWorld.java` there. If so, we can move on.

Before we can run our Java programs, we have to compile the code into a format that the computer can understand. So, we'll use the Java Compiler to perform that action. In the Terminal, we can type `javac HelloWorld.java` to compile our program. If everything works correctly, there won't be any output. However, we can use the `ls` command again, and we should now see a new file called `HelloWorld.class`. That is the Java bytecode for our program.

If that file isn't created, or the Java Compiler gives you any output, that probably means that you have a problem in your `HelloWorld.java` file. To fix it, go back to the previous page and see if you can correct the error. You can also refer to the next page for some tips on how to fix common errors in your code.

Finally, if everything worked correctly, we can type `java HelloWorld` to run our program. Hopefully we should see the expected output from our program appear on the Terminal!

Codio also includes some shortcuts for compiling and running programs. Most of the resources in this class will include these options, so feel free to use them anytime.

First, we'll need to make sure we have our `HelloWorld.java` source file open. Then, we can click on the **Run Menu**, which is here at the top of the screen, and select the appropriate options there. If we need to compile our program, we can choose **Java - Compile File** first. We should see Codio open a Terminal window, and it will automatically fill in the appropriate command. They look a bit different than the command we learned earlier, mainly because these commands include the folder path directly in the command.

Then, we can go back to our file, and choose **Java - Run File** to execute the code we just compiled. Pretty simple, right?

Many Codio lessons also include short assessments that help check your code and make sure it is working correctly. Whenever you see one, you'll want to take the time and make sure you are able to complete the assessment successfully before you move on. They are a great way to check and make sure you understand what the lesson is about. Also, these assessments are used to generate your grade on the tutorial assignments. So, make sure you take a minute and complete the assessments before moving on!
