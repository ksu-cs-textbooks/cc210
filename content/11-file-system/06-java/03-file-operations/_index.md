---
title: "File Operations"
pre: "3. "
weight: 30
---

{{% youtube gAAiv1Hbafc %}}

[Video Materials]({{<relref "./video">}})

Beyond just reading and writing files, we can also perform several operations on files and directories from within our programs. In fact, pretty much any operation that can be done in the terminal can also be done in our programs, though some are more difficult than others. Let's review a few of the common file operations and how we can use them in Java.

## Paths

First, we'll need to know how to access a _path_ using Java. A _path_ is a string that references a particular file or directory in a file system, identified by the path needed to move from the root node to that item. So, for example, we may use the path `/home/codio/workspace/file.txt` to reference a particular file in our Codio workspace. 

In Java, we also use the term _Path_ to refer to an object that points to an item on the file system. 

To create a Path object in Java, we use code similar to this

```java
import java.nio.file.Paths;
import java.nio.file.Path;
import java.nio.file.Files;
import java.nio.file.InvalidPathException;
import java.io.IOException;

public class Manipulate{
  public static void main(String[] args){
    
    try{
      Path pathObject = Paths.get("/home/codio/workspace/file.txt");
    
      /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */
      
    }catch(InvalidPathException e){
      //cannot convert string to path
      System.out.println("Error: Invalid Path");
      return;
    }catch(IOException e){
      //file system error
      System.out.println("Error: IOException");
      return;
    }
  }
}
```

In the code above, we can simply replace the string `"/home/codio/workspace/file.txt"` with any valid file path stored in a string to create the indicated Path object. It will even accept absolute paths, relative paths, and paths to directories instead of just individual files. It's a very versatile tool to use. For the rest of the examples below, we'll be using the `pathObject` variable created in the example above, with the code placed where the `MORE CODE GOES HERE` comment is in the skeleton above. 

## What Is It?

Once we have a Path object, we can use a few methods to determine what type of an object it is:

```java
//Determine if a file or directory exists at that path
Files.exists(pathObject);

//Is that object a directory?
Files.isDirectory(pathObject);

//Is that object a regular file?
Files.isRegularFile(pathObject);
```

Each of those methods returns a boolean value, either `true` or `false`. So, they can easily be used with **If-Then** statements to take different actions based on the type of object found. So, in our code, we can use some of these tests before trying to open a file, avoiding some of the more common exceptions. As we discussed in the chapter on exceptions, it is really up to us whether we prefer to use **If-Then** statements to avoid these exceptions, or **Try-Catch** statements to deal with them when they do happen. 

## How Big Is It?

We can also get the size of the object:

```java
Files.size(pathObject);
```

If the item is a regular file, this method will return the size in bytes of the file. However, if we use this method on a file that doesn't exist, or a directory, it will throw an IOException, so we'll probably need to pair it with one of the other methods above to avoid that problem.

## Copy and Move

There are also methods we can use to copy or move an item from one path to another path:

```java
Path source = Paths.get("/home/codio/workspace/dir1/file1.txt");
Path dest = Paths.get("/home/codio/workspace/dir2/file2.txt");

Files.copy(source, dest);
Files.move(source, dest);
```

These work very similarly to the `cp` and `mv` commands we've already seen on the Linux terminal. In addition, if the destination path already exists, these methods will throw a [FileAlreadyExistsException](https://docs.oracle.com/javase/8/docs/api/java/nio/file/FileAlreadyExistsException.html) unless we specify that it should overwrite existing files. We can refer to the documentation linked below to see examples for how to accomplish that.

## Delete

We can also delete an existing file or path:

```java
Files.delete(pathObject);
```

This method will delete a single file if the `pathObject` variable references a single file. If it references a directory, that directory must be empty, or else it will throw a [DirectoryNotEmptyException](https://docs.oracle.com/javase/8/docs/api/java/nio/file/DirectoryNotEmptyException.html). 

## Create

Of course, we can also create either a file or directory based on a Path:

```java
Files.createFile(pathObject);
Files.createDirectory(pathObject);
```

These methods will also throw a [FileAlreadyExistsException](https://docs.oracle.com/javase/8/docs/api/java/nio/file/FileAlreadyExistsException.html) if something already exists at that path.

## Example

Let's create a simple example program to test a few of these methods. 

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

### References

* [Files](https://docs.oracle.com/javase/8/docs/api/java/nio/file/Files.html) in the Java 8 API Documentation
* [Paths](https://docs.oracle.com/javase/8/docs/api/java/nio/file/Paths.html) in the Java 8 API Documentation
* [Java File I/O Tutorial](https://docs.oracle.com/javase/tutorial/essential/io/fileio.html) from Oracle's Java Tutorials

