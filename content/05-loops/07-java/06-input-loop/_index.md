---
title: "Input Loops"
pre: "6. "
weight: 60
---

<!-- TODO Add Video -->

Now that we know how to use loops, let's discuss a common structure for reading and parsing user input from the terminal using a loop.

### Reading Terminal Input

In many of our prior projects, we've seen the `Scanner` class used to read input from the keyboard's input stream, which is `System.in` in Java. Typically we use code similar to this:

```java
import java.util.Scanner;

public class ReadInput {

    public static void main(String[] args){
        // Create the Scanner object to read from the terminal
        Scanner scanner = new Scanner(System.in);

        int x = scanner.nextInt();
        double d = scanner.nextDouble();

        System.out.println(x + " + " + d + " = " + (x + d));
    }
}
```

Let's look at some of the important lines of code in this short example:

* `import java.util.Scanner;` - this line at the very top of our program is an **import statement**. It tells Java that we'd like to import, or use, the `Scanner` class from the `java.util` library, which is part of the standard Java Development Kit (JDK). These lines must be at the top of our file, before any class declarations. We'll learn more about importing and using library classes a bit later in this course.
* `Scanner scanner = new Scanner(System.in)` - this line serves two purposes. First, it creates a new instance of a `Scanner` object, which is stored in the variable `scanner`. Notice that these names are case-sensitive! The capitalized `Scanner` is the name of the class, which in this case is used like a data type similar to `int` or `double`. The lowercase `scanner` is the variable name where the object created from that class is stored. We'll learn about objects and classes a bit later in this course. The last part `new Scanner(System.in)` creates a new Scanner object and tells it to read input from the `System.in` stream, which is the connected to the keyboard in the terminal.
* `scanner.nextInt()` - this method will read the next piece of input from the keyboard and try to convert it to an integer. If it can, it will store it in the variable `x`. However, if the next piece of input is not an integer, this will cause an error and crash the program. We'll learn how to catch and handle these errors a bit later in this course, but for now we'll have to assume that our users are providing input that matches the expected structure.
* `scanner.nextDouble()` - similar to the previous line, this will read the next piece of input and try to convert it to a floating-point value. If it can, it will store it in the variable `d`. 

Of course, there are much more advanced ways to use a `Scanner` in Java. We'll learn more in a later chapter, or we can always refer to the Java Documentation for the [Scanner](https://docs.oracle.com/javase/8/docs/api/java/util/Scanner.html) class.

### Reading Multiple Lines

Many times, we want our programs to be able to read multiple lines of input, and to continue to read input until the end of the stream is reached. In that case, we can use a **While** loop and a few different methods in the `Scanner` class to accomplish this.

Consider this code example:

```java
import java.util.Scanner;

public class ReadManyLines {

    public static void main(String[] args){
        // Create the Scanner object to read from the terminal
        Scanner scanner = new Scanner(System.in);

        int countLetters = 0;
        int countLines = 0;

        // Repeat while the Scanner thinks there is another line to be read
        while(scanner.hasNextLine()){
            // Read the next line of input
            String input = scanner.nextLine();
            
            // Check to see if the line is empty after removing all leading and trailing whitespace
            if (input.trim().length() == 0){
            
                // If the line is empty, break out of the while loop
                break;
            }
            
            // parse the line of input and perform the calculations needed
            countLetters += input.length();
            countLines++;
        }

        // all input has been read at this point
        System.out.println("I read " + countLetters + " characters of input across " + countLines + " lines");
    }
}
```

This program will read input from the terminal until no more input is provided, and it will count the total number of lines and characters read from the terminal's input stream. To do this, it uses a few new methods of the `Scanner` class:

* `scanner.hasNextLine()` - this method will return `true` if there is more input to be read from the input stream. So, we use this in the **While** loop to repeat until there is no more input to be read.
* `scanner.nextLine()` - this method reads an entire line of input from the input stream. It will keep reading characters until it reaches a newline character `\n`. Remember that when the user presses the <kbd>ENTER</kbd> key on a keyboard, that will add a newline character `\n` to the keyboard's input stream, signalling the end of a line of input.

This works well in many situations, but there is one important thing we must remember - the keyboard input stream `System.in` is an **infinite stream**! This means that is never ends, and the `scanner.hasNextLine()` method will _always_ return `true` when reading input from the terminal. 

So, how do we get our program to end? In most cases, we will simply add an **If** statement inside of the loop to check and see if the line of input is empty, and then break out of the loop if it is. In this code, we use the Boolean expression `input.trim().length() == 0` to check and see if the String `input` is empty. We'll learn more about these string methods in a later part of this course. 

### Avoiding Dangling Newlines

This new method of reading input, which uses `scanner.nextLine()` to read an entire line of input instead of `scanner.nextInt()` or `scanner.nextDouble()` to just read a single element from the input, comes with one major caveat that developers must be aware of - the dangling newline.

Consider this code:

```java
import java.util.Scanner;

public class DanglingNewline {

    public static void main(String[] args){
        // Create the Scanner object to read from the terminal
        Scanner scanner = new Scanner(System.in);

        // Repeat while the Scanner thinks there is another line to be read
        while(scanner.hasNextLine()){
            // Read the next line of input
            String name = scanner.nextLine();

            // Check to see if the line is empty after removing all leading and trailing whitespace
            if (name.trim().length() == 0){
            
                // If the line is empty, break out of the while loop
                break;
            }

            // Read an integer from input
            int age = scanner.nextInt();
            System.out.println("Greetings " + name + "! Your age is " + age);
        }
    }
}
```

This program will read the name and age of a user from input, one per line. So, let's assume that we are providing the following input:

```
Willie
42
Wildcat
37
```

When we run this program, however, we see that an error occurs:

![Dangling Newline](/images/05-loop/dangling_newline.png)

Why did this happen? Let's look at the stream that would be read by the program, complete with the newline characters:

```
Willie\n42\nWildcat\n37\n
```

Now, let's step through the program and check all the `Scanner` methods that read the input to see where the error occurs! First, the `scanner.hasNextLine()` method will return `true` since the stream still has input to be read. Next, the `scanner.nextLine()` method will read the next line of input, up to and including the newline `\n` characater. So, it will read `"Willie"` from the stream and store it in `name`, and then remove it and the following newline. Now we have this in the stream:

```
42\nWildcat\n37\n
```

Good so far! After that, the `scanner.nextInt()` method will try to read the next item in the stream and convert it to an integer. It sees the characters `"42"` followed by a newline, and it knows that it can convert `"42"` to an integer, so it will read those characters and store the value `42` in the `age` variable. However, the `nextInt()` method **does not** remove the newline character from the stream. So, we'll be left with this content in the stream:

```
\nWildcat\n37\n
```

Here's where things go wrong. The `scanner.hasNextLine()` method will still return `true` since there is input to be read. So, the `scanner.nextLine()` method will read input until it reaches a newline character `\n`. In this case, it sees that immediately, so it will store the empty string `""` in the `name` variable and then remove the newline from the stream. So, we are left with this content in the stream.

```
Wildcat\n37\n
```

This means that, when the `scanner.nextInt()` method is called, the first thing it reads is not a number, so it throws an `InputMismatchException` and crashes the program!

This happens because had a **dangling newline** that was left in the input stream. To fix this, the easiest way is to always read an entire line of input, and then use other methods to parse and convert that line as needed. In general, we want to avoid mixing the `Scanner` methods that read entire lines and the methods that just read individual elements of input. In most cases, we should use one or the other.

In this case, we can change the `scanner.nextInt()` to `Integer.parseInt(scanner.nextLine())` to read the entire next line of input and then convert it to an integer:

```java
import java.util.Scanner;

public class DanglingNewline {

    public static void main(String[] args){
        // Create the Scanner object to read from the terminal
        Scanner scanner = new Scanner(System.in);

        // Repeat while the Scanner thinks there is another line to be read
        while(scanner.hasNextLine()){
            // Read the next line of input
            String name = scanner.nextLine();

            // Check to see if the line is empty after removing all leading and trailing whitespace
            if (name.trim().length() == 0){
            
                // If the line is empty, break out of the while loop
                break;
            }

            // Read an integer from input
            int age = Integer.parseInt(scanner.nextLine());
            System.out.println("Greetings " + name + "! Your age is " + age);
        }
    }
}
```

With that change in place, the program will run correctly!

![Dangling Newline](/images/05-loop/dangling_newline2.png)

### Prompting for Input

Lastly, it is usually considered good practice to include prompts that tell the user what kind of input is expected. For example, we can update the previous code to include some prompts, using the `System.out.print()` method:

```java
import java.util.Scanner;

public class DanglingNewline {

    public static void main(String[] args){
        // Create the Scanner object to read from the terminal
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter a name: ");

        // Repeat while the Scanner thinks there is another line to be read
        while(scanner.hasNextLine()){

            // Read the next line of input
            String name = scanner.nextLine();

            // Check to see if the line is empty after removing all leading and trailing whitespace
            if (name.trim().length() == 0){
            
                // If the line is empty, break out of the while loop
                break;
            }

            System.out.print("Enter an age as an integer: ");
            // Read an integer from input
            int age = Integer.parseInt(scanner.nextLine());
            System.out.println("Greetings " + name + "! Your age is " + age);

            System.out.print("Enter a name: ");
        }
    }
}
```

Notice that the first prompt has to be printed before the `while` loop - this is because the `scanner.hasNextLine()` method will wait until a line of input has been provided before it allows the program to continue, even if we haven't actually read that line of input yet. So, we have to print our prompt before checking for a line of input to be read from the terminal.

While this is considered best practice in the real world, we typically **will not** include these prompts for input in our programs in this course. The major reason for removing the input prompts is to ensure that the automated grader is just reading the output produced by your program and not the prompts for input. 

Without this change, we'd have to be very careful to make sure that our input prompts _also_ perfectly matched what the automated grader was expecting. Since we really want the focus to be on the output produced and not the input prompts, we've made the decision to simply not include input prompts in our programs in this course. 

{{% notice warning "My Program is Stuck" %}}

There are some instances where it may look like your program has stopped working, especially when dealing with loops and user input. If that happens, try these steps:

1. Try typing on the keyboard. If text appears in the terminal, that means your program is just waiting for you to provide input.
2. If no text appears when you type on the keyboard, try the keyboard shortcut <kbd>CTRL</kbd> + <kbd>C</kbd> (or <kbd>CMD</kbd> + <kbd>C</kbd> on a Mac) to interrupt the program.
3. If that does not work, close the terminal window or tab where the program is running. That should stop any programs running in that terminal.
4. If Codio or your system appears to still be running slow, as a last resort try restarting the computer where the program was running. In Codio, click the **Project** menu and choose **Restart Box...** to restart the underlying Linux system where your program is running.

{{% /notice %}}

