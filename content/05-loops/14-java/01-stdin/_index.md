---
title: "Reading from Stdin"
pre: "1. "
weight: 10
---

<!-- {{% youtube KSRvAtEqPbk %}} -->

<!--[Video Materials]({{<relref "./video">}}) -->

<!-- TODO Update Video -->

Now that we've learned how to use conditional constructs, it might be helpful to understand a bit about how to get input from our users directly in our program. Each programming language provides several ways to receive user input, and each one comes with its own pros and cons. 

We've already seen some examples of how to get user input via  command line arguments.  Let's examine how to make the a program interactive while it runs by using `stdin`;  we may refer to this as getting input from the keyboard or terminal.

## Reading StdIn

The most common class used to read `stdin` is `Scanner` from the `java.util` library.  To use a `Scanner` we must 
* Import it.  By convention, `import` statements go at the top of the file, before the class-definition.
* Instantiate an instance of `Scanner` (create an variable of 'type' Scanner) connecting it to `stdin` (more on instantiation in module 7)
**  `Scanner reader = new Scanner(System.in);`
* Use the `.nextLine()` method each time we want to get a line of input from the terminal.
** `.nextLine()` *always* produces (returns) a `String`


```java
// Load required classes
1   import java.util.Scanner;
2
3   public class Demo{
4  
5     public static void main(String[] args){
6    
7       // Scanner variable
8       Scanner reader = new Scanner(System.in);
9       String xStr = reader.nextLine();
10      int x = Integer.parseInt(xStr);
11      System.out.println("xStr is a String equal to /""+xStr+"/"");
12      System.out.println("x is the converted integer value "+ x);
13
14    }
15  }
```

Let's discuss this  code in detail to understand how it works. 

Line 1 tells Java to load the Scanner class.  We'll learn more about importing classes later in this course as we build larger programs. For now, we'll just need to know that we must import this class before we can use it.

{{% notice warning "Don't Forget to Import" %}}

If we omit this line, the compiler will give us an error similar to the following:

```tex
error: cannot find symbol
    Scanner reader = new Scanner(System.in);
    ^
  symbol:   class Scanner
  location: class Demo
```

So, if we see that error, we know that we forgot to add the correct `import` statements at the top of the file. 

{{% /notice %}}

Lines 3 and 5 are the class and main-method declarations.
Line 8 creates the Scanner variable and attaches it to `System.in` (StdIn).
Line 9 uses the Scanner to read a line of input and assign that string to the variable `xStr`.
Line 10 converts `xStr` into an int and assigns the value to the variable `x`.  IF `xStr` cannot be converted to an inr Java will throw a `NumberFormatException`.
Lines 11 and 12 print stuff out.

Each time you call `reader.nextLine()` the program will go to the terminal and wait for input.  See if you can modify Demo to accept a second number as a floating point, convert it to a double and print it out.

{{% notice info "Casting Strings to Numeric Types" %}}

Variables with a primitive data type do not have a "full fledged" set of methods because they are not objects.  They are holdovers from pre-object oriented languages like C; the early Java compilers were all written in C.

To make up for this Java has a bunch of wrapper classes: Integer, Double, etc.  One of the extremely useful things the wrapper classes provide are ways to convert from a String to the appropriate primitive type with their "parse" methods.

{{% /notice %}}

#### Naked Prompts (usually avoided)

You'll note that Demo.java does not have a  prompt for input.

![no prompt](/images/05-loop/javaNakidPrompt.png)

This is called a naked prompt.  There is no indication to the user that input is expected.  This is generally considered a bad practice.  Better would be a user prompt.

![user prompt](/images/05-loop/betterPrompt.png)

HOWEVER, because you are graded on exactly matching expected output, we have chosen to use "naked prompts" so you don't waste valuable time hunting for typos in the input prompts.

This means you program may appear to "hang".  When this happens, try typing in some input.

{{% notice note "My Program is Hung" %}}

With the introduction of reading from standard input and loops; it may appear that your program is "hung". When this happens:

1. First try entering a string, if text appears in the terminal, your program is not hung, it is waiting for input.
2. Try forcing a keyboard interrupt: cntrl-C on windows and cmd-. (command 'period') on mac at the time of this writing.
3. Close the terminal tab.
4. Close the Codio tab.

{{% /notice %}}

Of course, there are much more advanced ways to use a `Scanner` in Java. We'll learn more in a later chapter, or we can always refer to the Java Documentation for the [Scanner](https://docs.oracle.com/javase/8/docs/api/java/util/Scanner.html) class.

