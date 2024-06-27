---
title: "Writing Files"
pre: "4. "
weight: 40
---

<!--{{< youtube iGPn_vMqZlY  >}} -->

<!--[Video Materials]({{% relref "./video" %}}) -->

<!-- TODO Update Video -->

Beyond just reading data from files, we can also create our own files and write data directly to them. 

## Opening a File for Writing

In Python, we'll use the  `.open()` method we've been using to read from a file to also open a file for writing. So, here's an example of what that might look like:


```python
import sys
from pathlib import Path
import io

class Writer:
    
    @classmethod
    def main(cls, args):
        if len(args) > 1:
            path = Path(args[1])
            try: 
                with path.open("w") as writer:
                    pass # do some writing
            except IOError as e:
              # unable to write to the file
              print("IOError: {}".format(e))
            except Exception as e:  
              # unable to write to the file
              print("Exception: {}".format(e))

```

Let's break this code down into smaller parts so we can understand how it works.

First, we are using a **Try-Except** statement to handle any exceptions that are raised when we use a file. 
Next we check to see if a command line argument was provided and if so we make a Path object using it.

Then, we use a **With** statement to handle automatically closing our file once we are done with it. Otherwise, we'd need to add a `finally` block that includes `writer.close()` to make sure the file is closed properly. If we don't do that step, there is a chance that our data may not get written to the file correctly.  

We have the **With** statement :

```python
with path.open("w") as writer:
```

This line creates a _io_ object using Path's `open()` method to open a file. We provide the argument: "w", which stands for “write” and allows us to open the file for writing. If we don't provide that argument, it will just open the file for reading.  Then, we use the `as` keyword to assign it to the variable `writer`. This is very similar to how we've already seen the `as` keyword. 

It is important to note that, by default, if the file we are writing to already exists, it will be overwritten with the new output. If it doesn't exist, it will be created. There are ways to open a file and append new data to it without overwriting the file, which we'll discuss below.

Inside of the **With** statement, we see two lines that write data to the file using the `write()` method. That method can be used to write any string to the file. So, we can use this just like we would `print()` when writing output to the terminal. We can even use formatted strings!

The second line prints a newline character to the output file. This is because the `write()` method does not output a newline character by default each time it is used. This is different than `print()`, which always outputs a newline after each output unless we specify otherwise. So, we need to use `\n` each time we want to print a newline to the file. 

Finally, there are several exception handlers at the end of the **Try-Except** statement. They handle the most common exceptions that can occur when opening and writing to a file, but may not account for all possible exceptions. So, we've also included a block to catch the generic `Exception` as well. 

## Open Modes

When opening a file, we can also give a set of options, known as _modes_ in Python, to specify how we'd like to handle the file when it is opened. By default, when we use the `open()` method to open a file, it uses the following option:

* `r` - open for reading

If we'd like to change those options, we can specify them when opening the file. For example, if we'd like to append to an existing file, we can use the following code in our **With** statement to open the file:

```python
with path.open("a") as writer:
```

There are many other modes available in Python. 

## Flushing Output Buffers

When writing data to a file using a program, it is important to understand how the underlying operating system handles that process. In many cases, the operating system will store, or _buffer_ the output in memory, then write the output directly to the file a bit later. This allows the operating system to tell our program that the write was successful while it waits for the storage device the file is actually stored on to respond. So, our programs appear to run very quickly.

However, at times we want to tell the operating system to write the data it has stored in memory directly to the file. To do that, we can use the `flush()` method of our file object to _flush the buffer_, or make sure the data is written to the file. Here's an example:

```python
writer.write("Hello World")
writer.write("\n")
writer.flush()
writer.write("More data")
writer.close()
```

Thankfully, the `close()` method will automatically write any buffered data to the file before closing it. So, we can either use the `close()` method ourselves, or use a **With** statement to make sure that the file is closed automatically for us. 

We can even use `sys.stdout.flush()` to perform the same operation when printing output to the terminal. In most cases all of our output is printed directly to the terminal, but we can make sure that the output buffer is empty by using the `sys.stdout.flush()` method anytime.

## Example

Here's another quick example program to make sure we are able to write to files correctly. Feel free to adapt the code above to complete the exercise. 

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}