---
title: "Common Exceptions & Errors"
pre: "1. "
weight: 10
---

Before we learn about how to detect and handle exceptions in Java, let's review some of the common exceptions and errors we may see in our programs. Each of the headers below is the name of an exception in Java, which is represented by a particular class in the Java programming language. 

## Exception

[Java 8 API Reference](https://docs.oracle.com/javase/8/docs/api/java/lang/Exception.html)

Every exception that can be handled in Java is a subtype of the Exception class. So, when we aren't sure which type of exception to expect, we can always use the Exception class to make sure we catch all of them.

## ArithmeticException

[Java 8 API Reference](https://docs.oracle.com/javase/8/docs/api/java/lang/ArithmeticException.html)

An ArithmeticException can occur whenever our program attempts to perform a calculation that would result in an undefined value. In Java, this is the case when we divide by 0. So, the following code would generate an ArithmeticException:

```java
int a = 10;
int b = 0;
int c = a / b; // throws ArithmeticException
```

However, when using floating point values, the result is different:

```java
double a = 5.0;
double b = 0.0;
double c = a / b; // Infinity
```

In short, this is because the standard for floating point numbers defines Infinity as `1.0 / 0.0`, so it is a valid value according to the standard definition for floating point numbers. 

## ArrayIndexOutOfBoundsException

[Java 8 API Reference](https://docs.oracle.com/javase/8/docs/api/java/lang/ArrayIndexOutOfBoundsException.html)

An ArrayIndexOutOfBoundsException happens when we try to access an array index that does not exist. Here's a great example:

```java
int[] array = new int[5];
array[5] = 10; // throws ArrayIndexOutOfBoundsException
```

In this example, we are trying to access the 6th element in the array, which is at array index 5. However, since the size of the array is only 5, we'll get an ArrayIndexOutOfBoundsException when we try to execute this code since there is no 6th element.

## StringIndexOutOfBoundsException

[Java 8 API Reference](https://docs.oracle.com/javase/8/docs/api/java/lang/StringIndexOutOfBoundsException.html)

Similar to the ArrayIndexOutOfBoundsException above, a StringIndexOutOfBoundsException occurs when we try to access an invalid index of a character in a string. Here's a couple of examples:

```java
String s = "abc";
char c = s.charAt(3); // throws StringIndexOutOfBoundsException
char d = s.charAt(-1); // throws StringIndexOutOfBoundsException
```

In this example, we are first trying to access the character at index 3. Just like with arrays, that would be the 4th character in the string. Since the string only contains 3 characters, it would result in an exception. Likewise, we cannot access a negative character index in Java, so it would also cause this exception to be thrown.

## FileNotFoundException

[Java 8 API Reference](https://docs.oracle.com/javase/8/docs/api/java/io/FileNotFoundException.html)

This exception occurs when the program is trying to open a file that does not exist. This is one of the more common errors that programmers must deal with when using files for input, and it is relatively simple to correct. In most cases, we can simply ask the user to provide another file. Here's an example of some code that may cause this exception:

```java
String filename = "";
Scanner scanner = new Scanner(new File(filename)); // throws FileNotFoundException
```

In this case, we are providing a blank filename, which causes the program to throw a FileNotFoundException. 

## IOException

[Java 8 API Reference](https://docs.oracle.com/javase/8/docs/api/index.html?java/io/IOException.html)

An IOException is thrown whenever the program encounters a problem performing some input or output operation. This can be due to an error in the file it is reading from, a bug in the underlying operating system, or many other problems that can occur while a program is reading or writing data. 

For example, reading input using a Scanner object can result in an IOException, both when reading from the terminal using `System.in`, or when reading from a file. So, in general, anytime we are reading input from any source, we must always consider the fact that an IOException can occur. 

Thankfully, these errors are very rare on most modern computers, but they are something that can be dealt with. 

## NumberFormatException

[Java 8 API Reference](https://docs.oracle.com/javase/8/docs/api/java/lang/NumberFormatException.html)

A NumberFormatException is used in Java when we try to convert a string to a number but it doesn't work. See the sample code below to see how this could occur:

```java
String s = "abc";
int x = Integer.parseInt(s); // throws NumberFormatException
double d = Double.parseDouble(s); // throws NumberFormatException
```

This exception is really useful when we are asking the user to provide a number that fits a particular format. By detecting this exception, we know that the user entered an invalid number, so we may have to prompt the user for another input. 

## NoSuchElementException

[Java 8 API Reference](https://docs.oracle.com/javase/8/docs/api/java/util/NoSuchElementException.html)

A NoSuchElementException happens when a Scanner object tries to read input when there is no input available to read. 

```java
Scanner reader = new Scanner(System.in);
int x = reader.nextInt(); // throws NoSuchElementException if the input is empty;
```

## IllegalArgumentException

[Java 8 API Reference](https://docs.oracle.com/javase/8/docs/api/java/lang/IllegalArgumentException.html)

This exception is typically used by developers to indicate that a particular input to a program is invalid. Many developers also use it in their own code as a custom exception. 


## AssertionError

[Java 8 API Reference](https://docs.oracle.com/javase/8/docs/api/java/lang/AssertionError.html)<br>
[Programming with Assertions](https://docs.oracle.com/javase/8/docs/technotes/guides/language/assert.html)

An AssertionError happens when our code reaches an _assertion_ that fails. An assertion is a check added by the programmer to verify that a particular situation doesn't occur in the code, such as a variable being negative or an array being too large. Java supports the use of a special keyword `assert` that can be used to add these assertions to our code. By default, the Java runtime environment ignores any `assert` keywords, but they can easily be enabled by adding `-ea` as an argument to the `java` command when running a program. This is a helpful step when debugging a new application. We'll learn more about assertions and how they can be used effectively in a later chapter.

For now, here's a quick example of an assertion that would produce an AssertionError:

```java
int x = 5;
int y = 3;
assert x + y < 7; // throws AssertionError if enabled
```

## Errors

Beyond exceptions, there are a few unrecoverable errors that may occur in our Java code. Recall that errors are special types of exceptions that should not be handled by our programs, and should instead be allowed to cause our programs to crash. Some examples are:

* StackOverflowError - occurs when we have used up all of the available stack space in the Java virtual machine .. this usually happens with because of an infinite loops
* OutofMemoryError - occurs when we have used up all of the available system memory   ... this rarely happens but again can be caused by an  infinite loop

In addition, the Java compiler helps us detect many other errors, such as syntax and type errors that would cause our code to be unusable. Other languages, such as Python, have to deal with these errors at runtime, so there are many more unrecoverable errors in that language compared to Java. 

### References:

* [Lesson: Exceptions](https://docs.oracle.com/javase/tutorial/essential/exceptions/index.html) from Oracle's Java Tutorials
* [Exceptions in Java](https://www.geeksforgeeks.org/exceptions-in-java/) from GeeksforGeeks
* [Built-in Exceptions in Java with Examples](https://www.geeksforgeeks.org/built-exceptions-java-examples/) on GeeksforGeeks