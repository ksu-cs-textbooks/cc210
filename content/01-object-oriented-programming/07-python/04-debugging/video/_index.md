---
title: "Python Debugging"
pre: "4.P. "
weight: 41
hidden: true
date: 2019-02-05T10:53:26-05:00
---

{{< youtube 5W3xil6oBtc >}}

#### Resources

#### Video Script

One of the major frustrations when learning to write computer code is dealing with errors in your code. So, let's review a few common mistakes that you may encounter and how to solve them.

First, a common error that we may make is using online documentation that shows us how to write code for the Python 2 interpreter instead of the Python 3 interpreter. When we try to run that code using the `python3` command, we might see an error similar to this one.

We'd see a similar error if we try to run some Python 3 code using the Python 2 interpreter as well.

We can also make some mistakes in our code itself. For example, take a look at this version of the Hello World program and see if you can spot the error.

When we try to run this program using the Python interpreter, we'll get an error similar to this one. It tells us that it found an unexpected EOF, or end of file, when parsing. So, we need to carefully check our code, looking particularly for missing parentheses or quotation marks. In this case, we left off the closing parenthesis on the `print` method. So, we can easily correct that error and try again.

Here's another code example. Can you spot the error?

In this example, we misspelled the `print` method. Thankfully, the Python interpreter gives us a pretty helpful error message, so it should be pretty easy to sole this issue.

Of course, anytime you run into an error in your code, you should take some time to see if you can solve it yourself. If you really get stuck, don't be afraid to ask for help on Piazza. Especially when you are learning to code, there is a great chance that you'll run into an error that is difficult to solve by yourself, but we're always available to help!

Good luck completing this rest of this module!
