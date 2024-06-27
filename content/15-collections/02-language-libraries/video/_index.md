---
title: "Libraries"
pre: "1. "
weight: 10
hidden: true
date: 2019-12-6T00:00:26-05:00
---

{{< youtube NbtO47zpfFU >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

In this module, we'll spend some time learning about libraries and how we can use them in our code.

If we think of the term library, we probably think of these large public spaces that store books. Those books make vast amounts of information available at our fingertips, allowing us to leverage the work of prior generations and build upon it in our own work.

Software libraries work in a similar way. They are simply pieces of code that have been written by someone else that we can use in our programs. In most cases, software libraries are designed to handle many of the common tasks our programs may perform, such as reading from files, manipulating data, or even communicating across the internet. In this example, we have written a program that needs to play an Ogg Vorbis file, which is a media file format. Instead of writing all the code to read and interpret an Ogg Vorbis file directly in our program, we can simply use a few libraries that have been developed for that specific purpose. In our code, we can just call methods within that library to perform the actions we need, and it makes our program much simpler and easier to develop. In addition, if there is a new version of the Ogg Vorbis library released, we can usually use it in our code directly without any modification. It is a very handy way to build a program.

Most programming languages have large software libraries available for our use. We typically refer to the libraries included with the language itself as the "standard library" for that language. For example, here is a diagram showing the structure of the Java platform, containing all of the standard libraries and tools included with the language. Notice toward the bottom of the diagram we see things such as "Input/Output", "Math," and "Collections," which are libraries that we'll be using in our programs in this module.

Python also includes a large number of things in its standard library. This is one diagram that attempts to show the entire structure of dependencies between each part of the Python standard library.

If we zoom in a bit, we'll see libraries such as "abc," "io,", and "collections", which are libraries we are going to be using in this module as well.

In fact, many programming languages include quite a few common features in their standard libraries, including utilities for working with strings, files, data structures, networking, and so much more. Later in this chapter, we'll find links to the documentation for our chosen programming language's standard library. It is a great place to look for tools that we can use when writing our own programs!
