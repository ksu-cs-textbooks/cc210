---
title: "File System Commands"
pre: "4. "
weight: 40
---

{{% youtube Sx9Tr9_-nhs %}}

[Video Materials]({{<relref "./video">}})

Lastly, let's take a look at some helpful commands we can use on the terminal to manipulate the file system in Linux. We can open the terminal in Codio by clicking the **Tools** menu at the top of the page, then selecting **Terminal**. It should already be open in the panel to the left for this example. 

When we open the terminal, it should look something like the picture below. If we see that, we're ready to go.

![Linux Terminal Screenshot](/images/11-file/terminal.png)

## Command Prompt

When we open a Linux terminal, we'll see quite a bit of helpful information before we even type in a single command. In the screenshot above, the terminal's _command prompt_ is the line of text right before the cursor:

```tex
codio@rainbow-almond:~/workspace$
```

Let's look at what each part means:

* `codio` - The first part, before the at symbol `@`, gives the currently logged-in user name. When using Codio, we'll almost always be logged-in using the `codio` username.
* `@rainbow-almond` - The next segment, between the at symbol `@` and the colon `:` is the _host name_ of the system we are using. Codio assigns hostnames using two random words, in this case "rainbow" and "almond". We won't really need this information right now, but it will become useful in future courses. 
* `~/workspace` - Following the colon is the path of the _present working directory_ or _pwd_ for short. This is the directory we are currently in. 
* `$` - The last character is a dollar sign `$`. It is used to signify that we are not on an _elevated_ terminal, which would have administrator permissions. If we were on an elevated terminal, it would be a hash symbol `#` instead. 

As we can see, the command prompt gives quite a bit of important information at a glance!

## Print Working Directory

At any time, we can see our _working directory_ one of two ways:

1. It is always present in the command prompt on most Linux terminals as described above.
2. We can use the `pwd` command (short for "Print Working Directory") on the terminal.

Let's try the second option. On a terminal, we can type `pwd` and press enter. It should look something like this:

![Present Working Directory Screenshot](/images/11-file/pwd.png)

When we enter that command, the next line will show us our current working directory. However, notice that it printed `/home/codio/workspace` instead of the `~/workspace` that we see in the command prompt. This is because Linux uses several special characters in a _path_ as shortcuts. So, let's cover that before we move on.

## Special Path Characters

As we discussed earlier, the Linux file system uses a hierarchical path to show the location of directories and folders. However, sometimes those paths can be very complex, and it is a pain to type them out in full each time we want to use them. So, there are a few special rules and characters that apply to Linux paths.

1. If a path begins with a slash `/` character, the path is said to be an _absolute_ path. That is because it starts at the root of the file system, and gives the name of each directory along the path. If it does not begin with a slash, then the path is a _relative_ path, because it is relative to our present working directory and could have different meanings depending on which directory we are starting from.
1. If a path begins with a tilde and a slash `~/`, the path is relative to our _home directory_. So, the path `/home/codio/workspace` and `~/workspace` are the same, provided our current username is `codio`. 
1. If a path begins with a period and a slash `./`, the path is relative to our _present working directory_. So, if our _pwd_ is `/home/codio`, then the path `./workspace` is the same as `/home/codio/workspace`. 
1. If a path begins with two periods and a slash `../`, the path is relative to the _parent directory_ of our present working directory. So, if our _pwd_ is `/home/codio/workspace`, the path `../` would be the same as `/home/codio`. 

There are a few other special characters that can be used, but these are the ones that we'll see most often.

{{% notice tip "Chaining Paths" %}}

It is also possible to chain paths together using several of these special characters. For example, if our _pwd_ is `/home/codio/workspace`, the path `../../` would be `/home`, and `../../../` would be just `/`. 

Similarly, we can chain them together in ways that may seem nonsensical, such as `~/../../././home/codio/../codio/workspace`, which is the same path as `/home/codio/workspace`. 

In general, we won't need to use these complex paths very often if at all. However, it is helpful to know that it can be done. 

{{% /notice %}}

## Listing Contents

Next, we can list the contents in a directory using the `ls` command. Let's go ahead and enter that next on our terminal:

![ls Screenshot](/images/11-file/ls.png)

Assuming we are still at the `/home/codio/workspace` directory, we should see output similar to the screenshot above. Of course, many files have been added to this book since that screenshot was made, so it may be different now. In that screenshot, we see some interesting things:

1. Any entries that are blue represent _directories_ that can be opened. They may contain additional files or directories, or they may be empty.
1. Entries in white are _files_ that can be opened

Since it is difficult for some people to see those colors, we can also use the `ls -l` command to show more information:

![ls -l Screenshot](/images/11-file/lsl.png)

This gives us quite a bit more information about each directory or file. Here's a helpful diagram from DigitalOcean showing what each column contains:

![ls -l Diagram from Digital Ocean](/images/11-file/lsl_do.png)[^2]

[^2]: Image Credit: An Introduction to Linux Permissions from Digital Ocean https://www.digitalocean.com/community/tutorials/an-introduction-to-linux-permissions]

Another important aspect is the first character in the mode column, which gives the _type_ of the entry:

1. If that character is a `d`, the entry is a _directory_
1. If that character is a dash `-`, the entry is a _file_

There are a few other characters that could appear there, but we won't discuss them now. 

## Changing Directories

Once we've seen what a directory contains, we may want to open another directory and view its contents. To do that, we can use the `cd` command, followed by the _path_ that we'd like to visit. It could be an _absolute path_ or a _relative path_. For example, let's assume we are in the `/home/codio/workspace` directory. From there, we'd like to get to the directory `/home/codio/workspace/1j-hello`, which is contained in the present working directory. Each of the screenshots below gives an example of how we could accomplish that:

![Relative Path Screenshot](/images/11-file/rel.png)
![Relative Home Path Screenshot](/images/11-file/relhome.png)
![Relative Dot Path Screenshot](/images/11-file/dot.png)
![Absolute Path Screenshot](/images/11-file/abs.png)

So, it is very simple to use the `cd` command to move around the file system.

{{% notice note "Autocomplete" %}}

Tired of always having to type in complex folder names and commands in Linux? Thankfully, most Linux terminals, including the one in Codio, support _tab completion_ of commands and paths. Just start typing the first few characters of a command or part of a path, then press the **TAB** key to try and autocomplete it. If there is only one possible completion of that element, the Linux terminal will fill it in for you. 

If it is not unique, you can press **TAB** twice to see all possible ways that the command or path could be completed. This shortcut is one of the many ways a Linux power user gets around the terminal so quickly. It is definitely a trick worth learning!

{{% /notice %}}

## Other Commands

There are several other useful Linux terminal commands that we may need to use from time to time. Most of these commands can also be accomplished using the Codio file tree.

* `mkdir <path>` - make a new directory
* `touch <file>` - create a new blank file or update the last modified time of an existing file
* `cat <file>` - print a file's contents to the terminal
* `cp <source> <destination>` - copy a file or directory from the source to the destination. Use `cp -r` to make it _recursive_, where it will copy all of the contents inside of a directory as well. 
* `mv <source> <destination>` - move a file or directory from the source to the destination. This is very similar to _renaming_ a file or directory.
* `rm <file>` - remove (delete) a file
* `rmdir <directory>` - remove (delete) an empty directory

That's just a small sample of the many commands available on a Linux terminal. For more detailed information, feel free to check out this great video tutorial.

{{% youtube oxuRxtrO2Ag %}}
