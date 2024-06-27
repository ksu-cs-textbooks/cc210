---
title: "Running the Program"
pre: "3. "
weight: 30
---

{{< youtube 8Qb_1LaOh3c  >}}

<!-- TODO Update Video -->
<!-- OLD [Video Materials]({{% relref "./video" %}}) -->
<!-- TODO Update Screenshots -->

Now that we've written our first Python program, we must run the program to see the fruits of our labors. 

## Terminal

Codio includes a built-in Linux terminal, which allows us to perform actions directly on a command-line interface. We can access the Terminal in many ways:

1. Selecting the **Tools** menu, then choosing the **Terminal** option
1. Pressing SHIFT + ALT + T in any Codio window (you can customize this shortcut in your Codio user preferences)
1. Pressing the **Open Terminal** icon in the file tree

Additionally, some pages may already open a terminal window for us in the left-hand pane, as this page so helpfully does. As we can see, we're never very far away from a terminal.

{{% notice info "New to Linux?" %}}

No worries! We'll give you everything you need to know to run your Python programs in this course.

If you'd like to learn a bit more about the Linux terminal and some of the basic commands, feel free to check out this great video on YouTube:

{{< youtube oxuRxtrO2Ag  >}}

<p style ="color:red">Note: CC-210 requires no  more Linux knowledge than CC-110.</p>

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

In that output, we'll see that the full path to our working directory is `/home/codio/workspace`. This is the default location for all of our content in Codio, and it's where everything shown in the file tree to the far left is stored. When working in Codio, we'll always want to store our work in this directory.

Next, let's use the `ls` command, short for "LiSt," to see a list of all of the items in that directory:

```bash
ls
```

![ls Command Output](/images/01-oop/1.3.j.3.ls.png)

We should see a whole list of items appear in the terminal. Most of them are directories containing examples for the chapters this textbook, including the `HelloWorld.py` file that we edited in the last page. Thankfully, the directories are named in a very logical way, making it easy for us to find what we need. For example, to find the directory for Python examples, look for the directory named `python` in the output.  

Finally, we can use the `cd` command, short for "Change Directory," to change the working directory. To change to the `python` directory, type `cd` into the terminal window, followed by the name of that directory:

```bash
cd python
```

```tex
:~/workspace$ cd python
~/workspace/python$ 
```

We are now in the `python` directory, as we can see by observing the `~/workspace/python` on the current line in the terminal. Finally, we can do the `ls` command again to see the files in that directory:

```bash
ls
```


```tex
~/workspace/python$ ls
HelloWorld.py
```


We should see our `HelloWorld.py` file! If it doesn't appear, try using this command to get to the correct directory: `cd /home/codio/workspace/python`. 

Once we're at the point where we can see the `HelloWorld.py` file, we can move on to actually running the program.

## Running in Terminal

To run it, we just need to type the following in the terminal:

```bash
python3 HelloWorld.py
```


```tex
~/workspace/python$ python HelloWorld.py
Hello World!
```

That's all there is to it! We've now successfully run our first Python program. Of course, we can run the program as many times as we want by repeating the previous `python3` command. If we make changes to the HelloWorld.py file that instruct the computer to do something different, we should see those changes the next time we run the file.. 

{{% notice warning "Problems?" %}}

If the `python3` command doesn't give you any output, or gives you an error message, that most likely means that your code has an error in it. Go back to the previous page and double-check that the contents of `HelloWorld.py` exactly match what is shown at the bottom of the page. You can also read the error message output by `python3` to determine what might be going wrong in your file.

Also, make sure you use the `python3` command and not just `python`. The `python3` command references the newer Python 3 interpreter, while the `python` command is used for the older Python 2 interpreter. In this book, we'll be using Python 3, so you'll need to always make sure you use `python3` when you run your code.

We'll cover information about simple debugging steps on the next page as well. If you get stuck, now is a great time to go to you can use the course discussion forums or email list to ask for assistance. You aren't in this alone!

{{% /notice %}}

{{% notice tip "Try It!" %}}

See if you can change the `HelloWorld.py` file to print out a different message. Once you've changed it, use the `python3` command to run the file again. Make sure you see the correct output! 

{{% /notice %}}

## Codio Assessments

Last, but not least, many of the Codio tutorials and projects in this program will include assessments that we must solve by writing code. Codio can then automatically run the program and check for specific things, such as the correct output, in order to give us a grade. For most of these questions, we'll be able to make changes to our code as many times as we'd like to get the correct answer. Try the example below! 

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}
