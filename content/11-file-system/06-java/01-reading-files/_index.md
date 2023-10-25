---
title: "Reading Files"
pre: "1. "
weight: 10
---

<!--{{% youtube y6vTrInbR1I %}}

<!--[Video Materials]({{<relref "./video">}})

<!-- TODO Update Video -->

We've already been reading data from files throughout most of this course. However, let's take some time to review that code and improve it a bit to make it more flexible for use in the future. 

## Opening a File using `java.nio.file`

Here is the code we've used in the Exceptions module to open a file for reading:

```java
reader = new Scanner(new File("input.txt""));
```

This code uses a file name `"input.txt"`, and then creates a Scanner object to read data from that file, using an intermediate File object to represent the file itself. Scanners only open files for reading.

The File object used here is part of the older `java.io` package, which has been present in the Java API for quite a while. However, more recent versions of Java have included the new `java.nio.file` package, which includes many easier to use methods for handling files and directories. 

So, instead of using a File object from `java.io`, we will use a Path object from `java.nio.file`, which is much more flexible. In fact, it is completely compatible with the older versions, so we can easily obtain a Path from a File and vice-versa.

To create a Path object, we use the `Paths.get()` static method. So, an updated version of our starter code might look like this:

```java
import java.util.Scanner;
import java.nio.file.Paths;

public class Read{
  
  public static void main(String[] args) throws Exception{
    
    Scanner reader;
    reader = new Scanner(Paths.get("input.txt"));
    
    /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */
    
  }
}
```

There are a couple of important changes:

1. Instead of `import java.io.File;` at the top of the code, we must now use `import java.nio.file.Paths;` to get access to the new Paths class.
2. When creating the Scanner, we can now use `reader = new Scanner(Paths.get("input.txt"));`. This will use the `Paths.get()` static method to create a Path object, and then use that object to construct a Scanner which can read data from the file found at that path. 

With those changes in place, we are now using the `java.nio.file` library, which we'll use throughout this chapter. 

## Exceptions

Of course, as we learned in an earlier chapter, we should also add some **Try-Catch** and **Try with Resources** statements to this code to prevent any exceptions. So, let's do that now:

```java
import java.util.Scanner;
import java.nio.file.Paths;
import java.lang.ArrayIndexOutOfBoundsException;
import java.nio.file.InvalidPathException;
import java.nio.file.NoSuchFileException;

public class Read{
  
  public static void main(String[] args) throws Exception{
    
    Scanner scanner;
    
    try(
      //Try with Resources will automatically close the file
      Scanner reader = new Scanner(Paths.get("input.txt"));
    ){
    
      /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */
     
    //add additional catch statements here to handle expected exceptions
    }catch(InvalidPathException e){
      //path is invalid
      System.out.println("Error: invalid file path!");
      return;
    }catch(NoSuchFileException e){
      //file is not found
      System.out.println("Error: file not found!");
      return;
    }catch(Exception e){
      //generic catch statement
      System.out.println("Error: unknown error while reading input!");
    }
    
  }
}
```

This code is very similar to the code we saw in a previous chapter, with a couple of major changes:

1. At the bottom, we are using a **Try with Resources** statement to actually handle reading our input. This will automatically close the file once we are done with it. Otherwise, we'd need to add `scanner.close()` at the end of our program, possibly in a `finally` block. 
1. Since we are using the `java.nio.file` package, we now must use `import java.nio.file.NoSuchFileException;` to get the correct exception when a file cannot be found. 
1. In addition, the `Paths.get()` method can throw an `InvalidPathException` if the path provided cannot be converted to a proper path. 

## Reading Data

Once we have our file open, we can use the same methods we've been using to read data from the file. For example, we can use a simple **While** loop to read each line of the file:

```java
while(scanner.hasNext()){
  String line = scanner.nextLine().trim();
  if(line.length() == 0){
    break;
  }
}
```

In this code, we use the `hasNext()` method to check and see if the file has any additional lines to read. If so, it will read the line using the `nextLine()` method. We are also using the `trim()` method to remove any extra spaces from the beginning and end of the line. Finally, we have a short **If-Then** statement to check and see if the line is empty. If so, we'll assume that we've reached the end of the input file, or that the user typing input via the terminal is done, and we'll `break` out of the loop. 


