---
title: "Paths & Managing Resources"
pre: "1. "
weight: 10
---

## Path vs File objects

In Python 2, the file system was accessed using a variety of functions built into several modules: `sys`, `os`, `glob`, `shutil` are some of the more common.  The standard way to open a file was with the built-in function `open(<str>)`.

``` python 
a = open('myTest.txt')
print (type(a))  #<type 'file'>
```

Which attempted to open the file represented by the string and returns a file-object.  <a href="https://docs.python.org/3/c-api/file.html">File-objects</a> could be read, written to and searched.  However, it was not possible or convenient  to rename, move, copy etc the file object.  Making matters worse, path naming conventions vary by operating system, meaning Python 2 programs written for Windows might not work in OS, Android etc.

Python 3 resolves this by introducing in 2014 the `Path` object in the `pathlib` module.  <a href="https://docs.python.org/3/c-api/pathlib.html">Path-objects</a> are operating system agnostic[^1] and offer a host of methods to support a rich range of operations.  

[^1]: When Python is installed, it sets up the `pathlib` module for the installed OS-- allowing the "generic" path constructs to access the file system

``` python
from pathlib import Path
a = Path('myTest.txt')
print (type(a))  #<class 'pathlib.PosixPath'>  Linux (our OS) uses a posix file system
```

Path objects can be files, directories or place-holders. If they are files they can be opened for reading and writing.  We will use Path-objects for file access in this course, Path-objects are like a supper-set of File-objects.

## Managing Resources (context)

There are various resources the Python interpreter, or any computer language, must receive from the operating systems.  The most common are memory and Input/output streams^[a file descriptor is a kind of IO stream].


### Memory

The Python interpreter manages the memory your programs uses.  It occasionally runs a "garbage collector" which searches for objects that have been deleted or have fallen out of scope and tells the OS to reclaim the memory.  this impacts performance as the garbage collector uses up computer cycles even if there is nothing to collect.

Older languages (notably C) and high  performance languages make memory management the programmer's responsibility.  Programmers allocate (`malloc()`) and free up memory (`free()`) as required.  Well written programs of this type are smaller (lower memory footprint) and faster in execution that managed memory languages like Python.

###  Files

Most programming languages, including Python, leave managing file system up to the programmer.  While a program may make thousands of memory requests a second, they will normally only have a handful of files open at a time.  There is basically one rule:

<b>Once A File is Opened it MUST be Closed</b>

It can be hard to do this if when File/Path-objects are attributes of a class, object; passed as parameters or when exceptions occur.

```python
1  from pathlib import Path
2  some_path = Path('some_file.txt')
3  in_file = some_path.open('r') 
4  for line in in_file:
5      print(int(line))
6  in_file.close()
```

Here we 

* create a Path-object (2)
* makes a "reader" for the Path (3)
  * the '.open()' gets a file handle (descriptor) from the operating system
* for each line in the file it attempts to convert the line to an int then print it (4 -5)
* closes the reader (6)
  * this tells the OS to free-up or delete the file handle

That is fine, as long as there is no error.  

But what if a line in the file were 'cat'.  Certainly an exception would get thrown, 'cat' cannot be turned into an `int`.  

The program would terminate, but the OS will not be told to free file handler.  This is bad as the more file handlers that are open, the slower performance.  When  writing to files there are additional hazards:
* not everything may get written
* there is a small chance you corrupt the OS's file-control block, making the file and possibly the directory, unusable

To help with this Python has built in a context management function: `with .. as .. :`.

```python
with <item> as <identifier>:
    with-body
```
```python
1  from pathlib import Path
2  some_path = Path('some_file.txt')
3  with some_path.open('r') as in_file:
4      for line in in_file:
5          print(line)
6
```

Here we 
* create a Path-object (2) to the file
* open the Path for reading (3) using the alias 'in_file'
* for each line in the file it attempts to convert the line to an int then print it (4 -5)
* closes the reader (6)
  ** this behavior is built into the `with` structure
  
`with` will ensure that the `.close()`  is run on `in_file` whenever the context (with block) is left.  It will do this even if the reason for leaving the with-block is an unhandled exception.

{{% notice info "__enter__() and __exit__()" %}}

The `with` statement runs a special enter-method when the with-block starts and exit-method when it finishes.  This is based on the type (class) of the item you create.  With `Path-object.open()` creates a `io.TextIOWrapper`, which is a kind of stream which has these special methods defined.

Writing these methods requires detailed knowledge of the operating systems, network protocols and application specific "shutdown" procedures. 

Imagine the complexity of shutting down a networked database session that uses multiple network connections for speed and redundancy.  In this case, `__exit__()` might have to properly sequence database, network and parallel thread "shutdown" activities to ensure no corrupt data gets to the database and the network connections can be re-established.

{{% /notice %}}

You should always wrap your **file** reads and writes in a `with`-statement.

