---
type: "reveal"
hidden: true
---
<section>
	<h2>Problem Statement</h2>
</section>
<section>
  <p style="font-size: .7em">Write a program to play the traditional version of Connect Four. It should take place on a 6 x 7 game board.</p>
  <p style="font-size: .7em">On each turn, the game will print out the state of the board, then alert the current player to make a move. The player's move will consist of a single number, giving the column to place a piece. If the move is invalid, the player will be given the option to select another move.</p>
  <p style="font-size: .7em">After each move is made, the game will determine if the current player has won, or if the game was a draw. To simplify the game, we will not check for diagonal wins.</p>
  <p style="font-size: .7em">The program should be built using MVC architecture.</p>
</section><br>
<section>
  <h2>How to Build?</h2>
	<img class="stretch plain" src="https://media.giphy.com/media/3o7btPCcdNniyf0ArS/source.gif">
  <p class="imagecredit">Image Credit: <a href="https://media.giphy.com/media/3o7btPCcdNniyf0ArS/">Giphy</a></p>
	<p>Use MVC!</p>
</section><br>
<section>
  <img class="stretch plain" src="/cc210/images/14-mvc/13.8.p.uml.png">
</section><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="python">class ConnectModel:<br>
  @property
  def board(self):
    return self.__board<br>
  @property
  def current_player(self):
    return self.__current_player<br>
  # more code here</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="python">class ConnectModel:<br>
  @property
  def board(self):
    return self.__board<br>
  @property
  def current_player(self):
    return self.__current_player<br>
  <mark># more code here</mark></code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="python">def __init__(self, m, n):
  if m &lt; 4 or n &lt; 5:
    raise ValueError("The board must
          be at least 4 x 5")
  self.__board = []
  for i in range(0, m):
    self.__board.append([])
    for j in range(0, n):
      self.__board[i].append(0)
  self.__current_player = 1</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .43em"><code class="python">def load_game(self, board, current_player):
  if len(board) &lt; 4:
    raise ValueError("Board ...")
  if len(board[0]) &lt; 5:
    raise ValueError("Board ...")
  if current_player != 1 and
          current_player != 2:
    raise ValueError("Current ...")
  self.__board = board
  self.__current_player = current_player</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .41em"><code class="python">def make_move(self, y):
  </code></pre>
  </div>
</section><br>
<section>
  <img class="stretch plain" src="/cc210/images/14-mvc/13.4.connect_wiki.gif">
</section><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .41em"><code class="python">def make_move(self, y):
  if y &lt; 0 or y >= len(self.board[0]):
    raise ValueError("Invalid column")
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .41em"><code class="python">def make_move(self, y):
  if y &lt; 0 or y >= len(self.board[0]):
    raise ValueError("Invalid column")
  if self.board[0][y] != 0:
    raise ValueError("Column full")
  </code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .41em"><code class="python">def make_move(self, y):
  if y &lt; 0 or y >= len(self.board[0]):
    raise ValueError("Invalid column")
  if self.board[0][y] != 0:
    raise ValueError("Column full")
  row = len(self.board) - 1
  </code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .41em"><code class="python">def make_move(self, y):
  if y &lt; 0 or y >= len(self.board[0]):
    raise ValueError("Invalid column")
  if self.board[0][y] != 0:
    raise ValueError("Column full")
  row = len(self.board) - 1
  while self.board[row][y] != 0:
    row -= 1
  </code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .41em"><code class="python">def make_move(self, y):
  if y &lt; 0 or y >= len(self.board[0]):
    raise ValueError("Invalid column")
  if self.board[0][y] != 0:
    raise ValueError("Column full")
  row = len(self.board) - 1
  while self.board[row][y] != 0:
    row -= 1
  self.__board[row][y] = self.current_player
  return True</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .38em"><code class="python">def check_win(self):<br>
</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .38em"><code class="python">def check_win(self):
  # check rows
  for i in range(0, len(self.board)):<br>
    for j in range(0, len(self.board[0])):
      </code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .38em"><code class="python">def check_win(self):
  # check rows
  for i in range(0, len(self.board)):
    count = 0
    for j in range(0, len(self.board[0])):<br>
</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .38em"><code class="python">def check_win(self):
  # check rows
  for i in range(0, len(self.board)):
    count = 0
    for j in range(0, len(self.board[0])):
      if self.board[i][j] == self.current_player:
        count += 1
      else:
        count = 0
</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .38em"><code class="python">def check_win(self):
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
</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .38em"><code class="python">def check_win(self):
  # check rows
  for i in range(0, len(self.board)):
    count = 0
    for j in range(0, len(self.board[0])):
      if self.board[i][j] == self.current_player:
        count += 1
      else:
        count = 0
      if count >= 4:
        return True<br>
  # check columns
  <mark>for j in range(0, len(self.board[0])):</mark>
    count = 0
    <mark>for i in range(0, len(self.board)):</mark>
      if self.board[i][j] == self.current_player:
        count += 1
      else:
        count = 0
      if count >= 4:
        return True<br>
 </code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .38em"><code class="python">def check_win(self):
  # check rows
  for i in range(0, len(self.board)):
    count = 0
    for j in range(0, len(self.board[0])):
      if self.board[i][j] == self.current_player:
        count += 1
      else:
        count = 0
      if count >= 4:
        return True<br>
  # check columns
  for j in range(0, len(self.board[0])):
    count = 0
    for i in range(0, len(self.board)):
      if self.board[i][j] == self.current_player:
        count += 1
      else:
        count = 0
      if count >= 4:
        return True<br>
  <mark>return False</mark></code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .38em"><code class="python">def check_win(self):
  # check rows
  for i in range(0, len(self.board)):
    count = 0
    for j in range(0, len(self.board[0])):
      if self.board[i][j] == self.current_player:
        count += 1
      else:
        count = 0
      if count >= 4:
        return True<br>
  # check columns
  for j in range(0, len(self.board[0])):
    count = 0
    for i in range(0, len(self.board)):
      if self.board[i][j] == self.current_player:
        count += 1
      else:
        count = 0
      if count >= 4:
        return True<br>
  return False</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .38em"><code class="python">def check_draw(self):
  for j in range(0, len(self.board[0])):
    if self.board[0][j] == 0:
      return False
  return True<br>
def next_player(self):
  if self.current_player == 1:
    self.__current_player = 2
  else:
    self.__current_player = 1</code></pre>
  </div>
</section><br><br><br>
<section>
  <img class="stretch plain" src="/cc210/images/14-mvc/stop.png">
  <h3>Check Model Before Continuing!</h3>
</section><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.v.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .38em"><code class="python">import sys<br>
class ConnectView:<br>
  def __init__(self):
    # default constructor
    pass<br>
  <mark># more code here</mark></code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.v.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .42em"><code class="python">def show_board(self, board):
  for row in board:
    for square in row:
      print("[{}]".format(square), end="")
    print("")</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.v.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .42em"><code class="python">def show_board(self, board):
  for row in board:
    for square in row:
      print("[{}]".format(square), end="")
    print("")</code></pre><pre class="stretch" style="font-size: .5em"><code class="md">[1][2][1][2][1]
[1][2][1][2][1]
[1][2][1][2][1]
[1][2][1][2][1]
[1][2][1][2][1]</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .42em"><code class="python">def show_menu(self):
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
      return -1</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .42em"><code class="python">def show_menu(self):
  <mark>while(True):</mark>
    try:
      print("Which column would you like to place a token in?")
      inp = sys.stdin.readline().strip()
      out = int(inp)
      return out
    except ValueError:
      print("Invalid input! Please enter a number")
    except Exception:
      print("Unable to read input")
      return -1</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .42em"><code class="python">def show_menu(self):
  while(True):
    try:
      print("Which column would you like to place a token in?")
      inp = sys.stdin.readline().strip()
      <mark>out = int(inp)</mark>
      return out
    except ValueError:
      print("Invalid input! Please enter a number")
    except Exception:
      print("Unable to read input")
      return -1</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .42em"><code class="python">def show_menu(self):
  while(True):
    try:
      print("Which column would you like to place a token in?")
      inp = sys.stdin.readline().strip()
      out = int(inp)
      return out
    except <mark>ValueError</mark>:
      print("Invalid input! Please enter a number")
    except Exception:
      print("Unable to read input")
      return -1</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .42em"><code class="python">def show_menu(self):
  while(True):
    try:
      print("Which column would you like to place a token in?")
      inp = sys.stdin.readline().strip()
      out = int(inp)
      <mark>return out</mark>
    except ValueError:
      print("Invalid input! Please enter a number")
    except Exception:
      print("Unable to read input")
      return -1</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .42em"><code class="python">def show_menu(self):
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
      return -1</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.p.v.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .37em"><code class="python">def show_turn(self, player):
  print("It is player {}'s turn!".format(player))<br>
def show_end_game(self, winner):
  if winner == 0:
    print("The game is a draw!")
  else:
    print("Player {} wins!".format(winner))<br>
def show_error(self, error):
  print("Error: {}".format(error))</code></pre>
  </div>
</section><br><br>
<section>
  <img class="stretch plain" src="/cc210/images/14-mvc/stop.png">
  <h3>Check View Before Continuing!</h3>
</section><br>
<section>
  <img class="stretch plain" src="/cc210/images/14-mvc/13.8.p.uml.png">
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .40em"><code class="python">from ConnectModel import *
from ConnectView import *
import sys<br>
class ConnectController:<br>
  @staticmethod
  def main(args):<br><br>
# main guard
if __name__ == "__main__":
  ConnectController.main(sys.argv)</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .40em"><code class="python">from ConnectModel import *
from ConnectView import *
import sys<br>
class ConnectController:<br>
  @staticmethod
  def main(args):
    model = ConnectModel(6, 7)
    view = ConnectView()<br><br>
# main guard
if __name__ == "__main__":
  ConnectController.main(sys.argv)</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .40em"><code class="python">from ConnectModel import *
from ConnectView import *
import sys<br>
class ConnectController:<br>
  @staticmethod
  def main(args):
    model = ConnectModel(6, 7)
    view = ConnectView()
    while True:
      view.show_board(model.board)
      view.show_turn(model.current_player)
      try:<br><br><br><br>
      except Exception as e:
        view.show_error(str(e))<br><br>
# main guard
if __name__ == "__main__":
  ConnectController.main(sys.argv)</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .40em"><code class="python">from ConnectModel import *
from ConnectView import *
import sys<br>
class ConnectController:<br>
  @staticmethod
  def main(args):
    model = ConnectModel(6, 7)
    view = ConnectView()
    while True:
      view.show_board(model.board)
      view.show_turn(model.current_player)
      try:
        if model.make_move(view.show_menu()):<br><br><br>
      except Exception as e:
        view.show_error(str(e))<br><br>
# main guard
if __name__ == "__main__":
  ConnectController.main(sys.argv)</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .40em"><code class="python">from ConnectModel import *
from ConnectView import *
import sys<br>
class ConnectController:<br>
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
        view.show_error(str(e))<br><br>
# main guard
if __name__ == "__main__":
  ConnectController.main(sys.argv)</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .40em"><code class="python">from ConnectModel import *
from ConnectView import *
import sys<br>
class ConnectController:<br>
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
      view.show_end_game(0)<br>
# main guard
if __name__ == "__main__":
  ConnectController.main(sys.argv)</code></pre>
  </div>
</section><br>