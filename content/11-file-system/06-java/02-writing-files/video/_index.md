---
title: "Java Write Files"
pre: "4.J. "
weight: 40
hidden: true
date: 2019-09-23T00:00:26-05:00
---

{{< youtube u0jr_oelbuc >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

Let's look at how we can write to files in Java. To do this, we'll use another class named BufferedWriter, which handles opening and writing to files.

First, we'll need to declare and initialize a new BufferedWriter object. Just like we did with file input, we can use a Try with Resources statement to do this, which will ensure that the file is properly closed when we are done with it. Outside of that statement, we'll add a catch block for a generic exception for now, but we'll revisit that in a bit.

With all of this code, we need to import several classes to make it work. We'll need to import the BufferedWriter class from java.io, the Files class from java.nio.file, and the Paths class, also from java.nio.file.

There! That gives us the basic structure we need to write to a file. In this program, we are getting the filename from the first command-line argument, but we could easily substitute that for any string that contains a path to a file.

To write to the file, we can just use the `write()` method of the `writer` object. It accepts only strings, unlike the `System.out.println` method we've been using to output text to the terminal. So, we'll need to make sure we convert any output to a string when writing it to a file.

However, by default, the `write()` method does not add a newline at the end of the output, so we can call a second method, `newLine()` to print a newline character to our file.

That's all there is to it! Writing to a file in Java is pretty simple. However, to make this program truly robust, there are a few exceptions we should catch and handle.

First, since we are reading the name of the file from the command-line arguments, we need to make sure we don't have an ArrayIndexOutOfBoundsException. Similarly, since we are using the Paths class, we can also check for an InvalidPathException.

In addition, any input and output operations could cause an IOException, so we'll need to add another catch statement for that.

Finally, opening a file for writing can cause one additional exception, the UnsupportedOperationException. This occurs when we are unable to open a file for writing for some reason, usually due to operating system restrictions. So, we can add one more catch statement for that exception as well.

This code gives a very simple example for writing output to a file. While it looks very complex, most of the program is simply code to handle the various exceptions that could occur when opening and writing to a file. See if you can get the example on this page to work!
