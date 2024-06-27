---
title: "Python Write Files"
pre: "4.P. "
weight: 41
hidden: true
date: 2019-09-23T00:00:26-05:00
---

{{< youtube iGPn_vMqZlY >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

Let's look at how we can write to files in Python. To do this, we simply have to open a file using the `open()` function just like we do to read a file. We can use a Try-Except statement with a With statement inside, which will ensure that the file is properly closed when we are done with it. Outside of that statement, we'll add an except block for a generic exception for now, but we'll revisit that in a bit.

In this case, however, we provide a second argument to the `open()` function, "w", which tells the system that we'd like to write to that file.

There! That gives us the basic structure we need to write to a file. In this program, we are getting the filename from the first command-line argument, but we could easily substitute that for any string that contains a path to a file.

To write to the file, we can just use the `write()` method of the `writer` object. It accepts just about any writable data type, just like the `print()` function we've been using to output text to the terminal.

However, by default, the `write()` method does not add a newline at the end of the output, so we'll have to manually add the newline characters to our file where we'd like them.

That's all there is to it! Writing to a file in Python is pretty simple. However, to make this program truly robust, there are a few exceptions we should catch and handle.

First, since we are reading the name of the file from the command-line arguments, we need to make sure we don't have an IndexError.

In addition, any input and output operations could cause an IOError, so we'll need to add another except statement for that.

This code gives a very simple example for writing output to a file. While it looks very complex, most of the program is simply code to handle the various exceptions that could occur when opening and writing to a file. See if you can get the example on this page to work!
