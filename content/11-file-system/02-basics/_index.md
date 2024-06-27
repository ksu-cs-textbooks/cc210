---
title: "File System Basics"
pre: "2. "
weight: 20
---

{{< youtube 0oHKtm7jMuo  >}}

[Video Materials]({{% relref "./video" %}})

Before we start learning how to manipulate files and directories, we should cover some basic concepts related to how computers today deal with data.

![File System Tree](/images/11-file/dirtree_oracle.gif)[^1]

[^1]: Image Credit: Oracle Java Tutorials: What is a Path? https://docs.oracle.com/javase/tutorial/essential/io/path.html

{{% notice info "Trees & Nodes" %}}

In this chapter, we'll use a few terms that may be unfamiliar. So, let's review those now:

* **node**: A _node_ is a single element in a data structure. It is usually represented by a circle or box, and may be connected to other nodes in the data structure using lines. 
* **root**: The single _node_ at the top of a _tree_.
* **tree**: A _tree_ is a hierarchical data structure used in computing. A tree typically consists of a single node at the top, and then one or more nodes connected to each node, usually shown in successive layers of depth. When displayed, they typically look like an upside-down tree, with the trunk at the top and branches growing downwards.  The reason trees are drawn upside down, with the root at the top, has been lost to antiquity. 

So, in the diagram above, the entire diagram shows a _tree_ data structure, with each box representing a _node_ of the data structure. 

{{% /notice %}}

## File System

The _file system_ on a modern computer can be thought of as the topmost node in a tree that represents all of the data stored on a storage device. Each hard drive, flash drive, or other storage device on a computer contains at least one _partition_, and inside of that partition is a _file system_ that stores files. Of course, storage devices may contain many different partitions, each with a different file system, but that is becoming less common since storage is much cheaper than it used to be.

In the diagram at the top of this page, the topmost box represents the file system's root node. 

On a Windows system, the root node of each file system is represented by a drive letter. Typically the main file system uses the `C:\` drive letter.

On OS X and Linux-based systems, the file system begins with a root node that has the path `/`. Under that root node, additional file systems can be mounted on a unique path, usually in a special directory such as `/mnt` or `/media`. We'll take a closer look at the Linux file system on the next page.

## Directory

Within a file system, data is typically separated into a hierarchical structure using _directories_ or _folders_. Just like we would use folders in a file cabinet to group similar papers together, we can do the same with directories on our file systems. 

In the diagram at the top of this page, the boxes for "home", "user2", and "foo", among others, all represent directories that can store data within them.

Each directory is represented by a _path_, such as `C:\Users\user\Documents` on Windows or `/home/user/documents` on Linux. 

## File

Each individual piece of data stored on a file system is represented by a _file_. Those files can store many different types of data, from simple text and graphics to entire programs and videos. 

As with directories, each file is also represented by a _path_, such as `C:\Users\user\Documents\file.txt` on Windows or `/home/user/documents/file.txt` on Linux. 

## File Extensions

Most file names include an optional extension at the end. The extension comes after the last period `.` character in the filename, and consists of a few characters giving information about the type of data in the file. Some common file extensions include `.txt`, `.docx`, `.pdf`, and `.mp3`. 

Most Windows computers automatically hide these extensions from view, since Windows actually uses those extensions to determine the type of data that is stored in the file. Linux, on the other hand, uses a different system that involves looking inside the file itself, so the extension is not necessary (but helpful). 

## Symbolic Link

Most file systems support _symbolic links_ or _symlinks_, sometimes incorrectly referred to as _shortcuts_. A symbolic link allows one file path to refer to another, so they both appear to contain the same information.

For example, we could create a symlink at `/home/users/documents` that points to the directory `/data/documents`. So, whenever a user opens the `/home/users/documents` directory, they will actually see the files stored in `/data/documents`. Any changes made to those files will be visible to users who view the files using either path. 

We won't deal with symlinks in this chapter, but they are something to be aware of, as we may come across them when working with file systems in practice. 