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

![Connect Four UML Diagram](/images/14-mvc/13.8.j.uml.png)

Let's get started!

## Model

{{% youtube C5f5XUqRGxM %}}

[Video Materials]({{<relref "./video">}})

In many cases, the first part of any program following the MVC architecture to build is the model. This is usually the simplest and most straightforward part of the program, and both the view and the controller really depend on the model as the basis of the entire program. So, let's start there.

First, we'll need to build a class that contains the attributes and methods shown in the UML diagram above. By this point, we should be pretty used to this process:

```java
import java.lang.IllegalArgumentException;

public class ConnectModel{

  private int[][] board;
  private int current_player;
  
  public int getCurrentPlayer(){ return this.current_player; }
  public int[][] getBoard(){ return this.board; }

  // more code here
}
```

This code already contains implementations for the two getter methods as well as the declarations for the two private attributes. So, all we have left to do is implement the constructors and a few methods.

Let's focus on the constructors first. We can build the normal constructor as shown below:

```java
public ConnectModel(int m, int n){
  if(m < 4 || n < 5){
    throw new IllegalArgumentException("The board must be at least 4 x 5");
  }
  this.board = new int[m][n];
  this.current_player = 1;
}
```

This method really consists of two parts. First, we verify that the parameters provided are valid. If not, we'll throw an exception. Then, it initializes the board attribute to the correct dimensions. We also set the current player to 1.

We also need to implement our constructor for testing, which simply accepts a board and a current player:

```java
public ConnectModel(int[][] board, int current_player){
  if(board.length < 4){
    throw new IllegalArgumentException("Board must be at least 4 x 5");
  }
  if(board[0].length < 5){
    throw new IllegalArgumentException("Board must be at least 4 x 5");
  }
  if(current_player != 1 && current_player != 2){
    throw new IllegalArgumentException("Current player invalid - must be 1 or 2");
  }
  this.board = board;
  this.current_player = current_player;
}
```

This constructor simply enforces the size of the board and the values that are possible for the current player, and then sets those values to the ones provided as arguments. As we discussed before, this method is primarily used for testing our model, and won't actually be used in our program itself. 

Once we have our constructors built, we can also build our `makeMove()` method:

```java
public boolean makeMove(int y){
  if(y < 0 || y >= this.board[0].length){
    throw new IllegalArgumentException("Invalid column");
  }
  if(this.board[0][y] != 0){
    throw new IllegalArgumentException("Column full");
  }
  int row = this.board.length - 1;
  while(board[row][y] != 0){
    row = row - 1;
  }
  this.board[row][y] = this.current_player;
  return true;
}
```

This method is also pretty straightforward. First, we use a couple of **If-Then** statements to check and see if the input is valid. If it is, then we simply iterate through the column chosen from the last row up to the first, looking for the first empty slot. Once we've found it, we place the current player's piece there, and return `true`.

There we go! That's a simple method for checking to see if a move in Connect Four is valid according to the rules of the game.

Next, we'll need to write a method to determine if the current player has won. In this method, we'll simply check to see if any row or column has at least 4 consecutive pieces for the current player.

```java
public boolean checkWin(){
  // check rows
  for(int i = 0; i < this.board.length; i++){
    int count = 0;
    for(int j = 0; j < this.board[0].length; j++){
      if(this.board[i][j] == this.current_player){
        count += 1;
      }else{
        count = 0;
      }
      if(count >= 4){
        return true;
      }
    }
  }
  
  // check columns
  for(int j = 0; j < this.board[0].length; j++){
    int count = 0;
    for(int i = 0; i < this.board.length; i++){
      if(this.board[i][j] == this.current_player){
        count += 1;
      }else{
        count = 0;
      }
      if(count >= 4){
        return true;
      }
    }
  }
  return false;
}
```

This method is also pretty straightforward. We simply use two nested **For** loops to iterate across each row and down each column, keeping track of the count of items that match the current player. Anytime we see an item that doesn't match, we reset our count to 0. If we reach 4 at any time, we can simply return `true`. If we reach the end of the method without returning `true`, then we know that a win condition hasn't been reached and we should return `false`.

We'll also need a method to check for a draw:

```java
public boolean checkDraw(){
  for(int j = 0; j < this.board[0].length; j++){
    if(this.board[0][j] == 0){
      return false;
    }
  }
  return true;
}
```

In this method, we only have to check the top row of the board. If any of them are empty, we can return `false`. However, if we find that all of them are filled, we can return `true`, indicating that the board is filled. 

Finally, we'll build one more method to switch players between 1 and 2:

```java
public void nextPlayer(){
  if(this.current_player == 1){
    this.current_player = 2;
  }else{
    this.current_player = 1;
  }
}
```

It is really just a simple **If-Then** statement!

There we go! That should be everything we need to build a model of a working Connect Four game. We can use the assessments below to confirm that our code is working properly before continuing. 
