---
title: "Finally"
pre: "5. "
weight: 50
---

{{< youtube gW3Ntj0TqQc  >}}

[Video Materials]({{% relref "./video" %}})

When dealing with exceptions in our code, sometimes we have an operation that must be executed, even if the earlier code throws an exception. In that case, we can use the `finally` keyword to make sure that the correct code is executed.

## Finally

To understand how the `finally` keyword works, let's take a look at an example:

```java
import java.util.Scanner;
import java.lang.NumberFormatException;
import java.lang.IllegalArgumentException;

public class Finally{
  
  public static void main(String[] args){
    
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = Integer.parseInt(reader.nextLine());
      if(x < 0){
        throw new IllegalArgumentException("Input must be greater than 0!");
      }
    }catch(NumberFormatException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    }
    System.out.println("After Try");
  }
}
```

This program will read an integer from the terminal. If the integer is greater than or equal to 0, it will do nothing except print the "Finally Block" and  "After Try" messages. However, if the input is less than 0, it will throw an IllegalArgumentException. Finally, if the input is not a number, then an InputMismatchException will be thrown and handled. In each of those cases, it will also print the "Finally Block" message. 

Let's run this program a few times and see how it works. First, we'll provide the input "5":

```tex
$ java Finally
5
Finally Block
After Try
```

Here, we can see that the code in the `finally` block always runs when the program is finished executing the statements in the `try` block.

Let's run it again, this time with "-5" as the input:

```tex
$ java Finally
-5
Input must be greater than 0!
Finally Block
After Try
```

Here, we can see that it prints the error message caused by the IllegalArgumentException, then proceeds to the `finally` block. So, even if an exception is thrown while inside of the `try` block, the code in the `finally` block is **always** executed once the `try` block and any exception handlers are finished. 

Here's one more example, this time with "abc" as the input:

```tex
$ java Finally
abc
Error: Must input an integer!
Finally Block
After Try
```

Once again, we see that the code first handles the NumberFormatException, and then it will execute the code in the `finally` block. 

In a later chapter, we'll learn more about how to use the `finally` block to perform important tasks such as closing open files and making sure we don't leave the system in an unstable state when we handle an exception. 



