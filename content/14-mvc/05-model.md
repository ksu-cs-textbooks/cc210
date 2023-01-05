---
title: "Model"
pre: "5. "
weight: 50
---

The first part of MVC Architecture is the _model_. Roughly speaking, the model represents all data stored by the program. However, beyond just data, the model should also include all methods that are used to directly modify the data stored in the model. This could also include code that represents or enforces the "rules" around how the model can be manipulated.

It can sometimes be tricky to determine exactly which components of the program should be included in each part, but the model is usually the most straightforward one to work with.

## Example

One of the best examples of a program using MVC architecture is a board game. So, let's consider an example that represents the board game known in America as [Connect Four](https://en.wikipedia.org/wiki/Connect_Four)

![Connect Four Animation](/images/14-mvc/13.4.connect_wiki.gif)[^1]

[^1]: https://commons.wikimedia.org/w/index.php?title=Special:CiteThisPage&page=File%3AConnect_Four.gif&id=364997279

In this game, the model would obviously consist of a representation of the board itself, showing the position and color of each piece. However, in the model, we could also provide methods for actions such as placing a piece on the board or determining if the game is a draw.

In addition to updating the model, those methods would be responsible for enforcing the rules of the game, such as preventing players from placing a piece on a full column.

Of course, there are some rules of the game that are difficult to represent in code, such as keeping track of which player's turn it is. It could be done in the controller, but it is probably best done in the model.

So, what would a model for a Connect Four game look like? Here's a sample UML diagram for one way it could be designed:

![Connect Four Model UML Diagram](/images/14-mvc/13.4.modeluml.png)

In this UML diagram, we see two attributes:

* `board`: a 2-dimensional array or list of integers representing the squares on the board. We'll use the following representation scheme:
  * `0`---an unoccupied square
  * `1`---a square containing a piece for player 1
  * `2`---a square containing a piece for player 2
* `current_player`: an integer determining the player who is able to make the next turn.

We also see the following methods:

* `ConnectModel(m, n)`: a constructor accepting two parameters, `m` and `n`, giving the size of the board. 
* `ConnectModel(board, current_player)`: a secondary constructor accepting a board and a current player. We'll primarily use this method for testing, as it allows us to build a `ConnectModel` for a game currently in progress.  In Python, we'll call this method `load_game()`.
* `getCurrentPlayer()`: a getter method to get the current player as an integer, either `1` or `2`.
* `getBoard()`: a getter method to get the current board.
* `makeMove(y)`: a method for the current player to place a piece in the column indicated by the parameter `y`. This method will return `true` if the placement was successful, or throw an exception if it was not. 
* `checkWin():` this method will check and see if the game has been won by the current player. 
* `checkDraw():` this method will check and see if the game is a draw.
* `nextPlayer():` this method will swap the current player value to represent the other player. 
  
So, this `ConnectModel` class includes all of the attributes to store a game board and the current state of the game, as well as methods to update the game's state based on moves the player could make. 
