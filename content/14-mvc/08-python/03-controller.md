---
title: "A Worked Example - Controller"
pre: "3. "
weight: 30
---

Finally, we now can start working on our controller. This is where the program actually comes together and becomes useful. While a program such as Connect Four may seem quite complex, using MVC architecture can make it quite easy to work with. Let's check it out!

## Controller

{{< youtube kUPciOjhbj4  >}}

The `ConnectController` class just contains a single `main()` method:

```python
from ConnectModel import *
from ConnectView import *
import sys

class ConnectController:
  
  @staticmethod
  def main(args):
    model = ConnectModel(6, 7)
    view = ConnectView()
    while True:
      view.show_board(model.board)
      view.show_turn(model.current_player)
      try:
        if model.make_move(view.show_menu()):
          if model.check_win() or model.check_draw():
            break
          model.next_player()
      except Exception as e:
        view.show_error(str(e))
    if model.check_win():
      view.show_end_game(model.current_player)
    else:
      view.show_end_game(0)

# main guard
if __name__ == "__main__":
  ConnectController.main(sys.argv)
```

This method uses methods in the view and model classes to get the game to work. For example, if we start inside of the while loop, we see the following steps:

1. The game prints the current board to the screen.
1. The game prints a message for the current user.
1. The game then asks the user for input, and uses that input to make a move.
   1. If the move is successful, it checks to see if the game is over. If so, it exits the loop.
   1. If the move is unsuccessful, an exception is thrown and then caught and handled. The program repeats so the user has another opportunity to move.
1. Finally, once the program exits the loop, it will print a message giving the outcome of the game.

That's all there is to it! Once again, our `main()` method ends up being an outline of our program. In this case, almost every line of code is calling a method in both the model and the view, combining them in such a way as to make the program work seamlessly.

We can use the terminal to see how it works.