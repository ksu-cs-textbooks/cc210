---
title: "MVC Architecture"
pre: "3. "
weight: 30
---

{{% youtube dtmC5wJvZTA %}}

[Video Materials]({{<relref "./video">}})

One of the most common software design patterns is actually a complete architecture for an entire program, called the [Model-View-Controller](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller), or MVC, Architecture. 

MVC Architecture involves breaking the program into three distinct parts, the _model_, the _view_, and the _controller_. Each part may consist of one or multiple classes, but conceptually we can think of them as three separate pieces, each of which can be accessed from the other pieces in an easy-to-understand way.

From the user's perspective, a program using MVC Architecture may look and act as shown in this diagram:

![Model-View-Controller Diagram](/images/14-mvc/13.3.mvc_wiki.svg)^[^1]

[^1]: File:MVC-Process.svg. (2015, June 19). Wikimedia Commons, the free media repository. Retrieved 18:29, November 7, 2019 from https://commons.wikimedia.org/w/index.php?title=File:MVC-Process.svg&oldid=163714963.

When the user uses the software to perform an action, that action is sent to the controller. The controller then interprets the user's action, and calls methods in the software's model to manipulate and update the data stored in the software. Once the model has been changed, that data is sent to the view, which is responsible for displaying those changes to the screen. 

A classic example is word processing software. When the user has a document open and presses a key on the keyboard, that keypress action is sent to the controller by the operating system running the software. The controller interprets that keypress as a character, and then tells the model to add that character to the document. So, the model updates the data representing the document, and then informs the view that the document has changed and it should now display the new character in the document as well. Finally, the view updates what is presented on the screen to the user, and the user can now see that the action was completed. In this case, the process happens nearly instantaneously, but more complex software may take much longer to complete the action.

On the next few pages, we'll discuss each part of MVC architecture in more detail, using a simple example program.
