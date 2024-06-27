---
title: "MVC Architecture"
pre: "1. "
weight: 10
hidden: true
date: 2019-11-15T00:00:26-05:00
---

{{< youtube dtmC5wJvZTA >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

In this module, we'll explore how to build our programs following the Model-View-Controller Architecture, also known as MVC Architecture. It is one of the more common software design patterns for all sorts of programs, and usually one of the first we study when learning to program.

A program built using MVC has a program flow that resembles this flowchart. The model at the top represents the data stored in the program, which is then used to update the view that is displayed to the user. The user sees the view, and uses it to send commands to the controller. The controller then interprets the commands and uses them to manipulate the data stored in the model, starting the process all over again.

So, in summary, the model stores the data and implements the rules for accessing and modifying the data, the view displays the data to the user and provides the user options for interacting with the program, and finally the controller links the two together, interpreting user actions in the view as methods in the model, and sending the data from the model back to the view.

One great example of a program that could be built using the MVC architecture is a simple word processor. The model represents the text stored in the document, the view is the graphical display to the user, and the controller interprets keyboard events to help modify the text in the document.

Another example could be a video game. The model would then represent the world and the sprites in the game, the view would once again be the GUI and head's up display shown to user, and the controller would interpret events from the player's controller to move the character around the game.

As we continue in this module, we'll explore an example program built using MVC architecture to see how this works in practice.
