---
title: "History of Java"
pre: "1. "
weight: 10
---

![Java Logo](/images/01-oop/1.3.j.1.javalogo.wikipedia.svg)[^1]

[^1]: File:Java_programming_language_logo.svg. (2018, May 26). Wikipedia. Retrieved 13:46, December 10, 2018 from https://en.wikipedia.org/w/index.php?title=File:Java_programming_language_logo.svg&oldid=872323259.

The Java programming language was originally developed by Sun Microsystems starting in the early 1990s as _Oak_, a new programming language designed to build upon the ideas of C++. Oak would be object-oriented and include a garbage collector, both things that were seen as weak points of the C++ language at that time. In addition, it would be designed to be portable across many different types of devices. 

Eventually, the language was renamed to _Java_, and was originally used develop applications that could run on a website. These Java _applets_ for the web were very popular in the late 1990s and early 2000s, but most of them have since been replaced by JavaScript code that can run directly in the web browser. 

{{% notice info "Java vs. JavaScript" %}}

While Java and JavaScript may share a common-sounding name, they are in fact completely unrelated languages. JavaScript was originally named _Mocha_ and then _LiveScript_, but was rebranded to JavaScript in 1995. That move was widely regarded as a marketing ploy to take advantage of the fact that Java was the most popular new language at the time. 

In fact, today JavaScript is just one of many implementations of a language standard known as _ECMAScript_. However, the name confusion still exists.
 
{{% /notice %}}

Since that time, Java has grown into its own fully-fledged programming language, and has indeed met its goal of being highly portable. Java today can run on most major computer operating systems through the use of the _Java Runtime Environment (JRE)_ and _Java Virtual Machine (JVM)_. In addition, the Android mobile operating system uses the Java programming language, and it has been used on many web servers and in consumer electronics. 

For software developers, the _Java Development Kit (JDK)_ provides easy access to all of the tools needed to develop programs using the Java language. Once a program is developed, the Java compiler converts the program to _Java bytecode_, which is similar to machine-code. That Java bytecode can then be run on any compatible platform using the JVM. This allows Java to achieve true portability. The only part of the system that must be specific to the computer's hardware and operating system is the JVM, while Java bytecode can be used on any system with a compatible JVM installed. 

Today, the OpenJDK project handles all development of the Java platform, and the language and all supporting code is free and open source. 

If none of these features in the history of Java make any sense at this point, that's OK! It's difficult to describe the differences between programming languages without getting technical. However, that is a good thing for us, since nearly every programming language can be used to create the programs we'll be writing in this course. The differences aren't really important at this point!

Now that we've covered the basics, let's get right down to it and create our first program in Java!

## Resources

* [Java Homepage](https://www.java.com/en/)
* [OpenJDK](http://openjdk.java.net/)
* [Java Documentation](https://docs.oracle.com/en/java/)