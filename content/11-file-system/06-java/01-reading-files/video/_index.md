---
title: "Java Read Files"
pre: "3.J. "
weight: 30
hidden: true
date: 2019-09-23T00:00:26-05:00
---

{{< youtube y6vTrInbR1I >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

To read files using Java, we've been using some simple starter code. The code shown here is pretty much exactly what we saw in an earlier chapter on exception handling.

This starter code is using the `java.io.File` library to open files for reading. That library has been included in Java for quite some time, and is typically the first one students learn when reading from files.

However, more recent versions of Java have included a much more robust library for reading files, called the `nio` library, short for "non-blocking I/O". So, let's adapt this code a bit to use the new `nio` library.

First, we'll need to change the import statement at the top of the program to `java.nio.file.Paths`. This is because the `nio` library primarily works with `Path` objects instead of `File` objects, since `Path` objects can refer to both files and directories. Similarly, we'll change the code inside of the scanner to use the `Paths.get()` method instead of creating a new `File` object. Thankfully, the `Scanner` library can use either one interchangeably, so we don't have to change anything else.

Now that we are using `nio` libraries, we'll have to update our exception handlers a bit. First, when the file can't be found, instead of a `java.io.FileNotFoundExeption`, we could now receive a `java.nio.file.NoSuchFileException`. So, we'll update that import statement, as well as the catch statement for that exception.

In addition, the `Paths.get()` method could also throw a `java.nio.file.InvalidPathException` if the path we provide is invalid for some reason. So, we'll need to add one more catch statement for that exception as well.

There we go! We've updated our starter code to use the new Java `nio` library. Notice that this code will only read from the terminal if no arguments are provided. If we provide a command-line argument that causes an exception, this code will print an error and end the program. Most of the programs in this chapter and beyond use this behavior, since we really want to make sure we are reading input from a file instead of the terminal when we provide one as input, even if it causes an error.

Inside of the **Try with Resources** statement, we can use the `Scanner` object just like we have in our previous programs. Nothing else has really changed there. See if you can complete the sample program on this page to confirm that your new starter code is working properly.
