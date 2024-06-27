---
title: "Methods"
pre: "2. "
weight: 20
---

{{< youtube 5LOXCJZAS40  >}}

{{% notice note "Pseudocode in Video" %}}

The video above uses pseudocode to introduce the concept of methods. We are transitioning away from using pseudocode in this course. The intent of the video should be clear, but don't worry too much about the actual syntax of the examples in this video. We'll use Java code elsewhere in the text.

{{% /notice %}}

<!-- TODO Update Video-->

[Video Materials]({{% relref "./video" %}})

The answer lies in the use of _methods_ in our code. A _method_ is a piece of code that can be used by our program to perform an action. However, the biggest benefit of using a method comes from the fact that we can use methods multiple times, helping us avoid repeated code in our programs. We can also provide input to our methods and receive output from our methods, allowing a single method to perform work on a wide variety of data.

Let's look at an updated version of our previous example - a program that writes the same output to multiple files:

```java
public static void main(String[] args){
    outputToFile("file1.txt");
    outputToFile("file2.txt");
    outputToFile("file3.txt");
    outputToFile("file3.txt");
}

public static void outputToFile(String filename){
    BufferedWriter writer = new BufferedWriter(new FileWriter(filename));
    writer.write("This is the first line of " + filename);
    writer.newLine();
    writer.write("This is the end of the file");
    writer.newLine();
    writer.close();
}
```

In the Java code above, we have defined two methods, one called `main` just like we've seen many times before, and another method named `outputToFile` that we can use to write data to a file with the name stored in the `filename` parameter. The body of the functions are delimited with `{}`. Just like conditional statements and loops, all method definitions must have a body.

The first method, named `main`, is the actual code that runs when our program is executed. 

The other method, `outputToFile`, actually performs the work of outputting to the file.

To use a method, we've included code that looks like `outputToFile("file1.txt");` in our `main` method. That line is known as a _method call_ or _method invocation_, which will then execute the code inside of the `outputToFile` method. So, we might say that we are using that line to "call outputToFile" or "call the outputToFile method". Either way is correct!

Of course, we also need to be able to provide input to our method, as we do in this example. The next page will describe how that works in more detail.

{{% notice info "Function vs. Method vs. Subroutine" %}}

Informally, programmers may use the terms _function_, _method_, _subroutine_, and, to a lesser extent, _procedure_ and other terms, to refer to many similar things. In general, they can be used interchangeably in most cases, since it is pretty clear what they are referring to, but for new programmers it can be a bit difficult to understand all of the different terms that are used. 

So, to make things a bit clearer, we'll try to stick with the definitions below for each of these terms:

* **Subroutine**: A piece of code that can be executed as part of a program, which may return a value.  This is and old term and not generally used.
* **Function**: A synonym for subroutine, more common. Python comes with several built in functions.
* **Method**: A subroutine that can be executed as part of a class. We've been using many methods in our programs already. We'll learn more about classes in a later module.
* **Procedure**: A subroutine that doesn't return a value, but we'll generally avoid using this term

To make matters more complex, some languages use all of these terms, each with very precise definitions.  

Both Python and Java are pretty loose in their usage, and we will generally use the term "method" to mean any callable code snippet, but may use function and method interchangeably. 

For more information on this, feel free to read a [relevant post on StackExchange](https://softwareengineering.stackexchange.com/questions/20909/method-vs-function-vs-procedure).

{{% /notice %}}
