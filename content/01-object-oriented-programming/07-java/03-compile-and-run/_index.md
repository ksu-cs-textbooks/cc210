---
title: "Compile and Run"
pre: "3. "
weight: 30
---

{{< youtube x6bEKqhiZHY  >}}

[Video Materials]({{% relref "./video" %}})

<!-- TODO Update Screenshots -->
<!-- TODO Update Video -->

<p style="color:red; font-sze:150%">Note: the video's "Run" menu reference is obsolete.</p>

Now that we've written our first Java program, we must compile and run the program to see the fruits of our labors. There are many different ways to do so. We'll discuss each of them in detail here. 

{{% notice note "Codio vs. Other IDE" %}}

This textbook was written for the Codio learning environment, so many of the steps below will reference features in Codio. However, most integrated development environments (IDEs) also include features to compile and run your code, and you can always do so manually using commands in the terminal for your operating system. If you aren't sure how to get it to work, ask for help!

{{% /notice %}}

## Terminal

Codio includes a built-in Linux terminal, which allows us to perform actions directly on a command-line interface just like we would on an actual computer running Linux. We can access the Terminal in many ways:

1. Selecting the **Tools** menu, then choosing the **Terminal** option
1. Pressing SHIFT + ALT + T in any Codio window (you can customize this shortcut in your Codio user preferences)
1. Pressing the **Open Terminal** icon in the file tree

Additionally, some pages may already open a terminal window for us in the left-hand pane, as this page so helpfully does. As we can see, we're never very far away from a terminal.

{{% notice info "New to Linux?" %}}

No worries! We'll give you everything you need to know to compile and run your Java programs in this course.

If you'd like to learn a bit more about the Linux terminal and some of the basic commands, feel free to check out this great video on YouTube:

{{< youtube oxuRxtrO2Ag  >}}

{{% /notice %}}

Let's go to the terminal window and navigate to our program. When we first open the Terminal window, it should show us a prompt that looks somewhat like this one: 

![Initial Terminal View](/images/01-oop/1.3.j.3.terminal1.png)

There is quite a bit of information there, but we're interested in the last little bit of the last line, where it says `~/workspace`. That is the current directory, or folder, our terminal is looking at, also known as our _working directory_. We can always find the full location of our working directory by typing the `pwd` command, short for "Print Working Directory," in the terminal. Let's try it now!

Enter this command in the terminal:

```bash
pwd
```

and we should see output similar to this:

![pwd Command Output](/images/01-oop/1.3.j.3.pwd.png)

In that output, we'll see that the full path to our working directory is `/home/codio/workspace`. This is the default location for all of our content in Codio, and its where everything shown in the file tree to the far left is stored. When working in Codio, we'll always want to store our work in this directory.

Next, let's use the `ls` command, short for "LiSt," to see a list of all of the items in that directory:

```tex
~/workspace$ ls
```

```tex
java  README.md
```

We should see a short list of items appear in the terminal. 

We can use the `cd` command, short for "Change Directory," to change the working directory. To change to the `java` directory, type `cd` into the terminal window, followed by the name of that directory:

```tex
~/workspace$ cd java
```

```tex
~/workspace/java$
```


We are now in the `java` directory, as we can see by observing the `~/workspace/java` on the current line in the terminal. Finally, we can do the `ls` command again to see the files in that directory:

```tex
~/workspace/java$ ls
```

```tex
HelloWorld.java
```

We should see our `HelloWorld.java` file! If it doesn't appear, try using this command to get to the correct directory: `cd /home/codio/workspace/java`. 

Once we're at the point where we can see the `HelloWorld.java` file, we can move on to actually compiling and running the program.

## Compiling in Terminal

To compile a Java program in the terminal, we'll use the `javac` command, short for _Java Compiler_, followed by the name of the Java file we'd like to compile. So, in our case, we'll do the following:

```bash
javac HelloWorld.java
```

If it works correctly, we shouldn't get any additional output. The compiler will look through our Java file and create a new file containing the Java bytecode for our program, called `HelloWorld.class`. We can use the `ls` command to see it:

```bash
ls
```

![javac Command Output](/images/01-oop/1.3.j.3.javac.png)

{{% notice warning "Problems?" %}}

If the `javac` command gives you any output, or doesn't create a `HelloWorld.class` file, that most likely means that your code has an error in it. Go back to the previous page and double-check that the contents of `HelloWorld.java` exactly match what is shown at the bottom of the page. You can also read the error message output by `javac` to determine what might be going wrong in your file.

We'll cover information about simple debugging steps on the next page as well. If you get stuck, now is a great time request help via your course's help system. You aren't in this alone!

{{% /notice %}}

## Running in Terminal

Finally, we can now run our program! Once it is compiled, just type the following in the terminal to run it:

```bash
java HelloWorld
```

![java Command Output](/images/01-oop/1.3.j.3.java.png)

That's all there is to it! We've now successfully compiled and run our first Java program. Of course, we can run the program as many times as we want by repeating the previous `java` command. If we make changes to the `HelloWorld.java` file, we'll need to recompile it using the previous `javac` command first. Then, if those changes instruct the computer to do something different, we should see those changes when we run the program after compiling it. 

{{% notice tip "Try It!" %}}

See if you can change the `HelloWorld.java` file to print out a different message. Once you've changed it, use the `javac` and `java` commands to compile and run the updated program. Make sure you see the correct output! 

{{% /notice %}}


## Codio Assessments

Last, but not least, many of the Codio tutorials and projects in this program will include assessments that we must solve by writing code. Codio can then automatically run the program and check for specific things, such as the correct output, in order to give us a grade. For most of these questions, we'll be able to make changes to our code as many times as we'd like to get the correct answer.