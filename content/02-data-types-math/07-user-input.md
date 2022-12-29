---
title: "User Input in CC 210"
pre: "7. "
weight: 70
---

Most programs process some type of user input, whether through typed in text, mouse clicks or cut & paste.  In this class we are going to allow 3 types of user input:

1. Through command-line arguments
1. Through a file stream 
1. Through the keyboard stream


We are going to give the code that accesses the input right away, and will discuss nuances of the input type in more depth as we get to appropriate parts of the course.

{{% notice note "Hard Coding" %}}

Consider the code

```python
 x = 3
 y = 4
 z = x + y
 print (z)
```

Here the programmer has explicitly coded the values of `x, y, z`.  Because the user has no way to directly assign values to any of these variables, they are referred to as "hard coded." 

{{% /notice %}}

## Command Line Arguments

Today, this command line arguments are most often options for the program to follow at launch.  The `chrome` shortcut on my desktop actually just runs the console command 
`"C:\Program Files (x86)\Google\Chrome\Application\chrome.exe"`. 
But I could modify it to 
`"C:\Program Files (x86)\Google\Chrome\Application\chrome.exe" --incognito`,
and chrome would launch in incognito mode. The `--incognito` is a command line argument.


In this class, the command line we use typically consists of a launching program  (the command) and the name of the program to run. It can also have data which can be passed to the program.

``` text
$ <command> <program> <argument1> <argument2> ...
$  java Add 2 5
7
$  python3 Add.py 2 5
7
```
In both cases the program `Add` would run, and would be passed the strings: "2" and "5".  How this is coded will be covered in a few chapters, for now you just need to know how to pass arguments into you program.

### Common Properties of Command Line Arguments

There are some common properties of command line arguments you need to know.

1.  Arguments are passed in as strings. Programmers must convert them to the appropriate data types.
1.  Arguments are passed in order from left to right.  If your problem specification asks for a positive number then a negative number, you must provide them in that order. `java Program 2 -7` would be correct, `java Program -7 2` would be wrong.
1.  Arguments are separated by one or more spaces.
1.  There are ways for a program to tell how many arguments there are.

That's pretty much it.  User input can be provided on the command line in the form of string arguments (values).  When the command is run, these arguments are packed up by the operating system and given to the program.  When command line arguments are required (or optional), the problem statement will tell you their order and purpose.  The decision on whether or not to use command line arguments is typically a design consideration.

## Streams

Both file and keyboard input are handled as streams.  Streams are a computer science abstraction for data that is organized in a queue.  Data (usually bytes) are ordered and read from front to back.  You can see how this works for the keyboard.  When we type "dog" the keyboard stream (called stdin for "standard input") receives the bytes [100, 111, 103].  Files from a disk drive are similarly read first byte to last.

### Streams as Objects

Object oriented high level programming like Java and Python have built in classes that read values from a stream.  Thus, with some minor set up differences, the commands to  read from a file are typically exactly same  the commands to read from the keyboard.  This is the power of abstraction -- the details of how to read from these different streams are hidden from the programmer who only wants read them.

Streams are literally bytes of data. We will use methods that interpret those byes as text, and then convert the text to the type of variable we need.


