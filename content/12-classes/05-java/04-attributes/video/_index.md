---
title: "Java Attributes"
pre: "3.J. "
weight: 30
hidden: true
date: 2019-09-24T00:00:26-05:00
---

{{< youtube RzpoMdr2Fs4 >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

Let's begin learning how to build our own classes in Java. We can start by implementing the Student class that we see in the diagram at the top of this page.

First, we'll need to actually create the class declaration. We've been doing this as part of each of our programs already, so this should be pretty familiar by now. We use the `public` and `class` keywords, followed by the name of the class, and a set of curly braces.

Now, we need to add attributes. In the diagram above, we see that the first attribute is a String variable called `name`. So, just like we'd declare a variable in our code, we'll add a variable declaration to the inside of the class.

However, it is important to note that this code isn't being "executed" directly. It is simply defining the structure of the class. So, we can't do things like declare a variable on one line, and then update its value on a second line.

Thankfully, Java does allow us to declare a value and set a default value for that variable on a single line. So, if we want the default value of `name` to be "test", we can do that as shown here.

Filling in the rest of the attributes is pretty self explanatory. We can just create a variable for each one using the correct data type, and set a default value if desired.

Later in this module, we'll learn how to use additional keywords such as `public` and `private` in front of these variable declarations, but for now we won't worry about them.

Of course, we don't have to set default values either. So, at this point we can choose to leave those out if we'd like.

That's a good start! See if you can do the same for the other two classes in this program.
