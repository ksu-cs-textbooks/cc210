---
title: "A Worked Example - Controller"
pre: "3. "
weight: 30
---

Finally, we now can start working on our controller. This is where the program actually comes together and becomes useful. While a program such as Connect Four may seem quite complex, using MVC architecture can make it quite easy to work with. Let's check it out!

## Controller

{{% youtube 3AVem5EdY6U %}}

The `ConnectController` class just contains a single `main()` method:

```java
public class ConnectController{
  
  public static void main(String[] args){
    ConnectModel model = new ConnectModel(6, 7);
    ConnectView view = new ConnectView();
    while(true){
      view.showBoard(model.getBoard());
      view.showTurn(model.getCurrentPlayer());
      try{
        if(model.makeMove(view.showMenu())){
          if(model.checkWin() || model.checkDraw()){
            break;
          }
          model.nextPlayer();
        }
      }catch(Exception e){
        view.showError(e.getMessage());
      }
    }
    if(model.checkWin()){
      view.showEndGame(model.getCurrentPlayer());
    }else{
      view.showEndGame(0);
    }
  }
  
}

```

This method uses methods in the view and model classes to get the game to work. For example, if we start inside of the while loop, we see the following steps:

1. The game prints the current board to the screen.
1. The game prints a message for the current user.
1. The game then asks the user for input, and uses that input to make a move.
   1. If the move is successful, it checks to see if the game is over. If so, it exits the loop.
   1. If the move is unsuccessful, an exception is thrown and then caught and handled. The program repeats so the user has another opportunity to move.
1. Finally, once the program exits the loop, it will print a message giving the outcome of the game.

That's all there is to it! Once again, our `main()` method ends up being an outline of our program. In this case, almost every line of code is calling a method in both the model and the view, combining them in such a way as to make the program work seamlessly.

Try it out.