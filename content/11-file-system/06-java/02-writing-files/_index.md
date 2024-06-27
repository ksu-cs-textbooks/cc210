---
title: "Writing Files"
pre: "2. "
weight: 20
---

{{< youtube u0jr_oelbuc  >}}

[Video Materials]({{% relref "./video" %}})

Beyond just reading data from files, we can also create our own files and write data directly to them. 

## Opening a File for Writing

In Java, we'll use a class named BufferedWriter to actually handle writing to a file. So, to create a BufferedWriter object, we could do something like the following example:

```java
import java.io.BufferedWriter;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.io.IOException;
import java.lang.UnsupportedOperationException;
import java.nio.file.InvalidPathException;
import java.lang.ArrayIndexOutOfBoundsException;

public class Write{

  public static void main(String[] args){
  
    try(
      BufferedWriter writer = Files.newBufferedWriter(Paths.get("output.txt"));
    ){
   
      writer.write("Hello World");
      writer.newLine();
   
    }catch(ArrayIndexOutOfBoundsException e){
      //no arguments provided
      System.out.println("Error: no arguments provided!");
      return;
    }catch(InvalidPathException e){
      //path is invalid
      System.out.println("Error: invalid file path!");
      return;
    }catch(IOException e){
      //cannot open file or error while writing
      System.out.println("Error: I/O error!");
      return;
    }catch(UnsupportedOperationException e){
      //unable to open the file for writing
      System.out.println("Error: unable to open file for writing!");
      return;
    }catch(Exception e){
      //something went wrong
      System.out.println("Error: unknown error!");
      return;
    }
  }
}
```

Let's break this code down into smaller parts so we can understand how it works.

First, we are using a **Try with Resources** statement to handle creating the BufferedWriter to write to the output file. This will automatically handle closing the file when we are done with it. Otherwise, we'd need to add a `finally` block that includes `writer.close()` to make sure the file is closed properly. If we don't do that step, there is a chance that our data may not get written to the file correctly. 

Inside of the **Try with Resources** block, we have this line:

```java
BufferedWriter writer = Files.newBufferedWriter(Paths.get("output.txt"));
```

This line uses the Files class in `java.nio.files` to handle opening a file and creating a new BufferedWriter to write to that file. The `newBufferedWriter()` method needs a single input, which is a Path object representing the file to be opened. So, we can use the same `Paths.get()` method we use when opening a file for reading. Here we are using `"output.txt"` as the path to the file, but we can use any valid String as well. 

It is important to note that, by default, if the file we are writing to already exists, it will be overwritten with the new output. If it doesn't exist, it will be created. There are ways to open a file and append new data to it without overwriting the file, which we'll discuss below.

Inside of the **Try with Resources** statement, we see two lines that write data to the file using the BufferedWriter object. The first method, `writer.write()` can be used to write any String to the file. So, we can use this just like we would `System.out.print()` when writing output to the terminal. We can even use formatted strings as well!

The second line, `writer.newLine()` prints a newline character to the output file. This is because the `writer.write()` method does not output a newline character by default each time it is used. This is different than `System.out.println()`, which always outputs a newline after each output. So, we need to use `writer.newLine()` each time we want to start on a new line. 

Finally, there are several exception handlers at the end of the **Try with Resources** statement. They handle the most common exceptions that can occur when opening and writing to a file. The only one we haven't covered so far is the UnsupportedOperationException, which is used when the operating system doesn't allow us to write to a file, usually because the file permissions do not allow us to change or modify the file. It can also happen when we aren't allowed to create a new file in the location we've specified. There are several other exceptions that could be thrown when we are unable to write to a file based on the type of operating system we are using. So, we'll also need to catch a generic Exception here, just to be safe. 

## Standard Open Options

When opening a file, we can also give a set of options, known as StandardOpenOptions in Java, to specify how we'd like to handle the file when it is opened. By default, when we use the `Files.newBufferedWriter()` method to open a file, it uses the following options:

* StandardOpenOption.CREATE - create a file if it does not already exist
* StandardOpenOption.WRITE - open for write access
* StandardOpenOption.TRUNCATE_EXISTING - if the file exists, it will be truncated (all data will be removed)

If we'd like to change those options, we can specify them when opening the file. For example, if we'd like to append to an existing file, we can use the following code to open the file:

```java
BufferedWriter writer = Files.newBufferedWriter(Paths.get("input.txt"), StandardOpenOption.CREATE, StandardOpenOption.WRITE, StandardOpenOption.APPEND);
```

We'll also need to add `import java.nio.file.StandardOpenOption;` to the top of the file to give us access to those options.

There are many other options available in the Java StandardOpenOption class. Feel free to read the documentation linked below in the resources section to learn more.

## Flushing Output Buffers

When writing data to a file using a program, it is important to understand how the underlying operating system handles that process. In many cases, the operating system will store, or _buffer_ the output in memory, then write the output directly to the file a bit later. This allows the operating system to tell our program that the write was successful while it waits for the storage device the file is actually stored on to respond. So, our programs appear to run very quickly.

However, at times we want to tell the operating system to write the data it has stored in memory directly to the file. To do that, we can use the `flush()` method of our BufferedWriter class to _flush the buffer_, or make sure the data is written to the file. Here's an example:

```java
writer.write("Hello World");
writer.newLine();
writer.flush();
writer.write("More data");
writer.close();
```

Thankfully, the `close()` method will automatically write any buffered data to the file before closing it. So, we can either use the `close()` method ourselves, or use a **Try with Resources** statement to make sure that the file is closed automatically for us. 

We can even use `System.out.flush()` to perform the same operation when printing output to the terminal. In most cases all of our output is printed directly to the terminal, but we can make sure that the output buffer is empty by using the `flush()` method anytime. 

