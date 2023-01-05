---
title: "Documenting Code"
pre: "6. "
weight: 60
---

As we continue to write larger and more complex programs, it is important to remember that we can include comments and documentation in our code. Comments are lines of text in our program's source code that are ignored by the compiler or interpreter, allowing us to add information to the program beyond the code itself. 

These help explain our code to anyone who might read it, but can even be useful to help us remember exactly how it works or what it does, especially if we end up coming back to a program written a long time ago that we do not remember very well.

## Single Line Comments

As we've seen before, we can add single-line comments to our Java programs using two forward slashes `//` before a line in our source file:

```java
// this is a comment
int x = 5;

// this is also a comment
boolean b = true;
```

## Multiple Line Comments

Java also includes the ability to add a comment that spans multiple lines, without requiring each line to be prefixed with forward slashes. Instead, we can use a forward slash followed by an asterisk `/*` to start a comment, and then an asterisk followed by a forward slash to end it `*/`, as shown below:

```java
int x = 5;

/* This is a multi line comment
it can span multiple lines

and even blank lines */

int y = 10;
```

## Documentation

Finally, Java also includes a secondary type of comment that spans multiple lines, specifically for creating documentation. Instead of a single asterisk, we use a double asterisk after the forward slash at the beginning `/**`, but the ending is the same as before `*/`. 

In addition, these comments typically include an asterisk at the beginning of each line, aligned with the first asterisk of the start of the comment. Thankfully, most code editors will do this for us automatically, including Codio!

These comments are specifically designed to provide information about classes and methods in our code. Here's a quick example, using the `IntTuple` class developed earlier in this module:

```java
/**
 * Represents a tuple containing two integer values. 
 * 
 * @author Test Student
 * @version 1.0
 * @since 2019-01-01
 */
public class IntTuple{
  
  public int first;
  public int second;
  
  /**
   * Constructs a new IntTuple object.
   * 
   * @param one     the first element in the tuple
   * @param two     the second element in the tuple
   */
  public IntTuple(int one, int two){
    this.first = one;
    this.second = two;
  }
}
```

Once we've written this documentation in our code, Java includes a special tool called **Javadoc** that will generate HTML files that describe what our code does. In fact, the Java API files, such as the one for [Scanner](https://docs.oracle.com/javase/8/docs/api/java/util/Scanner.html), are generated using this tool!

For more information about writing comments for the Javadoc tool, as well as some great examples, consult the [documentation](https://www.oracle.com/technetwork/java/javase/documentation/index-137868.html).