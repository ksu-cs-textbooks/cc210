---
title: "User Input"
pre: "7. "
weight: 70
---

Most programs process some type of user input, either text input by the user, mouse clicks on the screen, or many other methods. In this course, we'll typically deal with three different types of user inputs:

1. Command-line arguments
1. Reading from a file stream
1. Reading from the keyboard stream

For the first few chapters, we'll go ahead and provide the code needed to handle and process user inputs. As we learn more, we'll go deeper into detail about each method and discuss the nuances involved with reading and processing user input.


{{% notice note "Hard Coding" %}}

Consider the code

```java
 int x = 3
 int y = 4
 int z = x + y
 print (z)
```

Here the programmer has explicitly coded the values of `x`, `y`, and `z`.  Because the user has no way to directly assign values to any of these variables, they are referred to as "hard coded." However, programs that contain only hard-coded values are not very useful since they don't respond to any input from the user. So, in most cases, our programs will include some sort of user input instead of hard-coded values.

{{% /notice %}}

## Command Line Arguments

Command-line arguments are pieces of data that are provided to the program when executed as part of the initial command. For example, we learned that we can run a basic Hello World program using a command similar to these:

```bash
# Java
java HelloWorld
```

```bash
# Python
python3 HelloWorld
```

We can provide a command-line argument to these programs by including them after the command. For example, we could re-write our program to make user of the user's name when provided as the first command-line argument. In that case, we can use the following command to run our program:

```bash
# Java
java HelloWorld Willie
```

```bash
# Python
python3 HelloWorld Willie
```

In this example, `Willie` is the input provided as the first command-line argument. We can change that to be any value we want. 

### Common Properties of Command Line Arguments

There are some common properties of command line arguments we should be aware of

1.  Arguments are passed in as strings. Programmers must convert them to the appropriate data types.
1.  Arguments are passed in order from left to right.  If a problem specification asks for a positive number then a negative number, we must provide them in that order.
1.  Arguments are separated by one or more spaces.
1.  There are ways for a program to tell how many arguments there are.

That's pretty much it.  User input can be provided on the command line in the form of string arguments (values).  When the command is run, these arguments are packed up by the operating system and given to the program.  When command line arguments are required (or optional), the problem statement will tell us their order and purpose.  The decision on whether or not to use command line arguments is typically a design consideration.

## Streams

Both file and keyboard input are handled as streams.  Streams are a computer science abstraction for data that is organized in a queue.  Data (usually bytes) are ordered and read from front to back.  We can see how this works for the keyboard.  When we type "dog" the keyboard stream (called `stdin` for "standard input") receives the bytes [100, 111, 103].  Files from a disk drive are similarly read first byte to last.

### Streams as Objects

Object oriented high level programming like Java and Python have built in classes that read values from a stream.  Thus, with some minor set up differences, the commands to read from a file are typically exactly same as the commands to read from the keyboard.  This is the power of abstraction -- the details of how to read from these different streams are hidden from the programmer who only wants read them.

Streams are literally bytes of data. We will use methods that interpret those byes as text, and then convert the text to the type of variable we need.

We'll learn more about reading data from the keyboard and from a file later in this course.


