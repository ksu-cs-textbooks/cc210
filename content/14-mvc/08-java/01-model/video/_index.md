---
title: "Java Example"
pre: "2.J. "
weight: 20
hidden: true
date: 2019-11-15T00:00:26-05:00
---

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

{{< youtube C5f5XUqRGxM >}}

Now that we've learned about the structure of a program written using MVC architecture, let's see how we could build it in code.

As always, we'll start with a problem statement. Here it is!

That looks pretty complex! Thankfully, we already know we are using MVC architecture, so we'll just have to figure out which parts belong in the model, view, and controller.

For this program, we'll be following this UML diagram to build our classes and their overall structure. To make it simple, we have each part of the MVC architecture represented by a single class. In a larger program, each part of MVC architecture could be represented by multiple classes working together.

In most cases, it is simplest to write the model first. So, let's look at the ConnectModel class. This class contains attributes to store the Connect Four board as a two dimensional array. It also stores the current player as an integer, and has getter methods for both attributes. We can build that part pretty quickly. The rest of the class involves methods to manipulate the board and enforce the rules of the game, which we'll address separately.

First, let's look at the constructor. It begins by verifying that the size of the board is at least 4 by 5, otherwise it would be an impossible game to play. If the parameters are accepted, then it simply creates a new board by initializing the two dimensional array, as well as setting the current player to player 1.

This program also includes a secondary constructor, simply for the purposes of testing. It allows us to submit our own board and player, representing a game in progress, so we can test a single move. Of course, we'll still have to verify that the input received is acceptable first. In practice, we could include this method for testing the model, then remove it from the final version of the code once we are sure it is working correctly.

Now let's look at the method for actually making a single move in the game.

On a player's turn, the player will select a column on the board and drop a piece in the top. The piece will fall down until it reaches the bottom of the board or another piece on that same column. The basic idea is shown in this animation.

So, for starters, we need to verify that the column selected is actually a valid column that exists on the board. If not, we'll throw an exception.

Next, we'll also need to make sure that the column selected isn't full by checking the item in the top row of that column. Again, we'll throw an exception if it is full, since that isn't a valid move.

Then, if the move is valid, we'll simply need to iterate from the bottom of the board toward the top, checking each row in that column and finding the first row that is empty. So, we'll start at the bottom row, then use a while loop to iterate upward until we find an empty square on the chosen column, and place our piece there.

Finally, since the move was successful, we should return `true` to signal that the piece was placed. That's all it takes to make a single move in Connect Four.

The next method we'll need to handle is the method to check and see if the player has won the game. To do this, we're looking for any row or column that contains 4 consecutive pieces for this player. Let's do the rows first, since they are easiest to check.

To iterate across each row, we'll use two nested for loops, just like this.

Inside of the first loop, we'll create a counter variable to keep track of the number of consecutive pieces we've found that match the current player's piece.

Then, in the inner for loop, we'll check and see if the current board position is equal to the current player. If it is, we'll increment our counter. If not, we'll have to reset it to 0.

Below that, we'll check to see if the counter is equal to 4. If it is, that means we've found 4 pieces in a row that belong to this player, meaning the player has won the game.

That covers checking the rows for a win. To check the columns, we can use the exact same code, but swap the order of the for loops so that the innermost loop is iterating down a column instead of across a row. Pretty neat, right?

Of course, if neither of those sets of loops find a win, we'll need to remember to return `false` at the end of the method, since the player has not won yet.

The last two methods in this class are checking to see if the game is a draw, which simply looks for any empty squares on the top row of the board. If it finds one, the game is not a draw. However, if it goes through the entire top row and doesn't find an empty square, we can return `true` to let the players know that it is a draw.

The last method simply swaps the value of the `current_player` attribute between 1 and 2.

There we go! That's all it takes to build the model class for Connect Four. Before we move on, let's use the assessments on this page to verify that the model class is working properly before moving on.

---

{{< youtube b5wNxvT6BNE >}}

Next, let's look at the ConnectView class. This class handles displaying the status of the game to the players, as well as prompting the players for input as needed. So, let's explore how we can write that class.

First, the class just contains a default constructor, so we don't need to do anything there. If this program had an actual graphical user interface, or GUI, this is where we'd build it.

The next method we'll look at is the method to print the board to the screen. This method is actually pretty simple. We use two nested for loops to iterate across each square on the board, and print the value of the square contained in square brackets. Notice that we are using `System.out.print()` to not print a new line after each square. Instead, we include a call to `System.out.println()` after the inner for loop, which will print a newline at the end of each row of squares.

This is actually a very standard process for printing the contents of a two dimensional array. So, when it is printed, we'll see output that looks something like this.

Next, we'll look at the method to show the menu to the user. In this case, it simply asks the current user to input a number that represents the column to place their piece.

This method uses a try statement inside of an infinite loop to accomplish this.

In effect, if the user inputs a value, we'll try to convert it to an integer. If it fails, we'll simply catch the exception, print an error, and the loop will repeat and ask the user for input again.

However, if the user inputs a valid number, it will be successfully converted and returned from the function, exiting the infinite loop. Pretty nifty, right?

The rest of the methods in the ConnectView class are pretty straightforward. Most of them are just displaying simple messages to the players. In a program that uses a GUI, these might be popup messages or updating the value of different boxes on the GUI instead of simple text outputs.

That's all there is to the view portion of the program. Once again, see if you can complete the assessments to make sure it works before continuing.

---

{{< youtube 3AVem5EdY6U >}}

Finally, we are ready to build our controller. If we look at the UML diagram, we see that it only contains a `main()` method. So, let's explore that code.

First, we'll need to instantiate a board and a view. For the board, we'll choose a standard 6 x 7 board.

Then, the program itself will take place inside of an infinite loop. This is because we want the game to continue until either one player wins or the game is a tie, so we'll just repeat forever and use `break` statements to exit the loop when needed.

Inside of the loop, we'll start by showing the current board to the players. Notice that we are calling the `getBoard()` method of the model and passing the returned value as an argument directly to the `showBoard()` method. In effect, we are using the controller to connect the parts of the model and view together and build our program one step at a time.

Next, we show the players the message telling them which player's turn it is.

After that, we'll use a try-catch statement to handle the part of the program where the user is allowed to make a move. We do this since our model could throw exceptions that we need to catch. In the catch block, we'll simply use the view to print the error message for the players.

Inside of the try block, we'll ask the user for a column to place a piece, and see if we can make a move there. Of course, if that move is invalid, it will throw an error that we can catch, and then the process will repeat.

If the move is successful, we need to check if the game is over due to the current player winning or the game reaching a draw. If either of those happen, we'll use the `break` keyword to exit the loop.

However, if the game doesn't end, we'll need to make sure we tell the model to switch to the next player before the program loops and the process begins again.

Outside of the loop, we know that the game has ended either in a win or a tie. So, we can call a method in the model to figure out which one, and then use the appropriate method in the view to show the correct message to the players.

There we go! That's all it takes. As with many programs we've developed, the controller for this program once again looks like an outline of the entire program itself. In fact, I've found that programs built using MVC are some of the simplest programs to work with, since each part of the program is clearly self-contained and only performs a few major actions.

See if you can complete this example yourself. Good luck!
