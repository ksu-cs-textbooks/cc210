---
title: "Making Strings"
pre: "1. "
weight: 10
---

String variables in Java can be created just like any other variable type we've seen so far. To declare a string variable, we can use the following syntax:

```java
String s;
```

Notice that the keyword `String` in Java is capitalized. This is because we are actually referring to a class named `String` that is a part of the Java programming language and not a simple data type. This tends to cause new programmers quite a bit of problems, so it is important to remember that this particular data type is capitalized in Java.

We can of course then instantiate our variable by assigning a value to it, as in this example:

```java
String s;
s = "This is a string!";
```

The text itself must be placed in double quotation marks as seen in this example. This allows the Java compiler determine what part of the source code file should be treated as text instead of code. 

As always, we can do both steps on a single line as well:

```java
String s = "This is a string!";
```
{{% notice info "Special Characters" %}}

Java supports several special characters that can use in our strings to represent specific symbols. For example, we know that strings must be surrounded by double quotation marks. So, what if we want to include quotation marks in our string? 

We can use `\"` as a special character to represent a double quote in our string. Here's an example:

```java
String s = "This is \"a quote\"";
System.out.println(s);
```

This code segment would produce the following output:

```tex
This is "a quote"
```

There are several special characters we can include in our strings. Here are a few of the more common ones:
* `\'` - Single Quotation Mark (usually not required)
* `\"` - Double Quotation Mark
* `\n` - New Line
* `\t` - Tab
* `\\` - The backslash

{{% /notice %}}

Character variables are created using the `char` data type in a similar way:

```java
char c;
c = 'a';

char d = 'b';
```

In Java, characters are placed in single quotation marks as seen above. 

Finally, we can also create a string from an array of characters, as in this example:

```java
char[] c = {'H', 'e', 'l', 'l', 'o', '!'};
String s = new String(c);

System.out.println(s); // Hello!
```

Here, we are using the `new` keyword to create a new String object. Then, we are using the variable `c` as input to the that object's _constructor_. We'll learn more about creating objects and using constructors in a later chapter, but it is important to know that it is possible to create a string from an array of characters quickly. 

### Reference

[Java Strings](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)