---
title: "Java Hello World"
pre: "2.J. "
weight: 20
date: 2019-02-04T10:53:26-05:00
hidden: true
---

{{< youtube vQeYP1dME7o >}}

#### Video Script

Let's go through the process of writing our first program in Java using Codio.

First, we'll need to make sure we have the correct file open. For this example, we are using a file named `HelloWorld.java`. It should already be open in the panel on the left for us. If not, we can always find it in the file tree to the far left.

To begin, we'll need to create a class inside of this file using a _class declaration_. So, let's type

```java
public class HelloWorld
```

into the file. The text on this page describes the special words `public` and `class` that we've included in this line and what they mean. They are some of the many _keywords_ in Java, or words which are used to tell the program what to do. Make sure you take the time to read that information carefully.

However, one very important thing to know is that the name of the class, in this case `HelloWorld`, must be exactly the same as the name of the file it is stored in. So, since our file is named `HelloWorld.java`, we must create a class named `HelloWorld` in that file.

Following the _class declaration_, we must also have a _class body_. To do this, we use two curly braces `{ }`. This just tells Java that anything between these two curly braces is considered to be part of the `HelloWorld` class.

Next, we need to create a _main method declaration_. This tells our program what code to run when it is first executed. So, let's add the following code to our file

```java
public static void main(String[] args){

}
```

Once again, you can refer to the text on this page for a longer description of what each of these words mean. We'll see this line of code in every Java program we create, so it'll become very familiar.

Also, we've used another set of curly braces after the _main method declaration_ to enclose the _method body_, just like we did for the _class body_ earlier.

Finally, we can add the code to print "Hello World!" to the screen:

```java
System.out.println("Hello World");
```

This line tells us to use the `println` or "print line" method that is stored in the `System.out` object in Java. We won't learn much about objects for several chapters, so don't worry about that part right now. We'll be sure to explain it clearly when we get to that point.

For now, we just need to know that anything inside of the parentheses `( )` will be displayed to the user. Since we want to print out actual text, we also make sure that it is in quotation marks `" "` so that Java will know that it is meant to be treated as text and not more code.

Finally, notice that this line ends in a semicolon `;`. Java, as well as many other programming languages, use a semicolon at the end of each line of code. This helps Java read our code a little bit easier, and also helps make our programs easier to understand in case we accidentally delete a line or merge several lines together.

That's all it takes! On the next page, we'll learn how to use the Java compiler to actually compile and run this program. So, when you are ready, click the "Next" button to move on to the next page.
