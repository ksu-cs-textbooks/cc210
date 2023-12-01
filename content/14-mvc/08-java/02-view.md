---
title: "A Worked Example - View"
pre: "2. "
weight: 20
---


The next part of any MVC program to build is the view. Depending on the complexity of the problem, sometimes it may be helpful to build the view and the model concurrently. Ideally, however, the model and the view should be properly distinct and separate, such that the model can be fully completed before the view is developed.

Let's review our UML diagram before continuing:

![Connect Four UML Diagram](/images/14-mvc/13.8.j.uml.png)

## View

{{% youtube b5wNxvT6BNE %}}

The `ConnectView` class only contains a few simple methods. First, let's build the class declaration and the constructor:

```java
import java.util.Scanner;
import java.lang.NumberFormatException;

public class ConnectView{
  
  public ConnectView(){
    //default constructor
  }
}
```

Since we aren't initializing a GUI, we'll just need a default constructor for this class. 

Next, let's look at the methods. First, we'll need a method to show the board on the screen, called `showBoard()`. Let's see what it looks like:

```java
public void showBoard(int[][] board){
  for(int i = 0; i < board.length; i++){
    for(int j = 0; j < board[0].length; j++){
      System.out.print("[" + board[i][j] + "]");
    }
    System.out.println();
  }
}
```

This method is very similar to methods we saw in an earlier module when we learned about arrays. Here, we are simply using two nested **For** loops to print the data in the array, with each row printed on its own line. 

When we run this method, we should get output that looks like this:

```tex
[1][2][1][2][1]
[1][2][1][2][1]
[1][2][1][2][1]
[1][2][1][2][1]
[1][2][1][2][1]
```

The other complex method to implement is the `showMenu()` method, which reads input from the player:

```java
public int showMenu(){
  while(true){
    try{
      Scanner reader = new Scanner(System.in);
      System.out.println("Which column would you like to place a token in?");
      String input = reader.nextLine().trim();
      int out = Integer.parseInt(input);
      return out;
    }catch(NumberFormatException e){
      System.out.println("Invalid input! Please enter a number");
    }catch(Exception e){
      System.out.println("Unable to read input!");
      return -1;
    }
  }
}
```

That method will print a prompt to the user, and get a response as a string. Notice that we aren't doing any validation of the input here beyond making sure that it is an integer---we can do that in the controller and the model. 

The final three methods simply print out messages to the user. So, we can implement those pretty easily:

```java
public void showTurn(int player){
  System.out.println("It is player " + player + "'s turn!");
}

public void showEndGame(int winner){
  if(winner == 0){
    System.out.println("The game is a draw!");
  }else{
    System.out.println("Player " + winner + " wins!");
  }
}

public void showError(String error){
  System.out.println("Error: " + error);
}
```

That's it! The view portion of the program is very simple, but it allows our users to see what is going on and interact with the program. We can use the tests below to make sure our view is working correctly before we continue with the controller.
