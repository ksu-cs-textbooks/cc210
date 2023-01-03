---
title: "Python Attributes"
pre: "3.P. "
weight: 31
hidden: true
date: 2019-09-24T00:00:26-05:00
---

{{< youtube 9ZX2RBcsRfc >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

Let's begin learning how to build our own classes in Python. We can start by implementing the Student class that we see in the diagram at the top of this page.

First, we'll need to actually create the class declaration. Thankfully, this is pretty simple in Python. At the top of the file, we can use the `class` keyword, followed by the name of the class and a colon. It is very similar to declaring a function. Then, any code that is part of the class simply goes below the colon, indented one level.

Now, we need to add attributes. In the diagram above, we see that the first attribute is a String variable called `name`. So, just like we'd declare a variable in our code, we'll add a variable declaration to the inside of the class. In Python, we'll need to give that variable a default value, since variables are only created upon assignment. As we'll see later in this module, this is actually creating a class variable instead of an instance variable, but the difference isn't really important right now.

Filling in the rest of the attributes is pretty self explanatory. We can just create a variable for each one using the correct data type as the default value.

That's a good start! See if you can do the same for the other two classes in this program.
