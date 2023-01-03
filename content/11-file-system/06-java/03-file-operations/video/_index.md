---
title: "Java File Operations"
pre: "5.J. "
weight: 50
hidden: true
date: 2019-09-23T00:00:26-05:00
---

{{< youtube gAAiv1Hbafc >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

Let's look at some of the more useful operations we can perform on files using Java.

In this example code, we're using the `Paths.get()` method to create a Path object representing a path on our file system. It may be an existing directory or file, or it could be something that doesn't exist. We'll see how check for that later in this video.

Of course, since we are dealing with Paths, we should check for both an InvalidPathException, as well as an IOException. So, we've added a couple of catch statements here to deal with those exceptions.

We're also importing the Files class from java.nio.file, which will give us access to some helpful methods. We aren't using it in this starter code, but we'll see it appear several times later in this video.

Finally, all the code on the following slides can be placed where this "more code goes here" comment is in the starter code. This helps make it a little easier to read the code on the following slides.

First, we may want to know what type of thing that path is pointing at. So, we can use methods from the Files class, such as `exists()`, `isDirectory()` and `isRegularFile()` to answer those questions. Each of these methods returns a Boolean value, either `true` or `false`, depending on what the `pathObject` is referencing.

If it is a file, we can use the `Files.size()` method to see how big the file is in bytes. However, if we try to do this on a directory or a path that doesn't exist, we could get an IOException. So, it is always a good idea to check if the item exists and is a regular file before calling this method.

What if we want to copy a file or move it to a new location? Thankfully, there are methods just for that. The Files class includes both a `copy()` and `move()` method, which accepts two Path objects as the source and destination parameters. Thankfully, if we try to copy or move an item onto an existing path, we'll get an exception by default. You can read the Java documentation to learn how to disable that exception and overwrite existing files or directories if you'd like.

Of course, we can also delete an item using the `delete()` method of the Files class. When doing this on a directory, we'll need to make sure the directory is empty before we try to delete it, otherwise we'll get a DirectoryNotEmptyException.

Finally, if needed, we can also directly create files or directories using the `createFile()` and `createDirectory()` methods. Once again, if something already exists at that path, it will throw an exception.

As we can see, there are lots of ways we can use Java to explore and manipulate both files and directories on our system. On this page you'll create a quick example program to try some of these methods yourself. See if you can get it to work!
