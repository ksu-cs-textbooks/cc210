---
title: "File System Commands"
pre: "2. "
weight: 20
hidden: true
date: 2019-09-23T00:00:26-05:00
---

{{< youtube Sx9Tr9_-nhs >}}

#### Video Script

Let's review some of the important concepts and commands you'll want to know when working with the Linux file system in Codio. Some of this material may be review, but it is helpful to have a quick refresher before starting the programming portion of this chapter.

In Codio, we can open a Terminal in several ways. We can choose the Terminal option from the tools menu, the Terminal button above the file tree, and the Open Terminal option in the Run menu. Any one of those options will get us to the terminal.

Once there, we'll be greeted with the standard Linux command prompt. This gives us several important pieces of information. First, we see our current username, which is `codio`. After that, there is an at `@` symbol, and then the name of the Codio box we are using. Codio boxes are given unique two-word names. In this case, it is blah blah.

Next, we have a colon `:`, and then following that we see the path of our working directory, `~/workspace`. By default, most times the Codio terminal will automatically open to the `workspace` directory inside of the home folder, which is where all of our files and work will be placed anyway.

Finally, we see a dollar sign `$`. That dollar sign indicates that we are using a standard terminal. The other symbol we might see there is a pound sign or hash symbol `#`, which indicates that we are using an administrative terminal as the `root` user. For Codio, that really doesn't matter, but on a real Linux system, it means that any commands you run have the permissions of the `root` user, which means you can install and configure software, but also accidentally break things without warning.

Next, let's review some important commands that we can use to navigate the file system in Linux. First, we can use the `pwd` command to print our working directory. In this case, it will print `/home/codio/workspace`, which is the directory our terminal is currently using.

Earlier, we said that we were in `~/workspace`, but the `pwd` command gives us `/home/codio/workspace`. So, why is that? It turns out that the tilde character `~` is one of the special characters we may see in Linux. In this case, it stands for the home directory of the current user. So, for the user named `codio`, that path would be `/home/codio`. In fact, on most Linux systems, we can find all user's home directories in the `/home` directory.

Once we know where we are, we may want to see what files are contained in that directory. So, let's use the `ls` command to list the files in this directory. When we run this command inside of the Codio textbook, we see folders for a number of chapters in this book.

If we want to see more details, we can use the `ll` command to get a long listing of the contents. This will show information such as the permissions, owner, groups, size, and last modified time of each of those files. We won't go into too much detail about any of that information in this course, but it's useful to know.

We can also use the `la` command to list all files in a directory, including hidden files. On Linux, any file or directory whose name begins with a period or dot `.` is hidden from the user by default. We can show those files using the `la` command.

Of course, if we want to have a long listing of those files, we can use the `ls -al` command to combine both commands in one.

Next, we may want to change our current working directory to another directory. To do this, we can use the `cd` command, followed by the path to a directory that we'd like to open. For example, if we want to open the `9p-files` directory, which is used for this chapter, we can type `cd 9p-files` to open that directory

Of course, if we want to make things even easier, Linux supports tab completion. So, as we type the name of a directory or file, we can use the <kbd>TAB</kbd> key to autocomplete it. Let's try that with the folder we just opened.

We can also enter full paths with the `cd` command, such as `cd /home/codio/workspace` to get back to the workspace folder. We can even use `cd ~/workspace` to get there too.

There are two other special directory paths we should be aware of. The first is a single period, which represents the current working directory. So, if we do `cd .`, we won't go anywhere. However, if we want to refer to a file or directory in our current directory, such as the `9p-files` directory, we can use `cd ./9p-files` to get there. This becomes really useful if we need to run a script or executable inside of our directories, but we won't worry about that in this course.

The other special directory path is two periods, or `..`, which refers to the parent of the current working directory. For example, if we are in the `9p-files` directory, we can use `cd ..` to go to the parent directory, which is the `workspace` directory. We can even chain them together, so by doing `cd ../../..` from here, we'll get to the root of our filesystem!

Now that we are comfortable moving around, let's review a few other commands that we can use to manipulate the filesystem in Codio. First, we can use the `mkdir` command to make a new directory. Let's do that now, making a new `test` directory in our `workspace` directory. Once we've done that, we can use `cd workspace` to get into that directory. Notice how I can type the first few letters of the directory, then press the <kbd>TAB</kbd> key to autocomplete the rest of the path. Once you get comfortable using tab completion, you'll use it all the time.

Inside of that directory, we can create a new file using the `touch` command. Let's create a file named `file.txt`, so we'll use `touch file.txt`. The `touch` command actually is used to update the last modified date of a file, but it can also create a file if one doesn't exist.

Now that the file exists, we can open it in Codio and add some contents. Unfortunately, there isn't a good way to open the visual Codio editor from the terminal, so you'll have to find the file in the file tree to the left and double-click on it there. Let's do that, and add some content. If you aren't able to see it, you may have to close the Codio guide to get access to the full file system.

Once we've created a file and added some content, we can print the contents using the `cat` command. So, let's type `cat file.txt` and see what happens. Again, the `cat` command is actually designed to concatenate many files to the terminal, but it can be used to print just a single file as well.

Next, we can use the `cp` command to copy a file or directory. To make a copy of a file, simply type the `cp` command, followed by the name or path of the file to be copied, and then the name or path of the destination. So, if we do `cp file.txt new.txt`, we'll create a new file called `new.txt` that contains the same content as `file.txt`. We can use the `cat` command to make sure the contents are the same.

If we exit the `test` directory, we can also use the `cp` command to copy entire directories. However, when we do that, we must use the `-r` option, which stands for recursive. This will allow `cp` to copy both the directory and its contents. So, we'd type `cp -r test newtest` to create a new folder called `newtest` that contains copies of the files in `test`. We can use the `cd`, `ls` and `cat` commands to confirm that everything worked like we want.

We can also use the `mv` command to move a file, either by giving it a new name, or an entirely new path. For example, from the `newtest` directory, we can use `mv new.txt second.txt` to rename the file `new.txt` to `second.txt`.

If we want to move a file to another directory, we can give a new path as the last part of the command. So, for example, if we want to move the file `second.txt` back to the `test` directory we created earlier, we can use `mv second.txt ../test/`. This command is a bit complex. We used the special path `..` to reference the parent directory, then the `test` name to get into the `test` directory contained in that parent directory. Since we left off the file name and ended the path with a slash `/`, it will know to use the same file name. If we run `ls` now, we'll see that the file `second.txt` has disappeared! But, if we use `cd ../test` to get to that directory, and then `ls` to see that the file has moved as we intended.

Of course, we can also use the `mv` command to move entire directories in the same fashion. Thankfully, we don't even have to include any special options if we are moving entire directories.

Lastly, we can use a couple of different commands to delete files and directories we've created.

If we enter our `newtest` directory, we see that there is just one file remaining. `file.txt`. To delete it, we can use the `rm` command, as in `rm file.txt`.

Now that we've deleted all of the contents in this folder, we can use `cd ..` to go to the parent directory. Then, we can use the `rmdir` command to delete that directory completely by typing `rmdir newtest`.

However, it is important to note that we can only delete directories that are already empty. If we try to do `rmdir test`, we'll get an error message that the directory is not empty. If we want to delete that directory and all of its contents, we can use the command `rm -r test` instead. Once again, the `-r` option stands for recursive, which means that it will delete everything in the directory before deleting the directory itself.

There we go! We've explored quite a few of the commands we can use to manipulate the Linux file system. Of course, most of these operations can also be performed graphically in the Codio file tree to the left side of the window. Most of those operations should be pretty self-explanatory as well. From here, we'll start learning how to manipulate files and directories from within our programs.
