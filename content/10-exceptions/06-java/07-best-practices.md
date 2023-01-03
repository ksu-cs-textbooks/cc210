---
title: "Best Practices"
pre: "7. "
weight: 70
---

Now that we've seen lots of information about how to throw, catch, and handle exceptions in Java, it is a great time to discuss some of the best practices we can apply in our code to make it as readable and bulletproof as possible. While these aren't strict rules that must be followed all the time, they are great things to keep in mind as we write code that deals with exceptions.

## Leave No Exception Unhandled

As much as possible, we should write our code to handle any exception we can reasonably expect our users to run into when using our programs. We cannot assume that users will always provide the correct input in the correct format, and a single typo by a user should not cause our entire program to crash.

Instead, we should always use **Try-Catch** statements whenever possible to detect and handle those errors as simply as possible. In addition, if the program is interactive, we can combine that approach with the use of loops to prompt the user to provide new input to resolve the error. 

The [Java 8 API](https://docs.oracle.com/javase/8/docs/api/) is a great resource to determine which exceptions could be thrown by any methods used in our code.

{{% notice info "Don't Substitute Unchecked Exception Handling for Value Checking" %}}

You can go "try catch" crazy.  Exception handling is powerful, but also slow, really really slow. 

You can write something like 

```
try{
    ratio = x / y;
    }
catch ArithmeticException e{
    System.out.println("Cannot divide by zero");
    }
```
but 
```
if (y !=0){
    ratio = x / y;
    }
else{
    System.out.println("Cannot divide by zero");
}
``` 
executes a lot more efficiently.  In this example the IF-construct is about 60-times faster than the TRY-CATCH.

In fact, most unchecked exceptions can be avoided through value checking.  In this course, we may direct you to throw and catch exceptions of this type for practice in exception coding.

{{% /notice %}}

## Don't use Try-Catch blocks for Control Flow

It is BAD practice to have implied control flow embedded and disguised as `try catch`.  For example, if  we are to accept input from either a file given as a command line argument or the keyboard.  This first code block is acceptable:

```java
Scanner reader;
if args.length() == 1{
    try{
     reader = new Scanner(new File(args[0])); 
    }
    catch Exception e{
      System.out.println("error accessing file");
      return;
    }
  } else {
    reader = new Scanner(System.in);
  }

```

This next code block is bad style:

```java

   try{
      scanner = new Scanner(new File(args[0]));
    }catch(FileNotFoundException e){
      System.out.println("FileNotFoundException: " + e.getMessage());
      scanner = new Scanner(System.in);
    }
  }
```

Most readers of your code will not expect "flow logic" to be in the catch blocks and may miss it.


## Be Specific

We should also always strive to use specific exceptions in our `catch` statements whenever we can. So, if we are opening a file, we should include a `catch` statement for a FileNotFoundException, and not just a single generic `Exception`. Even though this means we may have to include several `catch` statements, it is much better in the long run because it allows us to know exactly what happened when our code has a problem.

In addition, we should always make sure we catch the most specific exceptions first, before any more generic exceptions. As we saw earlier, if we try to catch an IOException before a FileNotFoundException, we won't be able to tell when we've reached a FileNotFoundException at all, since it is a subtype of the IOException.  

## Use Messages and Stack Traces

The Java Exception class includes some very helpful methods we can use to get additional information when we encounter an exception. 

Here's an example to show what we can learn:

```java
import java.lang.ArithmeticException;

public class StackTrace{
  public static void main(String[] args){
    try{
      int x = 5 / 0;
    }catch(ArithmeticException e){
      System.out.println("Error: " + e.getMessage());
      e.printStackTrace();
    }
  }
}
```

When this code is executed, it will produce the following output:

```tex
$ java StackTrace
Error: / by zero
java.lang.ArithmeticException: / by zero
        at StackTrace.main(Finally.java:6)
```

The first line will use `e.getMessage()` to get the short version of the error, in this case the text "/ by zero". The second line uses `e.printStackTrace()` to print a full stack trace showing the location of the error in code. 

In general, it is best to only show the short error message to users, but in some cases it may be better to add our own message. The text "/ by zero" isn't very clear, even to developers. Instead, we could say "Error: divisor cannot be zero" to make the error message clearer.

The information contained in the stack trace is very helpful to developers when trying to debug and fix problems in the code, but that information is very confusing to users. As we learn how to build more advanced programs, we'll see how to record and log those error messages and stack traces for debugging, but hide them from our users. 

To see what other methods are available, refer to the [Throwable](https://docs.oracle.com/javase/8/docs/api/java/lang/Throwable.html) entry in the Java 8 API reference. 

## Don't Ignore Exceptions

Another big problem is that many developers tend to catch exceptions, only to ignore them so their program doesn't crash. Here's a quick example:

```java
int x = 0;
Scanner reader = new Scanner(System.in);
try{
  x = Integer.parseInt(reader.nextLine());
}catch(Exception e){
  //do nothing
}
```

In this code, if the user inputs something that can't be converted to an integer, the code just silently ignores the exception and proceeds with `x` still storing the value $0$. While that may not cause issues, it can also make it very frustrating to debug later issues or changes in this program. So, it is always best to output an error message when an exception occurs, even if it can be easily ignored without additional input from the user. This will make it easier to debug additional issues later on in development. 

## Bulletproof Code

Here's a simple program that asks the user for input, and will repeat the question until a valid input is received. This code is designed to handle many common situations and exceptions:

```java
import java.util.Scanner;
import java.lang.NumberFormatException;
import java.util.NoSuchElementException;

public class HandleInput{
  public static void main(String[] args){
    int x = 0;
    try(
      Scanner reader = new Scanner(System.in)
    ){
      while(x <= 0){
        try{
          System.out.print("Please input a positive integer: ");
          x = Integer.parseInt(reader.nextLine());
          if(x <= 0){
            System.out.println("Error: Negative Integer Detected!");
          }
        }catch(NumberFormatException e){
          System.out.println("Error: Integer Not Found!");
          reader.nextLine(); // bypass bad input and try again
        }catch(NoSuchElementException e){
          System.out.println("Error: No Input Found!");
        }catch(Exception e){
          System.out.println("Error: Unknown Input Error!");
          return; //probably can't recover, so stop executing
        }
      }

      System.out.println("You entered " + x);
      
    }catch(Exception e){
      System.out.println("Error: Unable to Open Scanner!");
    }
  }
}
```

There are several items in this code that help make it very bulletproof:

1. First, when the program opens a Scanner object, it uses a **Try With Resources** statement to make sure that it will be properly closed when we are done with it. As we've discussed, this is a good practice when handling input via files, but really any input object can be handled in this way.
2. The **Try With Resources** statement has a single `catch` block to handle any exceptions that arise from opening the Scanner. This prevents those exceptions from being thrown to the user. If we are opening a file, we'll also need to handle the FileNotFoundException here. 
3. Inside of the **While** loop, there is a second **Try-Catch** statement to handle errors that come from reading an individual input, such as an NumberFormatException or a NoSuchElementException. 
4. If an NumberFormatException is caught, we'll need to use `next()` to successfully read the next token from input before we continue, or else it will try to read the same thing again. 
5. In addition, that inner **Try-Catch** statement will also catch any generic Exceptions that might occur when reading input. In that case, we use the `return` keyword to stop executing the program, since it may be difficult to continue to read input in that case. Thankfully, since we are using a **Try With Resources** block, the Scanner object will be correctly closed for us automatically. In addition, any `finally` blocks would be executed before the program stops. 

{{% notice warning "Don't Exit Early!" %}}

We should not use `System.exit()` to exit our program, which you may find on many online resources. The `System.exit()` method directly ends the Java Virtual Machine, or JVM, without properly closing any resources or executing `finally` blocks. It can also make your code much more difficult to maintain and test. This can be very dangerous!

{{% /notice %}}

Of course, there are many things that can be done differently in this code, depending on our preferences and how we'd like our program to function. This is just one possible way to build useful code that handles several exceptions.