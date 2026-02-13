---
title: "Input Streams"
pre: "6. "
weight: 60
---

Reading input from either the keyboard or a file are handled as streams. A stream is an abstract concept in computer science for data that is organized as a **queue**, where items that are added to the stream first are also the items that are read first. Put another way, when reading input from the keyboard, the program reads the keys in the order they are pressed. This is similar to a conveyor belt.

![Conveyor Belt](/images/05-loop/5.conveyor.jpg)[^1]

[^1]: image from https://www.cleanpng.com/png-conveyor-belt-transport-logistics-conveyor-system-431096/

Some streams, like the keyboard, are "infinite" and have no defined end.  When we type the characters `dog` followed by the <kbd>ENTER</kbd> key on the keyboard, the bytes `[x64, x6F, x67, x0B]` representing the ASCII characters `dog\n` are placed in the keyboard's input stream. Those bytes can then be read out of the stream by a program when it wants to receive keyboard input from the user. However, once those bytes are read, the stream does not close or end. Instead, it waits for new keyboard input to arrive from the user.

The process for reading files is similar. When the program opens a file, it can then read the bytes stored in the file from first to last until it reaches the end. Files, however, are "finite" meaning that they have a defined end. This is represented by a special ASCII character called the `EOF` or "End of File" character, represented by the byte `x05` in the stream.

### Streams as Objects

Programming languages such as Java and Python have many libraries and classes for working with streams. These classes are used to create stream objects that can read values from the stream using various methods. In this class, we've already seen this through the `Scanner` class in Java or the `input()` method in Python, which allow us to read input from the keyboard.

We can also read from files using many of the same methods. This is the power of abstraction in computer programming - if we can represent multiple items in a similar way, then we can write code that allows us to interact with either type of object.

Finally, the process of writing output to a file or to the terminal is also handled through streams. This allows us to both read and write from the same file or the terminal - we just use a stream to accomplish that!

### Standard Streams

Most operating systems make the following streams automatically available to any running program:

* `stdin` - this is the standard input stream that is used to receive input from the keyboard.
* `stdout` - this is the standard output stream that displays program output on the terminal to the user.
* `stderr` - this is the standard error stream that is used to present errors from the program.

In Java, these are available under the `System` class as `System.in`, `System.out` and `System.err`, respectively. We've already used the `System.out.println()` method many times to print output to the terminal, and we typically create a `Scanner` object that uses `System.in` to read input from the user. So, we've already used these streams many times in our programs!


