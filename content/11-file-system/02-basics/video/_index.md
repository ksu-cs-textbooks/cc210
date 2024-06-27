---
title: "File System Basics"
pre: "1. "
weight: 10
hidden: true
date: 2019-09-23T00:00:26-05:00
---

{{< youtube 0oHKtm7jMuo >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

In this chapter, we are going to learn all about how to manipulate files and directories using our programs. This is a very important part of programming, since many times we want to be able to save data for use later, or read and process existing data. If we know how to properly interface with the file system, we can do some really interesting things.

Before we begin, however, we need to cover some basic information about how files systems work on a modern computer. While you may be very familiar with storing and using files on your computer, many users never stop and think about what is going on behind the scenes.

For starters, most file systems today are structured like a tree. In Computer Science, a tree is a structure that contains nodes and branches, with the root node being shown at the top instead of the bottom. The nodes represent each directory or file, and the branches show the connections between them. Each directory can contain other directories, or files. A file would be a leaf node, since it cannot contain any other files or directories.

Also, we will use the term "directory" and "folder" interchangeably. They really refer to the same thing - a node in the tree that can contain child nodes, which are themselves either other directories or files.

Now, let's explore the filesystems of some common operating systems, just to get a feel for how these look in practice. On Windows, each drive or partition acts as a separate file system, so each one of those represents a root node on a tree. Inside, we see directories that contain our files. So, to find my files, we can open the `C:\` drive, followed by the `Users` folder, and finally my username.

One important thing to remember about Windows is that it uses a file extension to determine what the type of each file is. You may have them hidden by default, but they are easy to enable as well. You may be familiar with extensions such as PDF, DOCX, and JPG.

The Linux and Mac filesytems are similar. However, instead of each individual drive or partition being a separate file system, many times Linux and Mac computers use a virtual "root" filesystem, which each drive or partition besides the root partition contained within the root file system. Similarly, Linux includes directories and files. The major difference between Linux and Windows is how it determines the type of the file. Linux may also look at the file extension at the end of the filename, but it can also examine the contents of the file. Most major file types contain a special part at the beginning called a "file header" that identifies the type of the file. So, even if the file extension is missing or incorrect, many times Linux can determine the file type by examining the header.

Finally, let's look at the Codio filesystem. In many cases, you can find a representation of the filesystem to the left of the content. Since Codio is based on Linux, most of what we just discussed applies to Codio as well.

One important thing to notice is where the files in Codio are stored. Codio creates a special folder called the `workspace` folder, directly within the Codio user's home directory. So, the path `/home/codio/workspace` is where all of these files are located. Therefore, whenever we open a terminal, we'll have to be careful and make sure that we are in the correct directory before continuing. We'll show you how to do that in the next video.

Also, since Codio is based on Linux, we know that we don't have to worry about using the correct file extensions on our files. However, it is still a good practice to get into, as it helps us identify the types of files we are working with, and other programs besides Linux will still require those files to have the correct extensions.

There we go! That's a quick overview of file systems across a variety of systems. Next, we'll discuss a bit more specific information about navigating and using the Linux filesystem in Codio.
