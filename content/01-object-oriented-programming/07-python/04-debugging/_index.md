---
title: "Debugging"
pre: "4. "
weight: 40
---

<!-- {{< youtube 5W3xil6oBtc  >}}-->
<!-- TODO Redo Video -->
<!-- Video Materials]({{% relref "./video" %}}) -->

Of course, when developing a computer program, there are always times when things don't quite work the way we'd like them to. Let's review a few of the common errors and how to solve them. 

## Wrong Interpreter

When working with Python, one of the most common mistakes is typing the `python` command when we actually mean to use the `python3` command. This would cause our program to be interpreted with the Python 2 interpreter instead of the Python 3 interpreter. Those versions of Python are not fully compatible, so we might see some strange errors. 

For example, if we write our `HelloWorld.py` file using syntax for Python 2, and try to run it using the Python 3 interpreter, we may see an error similar to this one:

![Python Syntax Error](/images/01-oop/1.3.p.4.syntax.png)

We might run into similar problems if we ran code written for Python 3 in the Python 2 interpreter.

## Syntax Issues

One of the easiest errors to run into when learning how to program is forgetting a syntax element. To see how that works, let's replace the code in our `HelloWorld.py` file with the following:

```python
print("Hello World"
```

{{% notice info "Spot the Error" %}}

Before running that program, can you spot the error? Being able to find errors in code without using an interpreter will definitely help you develop programs much faster. It is just like being able to spell words correctly without using a spell-checker. It makes everything go just a bit more smoothly.

In each of the examples in this section, take a minute and see if you can spot the error before running it through the interpreter. The quiz in this module includes a few questions that require you to spot the error in a piece of code, so this is great practice for later!

{{% /notice %}}

Once we've updated that file, we can run it using the method of our choice, either using the terminal or the options in the **Run Menu**. When we do, we should see output similar to this:

![Python Missing Closing Parenthesis](/images/01-oop/1.3.p.4.missingparen.png)

That error message gives us quite a bit of information. The first part, `File "1p-hello/HelloWorld.py"` tells us which file the error is in, which is handy later on when we start working in programs that include multiple source code files. Following that, we see a `line 2` after the file name, which tells us that the error is on or around line 2. However, that doesn't always mean that we'll need to edit something at line 2 to fix the error; it just means that the Python Interpreter realized there was an error when it reached line 2. Sometimes, we must make a change elsewhere in the file to resolve the issue. 

After that, we'll see the actual error message, which in this case is `SyntaxError: unexpected EOF while parsing`. In this message, `EOF` refers to the end of the file. That may not seem very helpful at first, but it actually gives us an important clue. 

If we look at the code above, we'll notice that it is missing the closing parenthesis `)` at the end of the line of code. So, the interpreter was expecting to see a closing parenthesis, but didn't find it. So, to fix that, we'll just need to add a closing parenthesis at the end of that line of code, and it should work just fine. 

We would see a similar error if we left off an ending quotation mark `"` as well. 

## Incorrect Function

Here's another example we can try:

```python
pint("Hello World")
```

When we try to run this file, we should get output similar to the following:

![Python Incorrect Function](/images/01-oop/1.3.p.4.badfunction.png)

In this example, the output is really helpful. It clearly shows us exactly where in our code our error is, and we can see that the error is `NameError: name 'pint' is not defined`. If we look closely at the line indicated in the error message, we should see that we simply misspelled the name of the `print()` method, which can easily be corrected. 

{{% notice tip "Break Stuff" %}}

Now that you've learned a bit about how to debug interpreter errors, let's see if you can figure out how to cause one! Modify `HelloWorld.py` in a way that causes the interpreter to output the following error message: 

`SyntaxError: Missing parentheses in call to 'print'`

{{% /notice %}}