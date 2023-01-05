---
title: "View"
pre: "6. "
weight: 60
---

Next, let's look at the _view_ portion of MVC Architecture. In essence, this part is responsible for displaying data to the user, and in most cases it also handles requesting and receiving input from the user. 

One important thing to remember is that the view **should not** duplicate or store any data that is already present in the model. While it may be tempting to store a copy of the currently displayed data in the view, it technically violates the MVC Architecture. We should _only_ store data in the view that is unique to the view, while all data related to the state of the model should be stored in the model instead.

## Example

Going back to our Connect Four example, we would probably want our view to be responsible for displaying the current state of the game board, and which player's turn it is, to the player. In addition, it should have methods for retrieving input from the player about what moves to make. Finally, it should have a method to display a message to the players once the end of a game is reached.

So, one way we could represent the view portion of this program is shown in the UML diagram below:

![Connect Four View UML Diagram](/images/14-mvc/13.5.viewuml.png)

In this diagram, we notice that the view itself does not store any attributes at all. This is because the view doesn't have to manage any internal state when it is simply reading data from and writing to the terminal. If we were dealing with a file or a graphical user interface (GUI), then the view may have to store those items as attributes. In this program, we are keeping it pretty simple.

However, the `ConnectView` class includes several methods:
* `ConnectView()`: a simple constructor.
* `showBoard(board)`: this method will show the current board to the players on the terminal.
* `showTurn(player)`: this will display a message letting the players know which player is up next.
* `showMenu()`: this method will show the menu of options to the current player, allowing them to make a move. The input received from the player will be sent to the controller. 
* `showEndGame(winner)`: if either player wins, this will display that message to the terminal.
* `showError(error)`: this method is used by the controller to display any errors from the model to the user.

As we can see, the view portion of MVC Architecture mainly deals with displaying messages to the user, and then prompting the user for input. It doesn't have to store any data to be useful, and doesn't even include a direct link to the model. That is provided by the controller, which we'll learn about next. 