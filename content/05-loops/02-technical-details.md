---
title: "Streams - Technical Details"
pre: "2. "
weight: 20
---

<!-- TODO Rewrite -->

## `STDIN` -- the Standard Input Stream

Keyboard inputs get stored by the operating system in a special data structure called a "stream".  A memory-stream is a kind of First-In-First-Out queue for byte-data storage and retrieval. In most cases the keyboard stream is named `stdin`, but Java chooses to make this stream available under the name `System.in`

### Writing to `STDIN`

The simple act of typing in the keyboard places the byte equivalent in `stdin`. In the example below, the enter key in Linux is represented by the hexidecimal byte value `x0a`.  The value entered into `stdin` is operating system dependent.  A programming language "learns" this value during its installation.
 
![Writing to Stdin](.guides/img/stdin_1.png)[^1]

[^1]: J.R.R. Tolkien, "The Return of the King", Houghton Mifflin Company

### Reading from `STDIN`

High-level programming languages use various commands, classes and methods to read from `stdin`.  This happens so quickly it often appears that the input goes directly to the program; it does not.

When reading from `stdin`, a programming language typically removes a byte from `stdin`, converts it to its ASCII equivalent, and adds that character to a string. The programming language stops reading when it removes the special byte representing `<enter>`.  Java does not include the `<enter>` as part of the returned string when using Scanner's `.nextLine()` method, Python does when using `.readline()`.  

If we have `stdin` as represented above and were to have a command to read a variable

```tex
string line1 = ReadLine(stdin)
```

![Writing to Stdin](.guides/img/stdin_2.png)

we would end up with 
* Java `line1==“In western lands beneath the Sun”`.
* Python `line1==“In western lands beneath the Sun\n”`

{{% notice info "Reading Strings and Newlines" %}}

Some modern high-level languages, include the trailing `<enter>` or `\n` character when reading `stdin` as a string.

However most programming languages have many ways to read `stdin`.  `stdin` in may be read as bytes, ints, floats etc.  Different stream reader methods may use different characters as delimiters, and may even cherry-pick bytes (taking some and leaving others) from the `stdin`.

In CC 210 we will process all inputs as strings, and convert those strings to other data types as necessary.

{{% /notice %}}


## Reading Input Without Prompting the User

Usually, when requesting the user provide an input with the keyboard, programmers provide a prompt.

![Example input prompt](.guides/img/stdin_4.png)

This tells the user what to do, and more importantly, does not have a naked blinking cursor as the only indication that some action is necessary.

![Example naked input prompt](.guides/img/stdin_3.png)

In fact, naked prompts for user keyboard input would be nearly universally acclaimed as a bad coding style.  

Nevertheless, we have chosen to have you use this style for CC 210.

Your grade is based on exactly matching a program's output, and input-prompts are part of that.  We did not want you spending a lot of time looking for typos and extra spaces in your input-prompts trying to find that one character which is not correct.  Thus we adopt this bad convention of naked (or, if you prefer, blind) input prompts.  When writing code for your own purposes, ALWAYS include a prompt when a human is supposed to respond.



