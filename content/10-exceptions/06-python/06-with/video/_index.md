---
title: "Python With"
pre: "5.P. "
weight: 51
date: 2019-09-10T00:00:26-05:00
hidden: true
---

{{< youtube Mr6OPmyKRCM >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

One of the most common use cases of the **Try-Except** statement is to deal with input from a file or other resource, mainly because there are many possible exceptions that can occur when reading that input. However, even if we encounter an error, it is also good practice to make sure that we close whatever resource we are using. So, in this program, we have created a reader, initialized it to read input from a file, and then included a **Finally** block that will handle closing the reader, regardless of whether our code reaches an exception or not.

The Python programming language includes another programming construct that we can use to simplify this process, known as a **With** statement. To use a **With** statement, we can simply add the `with` keyword followed by the variables we'd like it to manage and then a colon. So, in this case, we can just add `with reader:` to our program, and then indent the lines below that use the reader to read input.

Once we do that, we can remove the **Finally** block from our code. This is because the **With** statement will automatically handle closing any open resources used by the `reader` variable, or any other variable listed after the `with` keyword.

In addition, if an exception occurs while reading the input, the **With** statement will automatically hide any additional exceptions that are caused when it tries to close the resource. In this way, it is much better than using a **Finally** statement, since the **Finally** statement executes after the exception is handled, and could be the source of additional exceptions that are not caught by the **Try-Except** statement.

Lastly, we can always create new variables from within the **With** statement using the `as` keyword, as shown here. So, if we know we need to read input from a single source, we can open the file directly inside of the **With** statement.

That's all there is to it! This is a very powerful yet simple way for developers to make sure that resources will be properly closed, no matter what happens.
