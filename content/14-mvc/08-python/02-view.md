---
title: "A Worked Example - View"
pre: "2. "
weight: 20
---

The next part of any MVC program to build is the view. Depending on the complexity of the problem, sometimes it may be helpful to build the view and the model concurrently. Ideally, however, the model and the view should be properly distinct and separate, such that the model can be fully completed before the view is developed.

Let's review our UML diagram before continuing:

![Connect Four UML Diagram](/images/14-mvc/13.8.p.uml.png)

## View

{{% youtube faqMSYoL77s %}}

The `ConnectView` class only contains a few simple methods. First, let's build the class declaration and the constructor:

```python
import sys

class ConnectView:
  
  def __init__(self):
    # default constructor
    pass
```

Since we aren't initializing a GUI, we'll just need a default constructor for this class. 

Next, let's look at the methods. First, we'll need a method to show the board on the screen, called `show_board()`. Let's see what it looks like:

```python
def show_board(self, board):
  for row in board:
    for square in row:
      print("[{}]".format(square), end="")
    print("")
```

This method is very similar to methods we saw in an earlier module when we learned about arrays. Here, we are simply using two nested **For** loops to print the data in the list, with each row printed on its own line. 

When we run this method, we should get output that looks like this:

```tex
[1][2][1][2][1]
[1][2][1][2][1]
[1][2][1][2][1]
[1][2][1][2][1]
[1][2][1][2][1]
```

The other complex method to implement is the `show_menu()` method, which reads input from the player:

```python
def show_menu(self):
  while(True):
    try:
      print("Which column would you like to place a token in?")
      inp = sys.stdin.readline().strip()
      out = int(inp)
      return out
    except ValueError:
      print("Invalid input! Please enter a number")
    except Exception:
      print("Unable to read input")
      return -1
```

That method will print a prompt to the user, and get a response as a string. Notice that we aren't doing any validation of the input here beyond making sure that it is an integer---we can do that in the controller and the model. 

The final three methods simply print out messages to the user. So, we can implement those pretty easily:

```python
def show_turn(self, player):
  print("It is player {}'s turn!".format(player))
  
def show_end_game(self, winner):
  if winner == 0:
    print("The game is a draw!")
  else:
    print("Player {} wins!".format(winner))
    
def show_error(self, error):
  print("Error: {}".format(error))
```

That's it! The view portion of the program is very simple, but it allows our users to see what is going on and interact with the program. We can use the tests below to make sure our view is working correctly before we continue with the controller.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}