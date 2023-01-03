---
title: "Try with Resources"
pre: "6. "
weight: 60
---

{{% youtube 86RzF9SgSJE %}}

[Video Materials]({{<relref "./video">}})

Lastly, Java includes a special type of **Try-Catch** statement, known as a **Try with Resources** statement, that can perform some of the work typically handled by the `finally` block. 

## Try with Resources

Let's look at an example of a **Try with Resources** statement:

```java
import java.util.Scanner;
import java.io.File;
import java.lang.NumberFormatException;
import java.io.FileNotFoundException;

public class Resources{
  
  public static void main(String[] args){
    
    try(
      Scanner reader = new Scanner(new File(args[0]))
    ){
      
      int x = Integer.parseInt(reader.nextLine().trim();
      System.out.println(x + 5);
      
    }catch(NumberFormatException e){
      System.out.println("Error: Invalid Number Format!");
    }catch(FileNotFoundException e){
      System.out.println("Error: File Not Found!");
    }
    
  }
}
```

In this example, there is a new statement after the `try` keyword, surrounded by parentheses. Inside of that statement, we are declaring and initializing a new Scanner object to read data from a file. That Scanner object is the _resource_ that we are using in our **Try with Resources** statement. We can add multiple resources to that section, separated by semicolons `;`. 

When the code in the `try` statement throws an exception, Java will automatically try to close the resources declared in the **Try with Resources** statement. So, when we are reading input from a file, it would close that file and make sure that it isn't damaged or left open when our program crashes. 

In addition, any additional exceptions thrown when trying to close the file are _suppressed_ by the system, so we only see the exception that caused the initial error. This is much better than using a `finally` statement to close the file, since we'd have to run the risk of throwing a second exception inside of the `finally` statement. 

Any Java class that implements the [AutoCloseable](https://docs.oracle.com/javase/8/docs/api/java/lang/AutoCloseable.html) interface can be used as a resource in this way. The Java 8 API documentation for [AutoCloseable](https://docs.oracle.com/javase/8/docs/api/java/lang/AutoCloseable.html) lists all known classes that implement that interface. We'll discuss interfaces more later in this course. 

Specifically, this type of statement is great when writing programs that will handle large amounts of input, either by connecting to a database, reading from a file, or using the Internet to communicate with a server. A **Try with Resources** statement is a great way to make sure those programs are able to handle exceptions without leaving the system in an unstable state. 

{{% notice warning "Never Use with System Resources" %}}

Try-with resources should never be used in concert with Scanners Readers or Buffers connected to System resources.  For example

```java

// attach scanner to System stdin
Scanner reader = new Scanner( System.in);  
// use as part of try with resources
try (Scanner scan = reader){...

} catch (Exception e){ 

}
// now System.in is closed and unavailable to rest of program
```
is a bad construct.  

{{% /notice %}}