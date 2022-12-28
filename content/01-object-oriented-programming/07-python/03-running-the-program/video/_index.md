---
title: "Python Run as Script"
pre: "3.P. "
weight: 31
hidden: true
date: 2019-02-05T10:53:26-05:00
---

{{< youtube uBvsct1TLhY >}}

#### Resources

#### Video Script

Let's review how to run a program written in Python using Codio. There are several ways we can accomplish this task.

First, we can always use the built-in Linux Terminal to run any programs we create. In fact, we could follow very similar steps to compile and run Python code on just about any computer!

In Codio, there are several ways to access the Terminal. We can go to the **Tools** menu and find it there. Or, we can press <kbd>SHIFT</kbd> + <kbd>ALT</kbd> + <kbd>T</kbd> anytime to open it using a keyboard shortcut. Finally, we can always click on the Terminal icon at the top of the filetree. In addition, most of the Codio books and projects in this course will have an **Open Terminal** option available on the **Run Menu** as well. So, there are lots of ways we can get to the Terminal, so take your pick.

On the Terminal itself, we should review a few basic Linux commands that will help us get around the filesystem. If you are completely new to Linux, there is another video on this page that gives a great overview of the Linux Terminal and how to use it.

First, we can always find our current location by using the `pwd` command. That stands for "present working directory", and should give you output similar to this. In our case, we are in the "home" folder, then inside the "codio" folder, and finally the "workspace" folder. That is the default location where all of our code is stored in Codio, so we'll always start in that folder.

To see the files and folders inside that folder, we can use the `ls` command. It is short for "list" and it will give us a list of all of the things inside of our present working directory. When we are in the Codio tutorials, we'll see folders here for each chapter. So, we'll need to open the folder for our current chapter. You can find the folder for the current chapter in the filetree to the far left of the screen.

So, to enter that folder, we'll use `cd` followed by the name of the folder we'd like to open. In this case, we'll do `cd 1p-hello`.

Once we are in that folder, we can do `ls` once again to see the files it contains. We should hopefully see `HelloWorld.py` there. If so, we can move on.

To run our program, we must type the command `python3` followed by the name of the file that contains our code. So, in this case, we want to enter `python3 HelloWorld.py` to run our program.

Also, it is very important to use the command `python3` instead of just `python`. This is because the `python` command runs Python version 2, which is out of date. So, always be sure to use `python3` on the Terminal.

Codio also includes some shortcuts for running programs. Most of the resources in this class will include these options, so feel free to use them anytime.

First, we'll need to make sure we have our `HelloWorld.py` source file open. Then, we can click on the **Run Menu**, which is here at the top of the screen, and select the appropriate option there. For Python, we can select **Python - Run File** to run our file using the Python interpreter. The command looks a bit different than the command we learned earlier, mainly because this command includes the folder path directly in the command.

Many Codio lessons also include short assessments that help check your code and make sure it is working correctly. Whenever you see one, you'll want to take the time and make sure you are able to complete the assessment successfully before you move on. They are a great way to check and make sure you understand what the lesson is about. Also, these assessments are used to generate your grade on the tutorial assignments. So, make sure you take a minute and complete the assessments before moving on!
