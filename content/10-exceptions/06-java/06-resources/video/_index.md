---
title: "Java Try with Resources"
pre: "5.J. "
weight: 50
date: 2019-09-10T00:00:26-05:00
hidden: true
---

{{< youtube 86RzF9SgSJE >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

One of the most common use cases of the **Try-Catch** statement is to deal with input from a file or other resource, mainly because there are many possible exceptions that can occur when reading that input. However, even if we encounter an error, it is also good practice to make sure that we close whatever resource we are using. So, in this program, we have created a Scanner object, initialized it to read input from a file, and then included a **Finally** block that will handle closing the scanner, regardless of whether our code reaches an exception or not.

The Java programming language includes another programming construct that we can use to simplify this process, known as a **Try with Resources** statement. To use a **Try with Resources** statement, we can simply add a set of parentheses after the `try` keyword. Then, inside of that set of parentheses, we can create and initialize our Scanner object. In Java 8, which is the version we are using, we must declare a new variable inside of the **Try with Resources** statement, but later versions of Java have removed this requirement.

Once we do that, we can remove our variable declaration outside of the **Try with Resources** statement, since it is now handled inside the statement. In addition, we can remove the **Finally** block as well. This is because the **Try with Resources** statement will automatically handle closing any open resources declared inside of the parentheses, without any additional code. It works with any Java class that implements the AutoCloseable interface. More information about that is included in the textbook.

In addition, if an exception occurs while reading the input, the **Try with Resources** statement will automatically hide any additional exceptions that are caused when it tries to close the resource. In this way, it is much better than using a **Finally** statement, since the **Finally** statement executes after the exception is handled, and could be the source of additional exceptions that are not caught by the **Try-Catch** statement.

That's all there is to it! This is a very powerful yet simple way for developers to make sure that resources will be properly closed, no matter what happens.
