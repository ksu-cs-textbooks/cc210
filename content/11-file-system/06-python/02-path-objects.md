---
title: "Path Objects"
pre: "2. "
weight: 20
---

As you should recall, a Linux (Posix) path can be represented by a string, starting from the root (`/`).

![File Tree](/images/11-file/filetree.png)

The terminal always starts in `/home/codio/workspace`  and we have typically worked in `/home/codio/workspace/python`. When in the terminal, the present working directory (pwd) is the directory "level" you are currently at.

When you invoke the Python interpreter with the command `python3`, Python sets the <b>current working directory (cwd)</b> for the program to Linux's pwd.

```tex
/home/codio/workspace$ python3 demo/demo.py
   #  cwd in program is set to /home/codio/workspace
   
/home/codio/workspace/demo$ python3 demo.py
   #  cwd in program is set to /home/codio/workspace/demo
```

##  Creating a Path object
To create a path object in Python, we use code similar to this

```python
from pathlib import Path

    p_object = Path("/home/codio/workspace/demo/memo.txt")
```

In the code above, we can simply replace the string `"/home/codio/workspace/demo/memo.txt"` with any string to create the indicated path object. It will even accept relative paths, so `p_object("memo.txt")` would create a path `<cwd>/memo.txt`.

Path objects have access to many class attributes and methods.  Some useful ones are:
* name: an attribute string the string used to instantiate the object 
* absolute(): a method returning a string of the absolute path
* exists(): a method returning True if the absolute path is either a file or directory
* is_file():  a method returning True if the absolute path is a file
* is_dir(): a method returning True if the absolute path is a directory.

{{% notice info "Why .exists()" %}}

Creating a Path-object does not interact with the file system.  So a reasonable practice when trying to use or access file is to create the path then check if it exists.  In this manner one can safely create new directories and files.  Particularly with files, programming languages assume the programmer knows what they are doing.   Most methods to write to a file will <b>overwrite</b> and destroy any existing file with the same name.  

By first checking to see if the path exists, it is possible to choose a new, unused file name so as to not overwrite existing data.

This process of checking if a path exists and is a file <b>before</b> attempting to treat it as such is a type of "look before you leap" programming.  

{{% /notice %}}

In the file `demo/demo.py` you can see the use of some common Path features.

```python

p_memo = Path("memo.txt")
try:
    print (p_memo.name)
    print (p_memo.absolute())
    print (p_memo.exists())
except IOError as e:
    print(e)

```

It creates a Path-object for `/home/codio/workspace/demo/memo.txt` and prints out its name, absolute path and whether or not it exists.  

Note the exception handling.  While not all features of the Path-object interact with the file system, Python documentation does not state which attributes and methods can throw which exceptions^[Several languages, like JAVA, require module authors to list, by method or class, which exceptions can be raised.  This simplifies the programmer's task.]. Here if there is any IO problem with accessing the object's features, we simply catch and print out error.

## Other Considerations

In the below examples if is assumed that `from pathlib import Path` has been used.

### Create

We can also create either a file or directory based on a Path:

```python
pathObject = Path("test")

# Create a directory
pathObject.mkdir()
 
# Create a file (by opening it)
pathObject.touch()
```

The `mkdir()` method will raise a FileExistsError if something already exists at that path. To create a file, `.touch()` creates an empty file.  It does nothing if the file exists.

### Copy and Move

There are also methods we can use to copy or move an item from one path to another path:

```python
destination = pathlib.Path("/home/codio/workspace/file2.txt")

# Move (rename) a file
pathObject.rename(destination)

# Copy a file
# We need to add `import shutil` to the top of the script
shutil.copy2(str(pathObject), str(destination))
```

These work very similarly to the `cp` and `mv` commands we've already seen on the Linux terminal. To move a file, we can simply rename it. We're even allowed to use the `rename()` method to change the path to the file as well. 

To copy a file, we use the `copy2()` method from the `shutil` library. In Python 3.4, which is the version of Python currently supported in Codio, we need to convert both of our path objects to strings before we can use them with `copy2()`. However, in more recent versions of Python, we don't have to do that step. 

### Delete

We can also delete an existing file or path:

```python
# Delete a file
pathObject.unlink()

# Delete an empty directory
pathObject.rmdir()
```

The `unlink()` method is used to delete a single file. To remove a directory, we can use the `rmdir()` method instead. However, the directory must be empty, or else the method will raise an OSError.
