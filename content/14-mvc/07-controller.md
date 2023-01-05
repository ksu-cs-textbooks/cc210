---
title: "Controller"
pre: "7. "
weight: 70
---

The final part of MVC architecture is the _controller_. The controller is really the "glue" that brings together the different parts of the model and the view, building a cohesive program. Traditionally, the controller contains the `main()` method of the program, and acts as the starting point for everything else the program does.

It can be tempting to think of the controller as the "brains" of the program. However, if we are careful about properly building methods in the model that enforce the rules of the program, as well as methods in the view that are able to validate any input received from the user, the controller itself may not have much logic at all in it. Instead, it simply passes data between the model and the view, and uses input from the view to select the next method to call in the model.

## Example

Going back to our Connect Four example one more time, let's look at the UML diagram for the controller part of this program:

![Connect Four Controller UML Diagram](/images/14-mvc/13.6.controluml.png)

Yup! That's it! In this example, the controller simply contains the main method for the program. The real magic happens in the code inside of the main method, gluing other parts of the program together and making them work. 

We'll explore the code for the controller later in this module as our worked example.