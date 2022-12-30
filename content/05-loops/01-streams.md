---
title: "Streams"
pre: "1. "
weight: 10
---

Both file and keyboard input are handled as streams.  Streams are a computer science abstraction for data that is organized in a queue.  Data (usually bytes) arrive over time, are ordered and read from first arrived to last arrived. This is similar to a conveyor belt.

![Conveyor Belt](/images/05-loop/5.conveyor.jpg)[^1]

[^1]: image from https://www.cleanpng.com/png-conveyor-belt-transport-logistics-conveyor-system-431096/

Some streams, like the keyboard, are "infinite".  When we type `dog<enter>` the keyboard stream (called `stdin` for "standard input") receives the bytes `[x64, x6F, x67, x0B]` ( bytes are typically written in their [hexadecimal](https://en.wikipedia.org/wiki/Hexadecimal) form). Once theses bytes are "read-out" of the stream, the stream does not close.  Rather it sits there empty until new data arrives.

Files from a disk drive are similarly read first byte to last.  Files are finite, and each language or operating system has a way of indicating the End Of File (EOF).  This is typically represented by the byte `x05` in Linux.

### Streams as Objects

Object oriented high level programming like Java and Python have built in stream classes.  These create stream objects and then read values from the object using built-in stream-object methods. Thus, with some minor set up differences, the commands to  read from a file are typically same the commands to read from the keyboard.  This is the power of abstraction -- the details of how to read from these different streams are hidden from the programmer who only wants read them.

Streams are literally bytes of data. We will use methods that interpret those byes as text, and then convert the text to the type of variable we need.

### Standard Streams

Most operating systems (operating systems handle the machine-code to hardware interface) make the following streams automatically available to a running program like the Java Virtual Machine or the Python interpreter.

* `stdin`  or standard input -- keyboard input
* `stdout` or standard output -- default screen or display for normal output
* `stderr` or standard error  -- default screen or display for error message output

These are legacy names from when terminals were connected to a computer.  A terminal is keyboard-screen device that contains no processors.  `stdout` and `stderr` typically display to the same device.

## Using the Keyboard

For the next several modules your programs will accept input for the keyboard stream.  Like command line arguments, data read from the keyboard is a string-type. So the typical flow will be:

1. Attach to the standard input stream
1. For each value
   1. Capture a stream-value as a string variable
   1. When required, convert the string to an appropriately typed variable

{{% notice info "Pseudocode" %}}

To represent the concept of user or file input, pseudocode uses `INPUT`.  Thus `x <- INPUT()` means get input from the user/file/whatever and assign it to the variable `x`.  Pseudocode generally abstracts away from (ignores) type.  You will rarely see type conversions in pseudo code.

{{% /notice %}}