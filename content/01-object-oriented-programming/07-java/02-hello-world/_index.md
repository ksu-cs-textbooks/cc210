---
title: "Hello World"
pre: "2. "
weight: 20
---

{{% youtube vQeYP1dME7o %}}

[Video Materials]({{<relref "./video">}})

According to tradition, the first computer program that we cover in any language is a simple program called "Hello World!" The entire goal of the program is to demonstrate what it takes to create our first program from scratch in the language and get to the point where we can print the message of our choice to the screen. While that sounds very simple, it is actually a pretty big first step toward learning how to write our own programs. Let's get started!

{{% notice warning "Help!" %}}

If this is your first-time programming, it can be quite daunting to know where to get started. This guide will walk you through all the steps to create your first program. However, if you have any questions at all, don't be afraid to seek help. It's much easier to answer questions up front when they come up, instead of dealing with them down the road when you are truly lost. 

If you are a Kansas State University student, both your syllabus and the course canvas pages will have information on how to requests help, attend office hours, etc.  

{{% /notice %}}

## Some Terminology

In any programming language, there is a bit of terminology that we should discuss before diving in. Here are a few terms we'll want to be familiar with at this point:

1. _keyword_ - in any programming language, a _keyword_ is a word that has a special meaning. These words tell the program exactly what to do, and we cannot use these words as _identifiers_. Consult the [Java Language Keywords](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/_keywords.html) list to determine which words are keywords in Java.
1. _identifier_ - any class, method, or variable name is considered an _identifier_. 
1. _declaration_ - in a programming language, we use special lines to _declare_ that something exists. In this example, we'll see both a _class declaration_ and a _method declaration_. 
1. _body_ - following a declaration, we typically find the _body_ of the declared item. The body is enclosed by _braces_. 
1. _braces_ - in Java, we use _braces_ or _curly braces_, denoted by `{` and `}`, to enclose blocks of code. We'll use these to enclose both the _class body_ and _method body_. 

{{% notice info "Declaration vs. Definition" %}}

Formally, a **Declaration** associates an identifier with a program language element.

``` java
public class Pet; // a declaration
                  // tells the compiler that there will be a class called Pet
                  // Java will not support a class declaration this way
```

A **Definition** includes the complete information about the program element.  So for a class, a definition includes its body.

``` java
public class Pet {
     ... some code for the body // a definition
                                // like a declaration with all the info about the class
}
```
Some older languages (notably C) allowed things to be declared and used before they were defined.   However, Java does not support this style of coding.  As a result, Java documentation and developers tend to use "declaration" for both declaration and definition.

{{% /notice %}}

## Open a File

To begin, there should see a file named `HelloWorld.java` open in the panel to the left. If not, click on that file in the file tree to the far left to open it. Make sure that file is open for this example, since the file name must match in order for this process to work properly. 

Also, we should make sure that the file is completely empty before moving on. If there is any text currently in that file, take the time to delete it now.

We can also do these same steps on a computer with the Java Development Kit installed. Simply create a new, blank text file named `HelloWorld.java`.

## Create a Class

Java is an _object-oriented_ programming language. We'll discuss this more in detail in a later module, but for now we'll just need to know that Java requires all of our code to be placed in a `class`. So, at the very top of our file, we'll enter the following line:

```java
public class HelloWorld
```

That line called a _class declaration_ in Java. Let's break that line down and discuss what each part means:

1. `public` - this keyword is used to identify that the item after it should be publicly accessible to all other parts of the program. In a later module, we'll talk about these keywords, called _access modifiers_, and the impact they have on our programs. For now, we'll just use `public` whenever we need an access modifier, such as in a class declaration.
1. `class` - this keyword says that we are declaring a new class.
1. `HelloWorld` - this is an identifier that gives us the name of the class we are declaring. Java requires that the class name matches the filename that it is stored in, so we must store the `HelloWorld` class in a file named `HelloWorld.java`. 

Every Java program must contain at least one class declaration. In fact, each Java file we create will contain at least on class declaration, so we'll see this structure repeated very often.

{{% notice note "Too Much Information?" %}}

Unfortunately, when learning to program in Java, there are a few things that we'll just have to take for granted for now until we learn a bit more about how they actually work. Class declarations are a great example of this. For the next several modules, we'll just have to include a class declaration at the top of each file without understanding everything about them. As long as we make sure the identifier matches the name of the file, it should work just fine. In fact, in most of the later examples in this book, we'll have some sample code in each file that includes the class declaration. 

We're covering it in detail here just to make sure it is clear what is going on at first. It's always better to have too much information than not enough. 

{{% /notice %}}

## Class Body

Once we've completed our class declaration, we need to move on to the _class body_. The class body is where all of the information about the class is stored. In Java, we use _braces_ to enclose a block of code, such as a body. So, let's modify our file to look like the following example by adding an _opening brace_ `{` and a _closing brace_ `}` with a few empty lines in between. Instead of copy-pasting it, try to type it in yourself and see what happens!

```java
public class HelloWorld {
  
  
}
```

Did you notice how the editor in Codio automatically added a closing brace right after you typed the opening brace? That's the power of using a text editor that is tailored for programming. It should have also indented all of the lines between the two braces a bit, making it easier to read your code as we continue to fill it in. It may seem a bit jarring a first, but you'll quickly get used to it. We'll see it happen again later in this example.

{{% notice info "Style Guide" %}}

To make your code easier to read, many textbooks and companies use a _style guide_ that defines some of the formating rules that you should follow in your source code. However, this is a point of contention, and many folks disagree over what is the best format. These formatting rules do not affect the actual code itself, only how easy it is to read. 

For this book, most of the examples will be presented in a variant of the [K&R Style](https://en.wikipedia.org/wiki/Indentation_style#K&R_style) used by most Java developers, which places the opening brace on the same line as the declaration, but the closing brace is placed on a line by itself and indented at the same level as the declaration. The code inside will be indented by four spaces. 

Google provides a comprehensive [style guide](https://google.github.io/styleguide/javaguide.html) that is recommended reading if you'd like to learn more about how to format your source code. 

{{% /notice %}}

## Main Method

Inside of our class body, we must create a main method. A _method_ is a piece of code that performs an action in our program. Methods are sometimes referred to as _functions_ or _subroutines_ as well, but we'll use the term _method_. Each Java program have one class that contains at least one special method, called the _main method_, that tells the program where to start. So, let's modify our file to the left to look like this example:

```java
public class HelloWorld {
  
  public static void main(String[] args){
    
    
  }
  
}
```

We just added a _method declaration_ and _method body_ to our program! Let's look at some of the keywords we used here:

1. `public` - just like before, we are using the `public` access modifier to allow any part of our program to access this method.
1. `static` - the `static` keyword is one of the more difficult to understand, and even some experienced programmers struggle with it. In this example, we must use `static` since this is the main method, which must always be a static method. This is because we aren't using this method inside of an object, which we'll cover in a much later module. For now, every method we create will use a `static` keyword. 
1. `void` - this describes what kind of data this method should output. Since this is the main method, it cannot output anything to another part of the program, so we use the special `void` keyword to denote the fact that it doesn't output anything. (At least, it doesn't output anything to the rest of the program, but it may display things on the screen!)
1. `main` - this is another identifier that gives the name of the method. Since our program needs to have at least one main method, we need to use `main` as the name of this method. 
1. `(String[] args)` - following the method name is a section in parentheses that defines the inputs, or _parameters_, for the method. The main method must take in one parameter, an array of Strings. By convention, we use the identifier `args` as the name of that parameter. We'll learn more about parameters, Strings, and arrays, in a later module. For now, we'll just have to remember that the main method must have this exact set of parameters. 

Lastly, we included a second set of braces to enclose the method body. Notice how everything in the class body is indented slightly, making it easy to see the structure of the code. 

For now, we'll just have to memorize the fact that the main method in Java is declared using `public static void main(String[] args)`. As we move through this book, we'll slowly learn more about each part of that line and what it does, and it will make much more sense. 

## Saying Hello

Finally, we can write our code. The actual code of our program goes inside the main method's body, between the two braces. In the classic "Hello World!" example, we simply want to print the words "Hello World!" to the screen. So, let's modify our program one last time to look like this example:

```java
public class HelloWorld{
  
  public static void main(String[] args){
    System.out.println("Hello World");
    
  }
  
}
```

As you typed in that information, you might have noticed that Codio also added a second set of quotation marks `"`, just like it did with the braces earlier. This is another example of a programmer-friendly text editor at work!

Let's review what we just added to our program:

1. `System.out.println` - this line tells us that we'd like to use a method called `println` in the `System.out` [PrintStream](https://docs.oracle.com/javase/7/docs/api/java/io/PrintStream.html) object. Again, that means very little to us right now, but for now we'll need to know to use this method to print a line of text to the screen. Following the name of the method is a set of parentheses that accepts input to the method, which is what we'd like to have printed to the screen.
1. `"Hello World"` - by putting this in the parentheses after `System.out.println`, we are telling the `println` method in `System.out` to print `Hello World` to the screen. We have to enclose it in quotation marks `"` so that our program will treat it as a line of text and not more Java code. The values, or variables passed to a method are referred to as the method's *parameters*.
1. `;` - each line of code in Java must end with a semicolon `;`. This helps the compiler determine where one line of code ends and another begins. They really serve the same purpose as the period `.` in written English. However, periods are already used for other purposes in Java, so the semicolon became the standard symbol for the end of each line of code. 

That's it! That's all it takes to write our first program in Java. On the next page, we'll learn how to actually compile and run this program using Codio. 