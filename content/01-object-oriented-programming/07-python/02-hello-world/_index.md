---
title: "Hello World"
pre: "2. "
weight: 20
---

{{< youtube mXI22TUa9G4  >}}

<!-- TODO Update Video -->
<!-- OLD [Video Materials]({{% relref "./video" %}}) -->

According to tradition, the first computer program that we cover in any language is a simple program called "Hello World!" The entire goal of the program is to demonstrate what it takes to create our first program from scratch in the language, and get to the point where we can print the message of our choice to the screen. While that sounds very simple, it is actually a pretty big first step toward learning how to write our own programs. Let's get started!

{{% notice warning "Help!" %}}

If this is your first time programming, it can be quite daunting to know where to get started. This guide will walk you through all the steps to create your first program. However, if you have any questions at all, don't be afraid to seek help. It's much easier to answer questions up front when they come up, instead of dealing with them down the road when you are truly lost. 

In this program, you can use the you can use the course discussion forums or email list to ask for help. You may also find information about help sessions and open office hours posted there. That should always be your first place to go when you get stuck.

Good luck!

{{% /notice %}}

## Some Terminology

In any programming language, there is a bit of terminology that we should discuss before diving in. Here are a few terms we'll want to be familiar with at this point:

1. _keyword_ - in any programming language, a _keyword_ is a word that has a special meaning. These words tell the program exactly what to do, and we cannot use these words as _identifiers_. Consult the [Python Language Keywords](https://docs.python.org/3.4/reference/lexical_analysis.html#keywords) list to determine which words are keywords in Python.
1. _built in functions_ - in addition to keyword, Python has a list of built in functions, the names of these functions should be treated as keywords--don't use them as identifiers. Consult the [Python Built in Functions](https://docs.python.org/3.4/library/functions.html) list to determine the names you should avoid. `print` is a built in function.


## Open a File

To begin, there should see a file named `HelloWorld.py` open in the panel to the left. If not, click on that file in the file tree to the far left to open it. Make sure that file is open for this example, since the file name must match in order for this process to work properly. 

Also, we should make sure that the file is completely empty before moving on. If there is any text currently in that file, take the time to delete it now.

We can also do these same steps on a computer with Python installed. Simply create a new, blank text file named `HelloWorld.py`.


```python
import sys
class HelloWorld:
    
  @staticmethod
  def main(args):
      ## Your Code goes below

      ## Your code goes above

if __name__ == "__main__":
    HelloWorld.main(sys.argv)
```

Lets take a quick look at the starter code.

<table>
  <tr><td style="white-space: nowrap"><code>class HelloWorld:</code></td> <td>starts the class definition.  By convention, class names in Python follow PascalCase, each "word", including the first is capitalized and spaces are omitted.  Also by convention, the file name and class name are the same.</td></tr>
  <tr><td style="white-space: nowrap"><code>  @staticmethod<br/>    def main(args):</code></td><td><code>def main()</code> starts the definition of the main method.  Python convention is that method names (function names) are in camelCase.  Object oriented convention is that the <code>main()</code> method is static (more on this about module 10).</td></tr>
  <tr><td style="white-space: nowrap"><code>      # WRITE YOUR CODE HERE</code></td><td>Through module 5, you will just be adding code to the <code>main()</code> method.  These comments are a guide to help you get the code in the right place.  There is no connection between the number of blank lines and the number of lines of code you will need to write.</td></tr>
  <tr><td style="white-space: nowrap"><code>if __name__ == ...</code></td><td>By convention, object oriented programs start in the main method, this code accomplishes that.</td></tr>
</table>


## Saying Hello

Finally, we can write our code. The remaining code of our program goes right inside the definition of `main()` . In the classic "Hello World!" example, we simply want to print the words "Hello World!" to the screen. So, let's add the following code to that file. To fully see how this example works, we should manually type the code into the file instead of copying and pasting it:

```python
print("Hello World!")
```

Did you notice how the editor in Codio automatically added a closing parenthesis right after you typed the opening parenthesis? That's the power of using a text editor that is tailored for programming. It should have also done the same for the quotation marks. It may seem a bit jarring a first, but you'll quickly get used to it. 

Let's review what we just added to our program:

1. `print` - this line tells us that we'd like to use a method called `print()`, which is a built-in method in Python. That means very little to us right now, but for now we'll need to know to use this method to print a line of text to the screen. Following the name of the method is a set of parentheses that accepts input to the method, which is what we'd like to have printed to the screen.
1. `"Hello World"` - by putting this in the parentheses after `print`, we are telling the `print()` method to print the litteral value `Hello World` to the screen. We have to enclose it in quotation marks `"` so that our program will treat it as a line of text and not more Python code.

{{% notice info "Style Guide" %}}

To make your code easier to read, many textbooks and companies use a _style guide_ that defines some of the formating rules that you should follow in your source code. In Python, these rules are very important, as the structure of your code is defined by the layout. We'll learn more about that in a later module. 

For this book, most of the examples will be presented using the guidelines in the [Style Guide for Python](https://www.python.org/dev/peps/pep-0008/). However, by default Codio used to use 4 spaces for an indentation level instead of 2, so that is the format that will be used in some examples in this book.

Google also provides a comprehensive [style guide](http://google.github.io/styleguide/pyguide.html) that is recommended reading if you'd like to learn more about how to format your source code. 

{{% /notice %}}

That's it! That's all it takes to write our first program in Python. On the next page, we'll learn how to actually run this program using Codio. 