---
title: "Try-Catch"
pre: "3. "
weight: 30
---

{{< youtube QvH6BImQxII  >}}

[Video Materials]({{% relref "./video" %}})

Programs written in Java can have many exceptions occur on a regular basis. Thankfully, as we learned earlier, it is possible to detect and handle these exceptions in our code directly, in order to prevent our program crashing and causing the user more stress. Let's see how we can perform this step in Java.  A <b>Try-Catch</b> construct is synonymous with "handler".

## Try-Catch

In Java, we use a **Try-Catch** construct to detect and handle exceptions in our code. Let's look at a quick example, and then we can discuss how it works.

```java
import java.util.Scanner;
import java.lang.Exception;

public class Example{

  public static void main(String[] args){
  
    Scanner reader;
    
    try{
    
      reader = new Scanner(System.in);
      int x = Integer.parseInt(reader.nextLine());
      System.out.println(x);
      
    }catch(Exception e){
      System.out.println("Error!");
    }
    
  }
}
```

First, we use the `try` keyword, followed by curly braces `{}` around a block of code. If any exceptions occur in the code contained in the `try` statement, we can add `catch` statements to handle that exception.

Directly following the closing curly brace after the `try` block, we must include at least one `catch` statement. The `catch` keyword is followed by the name of an exception and a variable for that exception in parentheses `()`. In this example, we are just catching the generic `Exception` type, which will match any catchable exception. We'll see how we can detect specific exceptions in a later example. Then, we have one more block of code contained in curly braces `{}` that is executed when we detect an exception. We can use the variable for the exception, in this case `e`, to access additional details about the exception we've detected. 

Finally, notice that we also must add `import java.lang.Exception` to the top of our file. We'll need to import any exceptions we want to catch in order to use them. 

## Which Exceptions to Catch?

When writing code, it can sometimes be very difficult to even know which exceptions to expect from a particular piece of code. Thankfully, the [Java 8 API Reference](https://docs.oracle.com/javase/8/docs/api/index.html) includes quite a bit of information, including which exceptions can be thrown by a particular method. 

Let's return to our earlier example. Here is the code contained in the `try` block:

```java
reader = new Scanner(System.in);
int x = Integer.parseInt(reader.nextLine());
System.out.println(x);
```

While this may look like a very simple few lines of code, there are actually several exceptions that could be produced here. Below is a list of them, followed by a link to the Java 8 API reference for the source of that exception:

* FileNotFoundException - [new Scanner(File) Constructor](https://docs.oracle.com/javase/8/docs/api/java/util/Scanner.html#Scanner-java.io.File-)
* NumberFormatException - [Integer.parseInt()](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html#parseInt-java.lang.String-)
* NoSuchElementException - [Scanner.nextLine()](https://docs.oracle.com/javase/8/docs/api/java/util/Scanner.html#nextLine--)
* IllegalStateException - [Scanner.nextLine()](https://docs.oracle.com/javase/8/docs/api/java/util/Scanner.html#nextLine--)

When writing truly bulletproof code, it is a good idea to attempt to catch and handle all of these exceptions if possible. You can always refer to the official Java 8 API reference to see what exceptions could be produced by any methods you use that are a part of the main Java language. Later on in this chapter we'll discuss some best practices when it comes to detecting and handling exceptions in code. 

## Handling Multiple Exceptions

Of course, we can add multiple `catch` statements after any `try` block to catch different types of exceptions. 

```java
import java.util.Scanner;
import java.io.IOException;
import java.lang.NumberFormatException;

public class Example{

  public static void main(String[] args){
  
    Scanner reader;
    
    try{
    
      reader = new Scanner(System.in);
      int x = Integer.parseInt(reader.nextLine());
      System.out.println(x);
      
    }catch(IOException e){
      System.out.println("Error: IO Exception!");
    }catch(NumberFormatException e){
      System.out.println("Error: Input Does Not Match Expected Format!");
    }
    
  }
}
```

In the example code above, we see three different `catch` statements, each of which will handle a different type of exception. When an exception occurs in the code contained in a `try` block, the Java runtime will create the exception, and then it will search for the first handler that matches. So, it will begin with the first `catch` statement, and see if the exception created matches the type of the exception in parenthesis. If so, it will execute the code inside of that `catch` block. If not, it will continue to the next `catch` statement. If none of the `catch` statements match the exception, then it will be _thrown_ and cause the program to stop executing. 

## Exception Hierarchy

The exceptions in Java form a hierarchical structure, meaning that an exception may match multiple types. For example, all exceptions that programs can catch are based on the generic Exception type. So, FileNotFoundException and ArrayIndexOutOfBoundsException would both match the Exception type. 

In addition, many exceptions are descended from the IOException type. For example, FileNotFoundException is based on IOException, which itself is based on the Exception type. So, a FileNotFoundException would match any of those three types of exceptions. It can make things a bit tricky!

So, how can we know what types of exceptions we are dealing with, and what the hierarchy is? Thankfully, the [Java 8 API Reference](https://docs.oracle.com/javase/8/docs/api/index.html) contains information about all possible exceptions, including the entire hierarchy of that exception. 

For example, here is a screenshot from the [FileNotFoundException](https://docs.oracle.com/javase/8/docs/api/java/io/FileNotFoundException.html) page showing its hierarchy:

![FileNotFoundException Hierarchy](/images/10-except/8.7.j.3.filenotfound.png)

Because of this, we must be careful about how we order the catch statements. In general, we want to place the more specific exceptions first (the ones further down the hierarchy), and the more generic exceptions later. 

Let's look at an example of poor ordering of exception handlers:

```java
import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.lang.NumberFormatException;

public class Example{

  public static void main(String[] args){
  
    Scanner reader;
    
    try{
    
      reader = new Scanner(new File("input.txt"));
      int x = Integer.parseInt(reader.nextLine());
      System.out.println(x);
      
    }catch(IOException e){
      System.out.println("Error: IO Exception!");
    }catch(FileNotFoundException e){s
      System.out.println("Error: File Not Found!");
    }catch(NumberFormatException e){
      System.out.println("Error: Input Does Not Match Expected Format!");
    }
    
  }
}
```

In the code above, we are catching the IOException first. So, if the code produces a FileNotFoundException, it will be caught and handled by the first `catch` statement, since FileNotFoundException is also an IOException. Therefore, we wouldn't want to order our `catch` statements in this way.

{{% notice note "Reading Files" %}}

This chapter introduces the basic code for reading files using a `Scanner` object. It is mainly presented as a way to introduce some of the more common exceptions related to file input and output. We'll cover the actual process of reading and writing from files in a later chapter.

{{% /notice %}}

## Try It!

Let's see if we can write a very simple program to catch and handle a few common exceptions. Here's some code to start with:

```java
import java.util.Scanner;
import java.io.File;

public class Try{

  public static void main(String[] args){
  
    Scanner reader;

    reader = new Scanner(System.in);
    int x = Integer.parseInt(reader.nextLine());
    int y = Integer.parseInt(reader.nextLine());
    int z = x / y;
    
    System.out.println(z);
    
  }
}
```

For this example, place this starter code in `Try.java`, open to the left, and modify it to catch and handle the following exceptions by printing the given error messages:

* NumberFormatException - print "Error: Input Does Not Match Expected Format!"
* NoSuchElementException - print "Error: Too Few Inputs Provided!"
* ArithmeticException - print "Error: Divide by Zero!"

Any other exceptions can be ignored. Don't forget to add import statements at the top of the file for each type of exception we need to catch!

