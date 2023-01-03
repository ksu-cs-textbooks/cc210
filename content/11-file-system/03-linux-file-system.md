---
title: "Linux File System"
pre: "3. "
weight: 30
---

The Codio programming environment uses the Linux file system to store files and directories. So, let's take a minute and discuss some features specific to the Linux file system.

## Layout

![Linux File System Layout](/images/11-file/unix_wiki.svg)[^1]

[^1]: File:Standard-unix-filesystem-hierarchy.svg. (2016, November 27). Wikimedia Commons, the free media repository. Retrieved 20:45, April 18, 2019 from https://commons.wikimedia.org/w/index.php?title=File:Standard-unix-filesystem-hierarchy.svg&oldid=221696273.

As we discussed earlier, the Linux file system begins with a single root node which has the path `/`. Below that root node, there are several directories which are typically present on each Linux system. The diagram above gives information about what could be found in each of those directories. 

## Home Directory

On Linux, each user is assigned a _home directory_ where they can store all of their files. Those directories are typically stored in the `/home` directory. So, a user with the username `codio` could find their files in the `/home/codio` directory.

The Codio programming environment does indeed use the `codio` username by default. So, all of our files can be found in the `/home/codio` directory.

## Workspace

In addition, Codio specifically uses a particular subdirectory of the home directory, named `workspace`, to store all of the files used by the Codio development environment. So, any files we see in the file tree on the left side of the window are actually stored in the `/home/codio/workspace` directory. When we open a terminal window in Codio, that is the directory we will be taken to by default. 

## Hidden Files

On Linux, any file or directory name that begins with a period `.` is hidden from view by default. So, we must be careful not to accidentally add a period to the beginning of any file or directory name, or else we may not be able to see it. On the next page, we'll learn some handy terminal commands we can use to see those files. 

### Further Reading

* [The Linux Filesystem Explained](https://www.linux.com/blog/learn/intro-to-linux/2018/4/linux-filesystem-explained) from Linux.com
* [About Files and the File System](https://www.tldp.org/LDP/intro-linux/html/chap_03.html) from The Linux Documentation Project