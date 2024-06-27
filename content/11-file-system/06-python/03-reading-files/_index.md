---
title: "Reading Files"
pre: "3. "
weight: 30
---

<!--{{< youtube tdBCzDVmqqo  >}} -->

<!--[Video Materials]({{% relref "./video" %}}) -->

<!-- TODO Update Video -->

Lets look at how we might take input from either a file or the keyboard.  Our goal is that the program uses the first command line argument for input if it is a file.  If no argument is given it should use the keyboard.  If the first command line argument is not a file, or if an error occurs, the program should print "Error processing the first argument as a file". A start might be:

```python
import sys
import io
import pathlib

...
    def main(cls, args):
        if len(args) > 1:
            pass
            # some commands to handle the file reading
            # reader = ???
        else:
            reader = sys.stdin


```

According to the <a href="https://docs.python.org/3.4/library/pathlib.html">Python documentation</a> , `Path`'s `.open('r')` opens the Path as a file for read-access[^1].  Our strategy will be to read the entire file into memory as a string, then convert that string into an ioString Stream so it has the same method calls as the keyboard stream.

[^1]: Errors will be thrown if the Path-object is not a file.

```python

if len(args) > 1:
    # make a Path-object
    in_path = Path(args[1]) 
    # make a File-object from the Path object 
    try:
        if in_path.is_file():
            with in_path.open('r') as in_file:
                # store all the text in the file as a string
                data = "".join(in_file.readlines())
                # convert 'data' to a stream of text
                reader = io.StringIO(data)
        else:
            raise IOError()
    except IOError as e:
        print("Path is not a file")
        return
else:
    reader = sys.stdin

```

### Reading Data From the File

1. The line `data = "".join(input_file.readlines())` reads all the lines from the file.
2. `input_file.readlines()` creates a list of `str` to represent the data, and `data = "".join(..)` is a way to make them all one `str`.  
3. This `str` is then used to create an object of type oi.StringIO--this object is in the same "family" as `sys.stdin` and they share most of the same method names.

You can look up <a href="https://docs.python.org/3/library/io.html?highlight=readlines#io.IOBase.readlines">readlines()</a> and <a href="https://docs.python.org/3/library/stdtypes.html">str.join()</a> if you want more information.


Running this code snippet has one of three outcomes:
1. `reader` is a string-stream attached to the data that was in the input file (the file is closed by exiting the `with` statement)
1. `reader` is a string-stream attached standard input
1. an exception has been thrown

### Exceptions

Of course, as we learned in an earlier chapter, we should also add some **Try-Except** statements to this code to prevent any exceptions from crashing the program. So, let's do that now:

```python
 
    if len(args) > 1:
        # make a Path-object
        in_path = Path(args[1]) 
        # make a File-object from the Path object 
        try:
            if in_path.is_file():
                with in_path.open('r') as in_file:
                    # store all the text in the file as a string
                    data = "".join(in_file.readlines())
                    # convert 'data' to a stream of text
                    reader = io.StringIO(data)
            else:
                print("Error processing the first argument as a file")
                return
        except Exception as e:
            print("Error processing the first argument as a file")
            return
            
    else:
        reader = sys.stdin
```

We wrap all the Path and File commands in a single try-catch block.

If there is a command line argument, the code uses the Path method `is_file()` to decide if it is a file and thus if it should try and open in for reading in the **with** statement. Note we print an error message and exit main() using a `return` statement if the path is not a file.

Te number of exceptions are which could be thrown are vast, esoteric and potentially undocumented[^2]--since we know the file exists, we will never see a FileNotFoundError.  But we could still lose connection with a network drive, or if the file is huge, run out of memory trying to create the StringIO object.  So lets catch the generic Exception and exit the program.

[^2]: Python specifications do not force language developers to enumerate all the possible exceptions a function or method can generate


## Reading from the StringIO or sys.stdin Object

<p style="color:red; padding:10"><b>An unfortunate compromise:</b> in order to have the exact same code be able to handle the terminal or a file input and accept a variable number inputs, there has to be a way for a program to determine it is done with getting data.  We have chosen that a blank line represents this sentinel value. This means we cannot write programs that accept blank lines as valid input.<br> Fortunately, it is vary rare to need a program that handles the input from the terminal and a file exactly the same.  In well designed object oriented code, different classes, thus different code will generally be used to process input from different sources. </p>

Data read via the `readline()` or `readlines()` methods includes the operating system specific line terminator--a fancy way of saying the `\n` character in for Linux.  

In this course, it is best to use the string `strip()` method to eliminate leading and trailing whitespace characters.  Again, we want you focused on the logic and syntax of programming, not hunting for missing "spaces". 

So to read and print every line you would 

``` python
for line in reader:
    if line is None or len(line.strip()) == 0:
        break
    ...

```

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}