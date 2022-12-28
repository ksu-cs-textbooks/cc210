---
title: "Debugging"
pre: "4. "
weight: 40
---


<!-- {{% youtube 1aeEZ4Z-jdc %}} -->
<!-- TODO Redo Video -->
<!-- Video Materials]({{<relref "./video">}}) -->

Of course, when developing a computer program, there are always times when things don't quite work the way we'd like them to. Let's review a few of the common errors and how to solve them. 

## Compiler Issues

The Java Compiler is usually the source of most of our woes when first learning how to write programs in Java. The compiler expects the source code to be correctly formatted, or else it won't be able to generate the Java bytecode for our program. Let's modify our `HelloWorld.java` file to include some errors, just to see exactly what the error messages from the compiler are like.

### Missing Braces

First, let's replace everything in `HelloWorld.java` with the following code:

```java
public class HelloWorld{
  
  public static void main(String[] args){
    System.out.println("Hello World");
    
  
}
```

{{% notice info "Spot the Error" %}}

Before compiling that program, can you spot the error? Being able to find errors in code without using a compiler will definitely help you develop programs much faster. It is just like being able to spell words correctly without using a spell-checker. It makes everything go just a bit more smoothly.

In each of the examples in this section, take a minute and see if you can spot the error before running it through the compiler. The quiz in this module includes a few questions that require you to spot the error in a piece of code, so this is great practice for later!

{{% /notice %}}

Once we've updated that file, we can compile it using the using the terminal. When we do, we should see output similar to this:

![Java Missing Closing Brace](/images/01-oop/1.3.j.4.missingbrace.png)

That error message gives us quite a bit of information. The first part, `java/HelloWorld.java` tells us which file the error is in, which is handy later on when we start working in programs that include multiple source code files. Following that, we see a `7` after the file name, which tells us that the error is on or around line 7. However, that doesn't always mean that we'll need to edit something at line 7 to fix the error; it just means that the Java Compiler realized there was an error when it reached line 7. Sometimes, we must make a change elsewhere in the file to resolve the issue. 

After that, we'll see the actual error message, which in this case is `error: reached end of file while parsing`. That may not seem very helpful at first, but it actually gives us an important clue. 

If we look at the code above, we'll notice that it is missing the second closing brace `}` at the end of the file. So, the compiler was expecting to see one more closing brace, but didn't find it. So, to fix that, we'll just need to add one more closing brace at the end of the file, and it should work just fine.

### Missing Semicolon

Here's another example we can try:

```java
public class HelloWorld{
  
  public static void main(String[] args){
    System.out.println("Hello World")
    
  }
}
```

When we try to compile this file, we should get output similar to the following:

![Java Missing Semicolon](/images/01-oop/1.3.j.4.missingsemicolon.png)

In this example, the output is really helpful. It clearly shows us exactly where in our code we forgot to include a semicolon. By adding that symbol where indicated, we can solve the problem.

## Runtime Issues

Of course, there are some problems that the compiler may not catch. These are known as _runtime errors_, since they happen at the _time_ we _run_ our programs. They can be especially tricky to deal with, but thankfully they are usually quite rare. 

### Incorrect Main Method

Let's look at one more example:

```java
public class HelloWorld{
  
  public static void main(String args){
    System.out.println("Hello World");
    
  }
}
```

This time, the program actually compiles! However, when we try to actually run the file, we'll get an error similar to this one:

![Java Incorrect Main Method](/images/01-oop/1.3.j.4.mainmethod.png)

This is because we accidentally forgot the square brackets `[]` in the main method declaration. It should be `public static void main(String[] args)`, as the error message so helpfully tells us. So, it is important to remember that our programs may still have errors, even if the compiler doesn't find any. 

{{% notice note "Break Stuff" %}}

Now that you've learned a bit about how to debug compiler errors, let's see if you can figure out how to cause one! Modify `HelloWorld.java` in a way that causes the compiler to output the following error message: 

`error: class WrongClass is public, should be declared in a file named WrongClass.java`

{{% /notice %}}
