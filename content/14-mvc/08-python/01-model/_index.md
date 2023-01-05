---
title: "A Worked Example - Model"
pre: "1. "
weight: 10
---

Let's continue our example exploring a program to play Connect Four by actually building the code to implement the game. By exploring the code, we should be able to better understand the structure and reasoning behind the MVC Architecture.

## Problem Statement

First, let's formalize our problem statement:

> Write a program to play the traditional version of Connect Four. It should take place on a 6 x 7 game board.

> On each turn, the game will print out the state of the board, then alert the current player to make a move. The player's move will consist of a single number, giving the column in which to place a piece. If the move is invalid, the player will be given the option to select another move.

> After each move is made, the game will determine if the current player has won, or if the game was a draw. To simplify the game, we will not check for diagonal wins.

> The program should be built using MVC architecture.

So, for this program, we'll use the following UML diagram:

![Connect Four UML Diagram](/images/14-mvc/13.8.p.uml.png)

Let's get started!

## Model

{{% youtube eTatlji1Ajc %}}

[Video Materials]({{<relref "./video">}})

In many cases, the first part of any program following the MVC architecture to build is the model. This is usually the simplest and most straightforward part of the program, and both the view and the controller really depend on the model as the basis of the entire program. So, let's start there.

First, we'll need to build a class that contains the attributes and methods shown in the UML diagram above. By this point, we should be pretty used to this process:

```python
class ConnectModel:

  @property
  def board(self):
    return self.__board
  
  @property
  def current_player(self):
    return self.__current_player
  
  # more code here
```

This code already contains implementations for the two property getter methods for the private attributes. So, all we have left to do is implement the constructor and a few methods.

Let's focus on the constructor first. We can build the normal constructor as shown below:

```python
def __init__(self, m, n):
  if m < 4 or n < 5:
    raise ValueError("The board must be at least 4 x 5")
  self.__board = []
  for i in range(0, m):
    self.__board.append([])
    for j in range(0, n):
      self.__board[i].append(0)
  self.__current_player = 1
```

This method really consists of two parts. First, we verify that the parameters provided are valid. If not, we'll throw an exception. Then, it initializes the board attribute to the correct dimensions and fills it with empty squares represented by 0. We also set the current player to 1.

We also need to implement our `load_game()` method for testing, which simply accepts a board and a current player:

```python
def load_game(self, board, current_player):
  if len(board) < 4:
    raise ValueError("Board must be at least 4 x 5")
  if len(board[0]) < 5:
    raise ValueError("Board must be at least 4 x 5")
  if current_player != 1 and current_player != 2:
    raise ValueError("Current player invalid - must be 1 or 2")
  self.__board = board
  self.__current_player = current_player
```

This method simply enforces the size of the board and the values that are possible for the current player, and then sets those values to the ones provided as arguments. As we discussed before, this method is primarily used for testing our model, and won't actually be used in our program itself. 

Once we have our constructors built, we can also build our `make_move()` method:

```python
def make_move(self, y):
  if y < 0 or y >= len(self.board[0]):
    raise ValueError("Invalid column")
  if self.board[0][y] != 0:
    raise ValueError("Column full")
  row = len(self.board) - 1
  while self.board[row][y] != 0:
    row -= 1
  self.__board[row][y] = self.current_player
  return True
```

This method is also pretty straightforward. First, we use a couple of **If-Then** statements to check and see if the input is valid. If it is, then we simply iterate through the column chosen from the last row up to the first, looking for the first empty slot. Once we've found it, we place the current player's piece there, and return `True`.

There we go! That's a simple method for checking to see if a move in Connect Four is valid according to the rules of the game.

Next, we'll need to write a method to determine if the current player has won. In this method, we'll simply check to see if any row or column has at least 4 consecutive pieces for the current player.

```python
def check_win(self):
  # check rows
  for i in range(0, len(self.board)):
    count = 0
    for j in range(0, len(self.board[0])):
      if self.board[i][j] == self.current_player:
        count += 1
      else:
        count = 0
      if count >= 4:
        return True
  
  # check columns
  for j in range(0, len(self.board[0])):
    count = 0
    for i in range(0, len(self.board)):
      if self.board[i][j] == self.current_player:
        count += 1
      else:
        count = 0
      if count >= 4:
        return True
      
  return False
```

This method is also pretty straightforward. We simply use two nested **For** loops to iterate across each row and down each column, keeping track of the count of items that match the current player. Anytime we see an item that doesn't match, we reset our count to 0. If we reach 4 at any time, we can simply return `True`. If we reach the end of the method without returning `True`, then we know that a win condition hasn't been reached and we should return `False`.

We'll also need a method to check for a draw:

```python
def check_draw(self):
  for j in range(0, len(self.board[0])):
    if self.board[0][j] == 0:
      return False
  return True
```

In this method, we only have to check the top row of the board. If any of them are empty, we can return `False`. However, if we find that all of them are filled, we can return `True`, indicating that the board is filled. 

Finally, we'll build one more method to switch players between 1 and 2:

```python
def next_player(self):
  if self.current_player == 1:
    self.__current_player = 2
  else:
    self.__current_player = 1
```

It is really just a simple **If-Then** statement!

There we go! That should be everything we need to build a model of a working Connect Four game. We can use the assessments below to confirm that our code is working properly before continuing. 

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}