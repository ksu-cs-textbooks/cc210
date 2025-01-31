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
  <img class="stretch plain" src="/cc210/images/14-mvc/13.8.j.uml.png">
</section><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .35em"><code class="java">import java.lang.IllegalArgumentException;<br>
public class ConnectModel{<br>
  private int[][] board;
  private int current_player;<br>
  public int getCurrentPlayer(){
    return this.current_player;
  }<br>
  public int[][] getBoard(){ return this.board; }<br>
  // more code here<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .35em"><code class="java">import java.lang.IllegalArgumentException;<br>
public class ConnectModel{<br>
  private int[][] board;
  private int current_player;<br>
  public int getCurrentPlayer(){
    return this.current_player;
  }<br>
  public int[][] getBoard(){ return this.board; }<br>
  <mark>// more code here</mark><br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public ConnectModel(int m, int n){
  if(m &lt; 4 || n &lt; 5){
    throw new IllegalArgumentException("The board
        must be at least 4 x 5");
  }
  this.board = new int[m][n];
  this.current_player = 1;
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public ConnectModel(int[][] board, int current_player){
  if(board.length &lt; 4){
    throw new IllegalArgumentException("Board ...");
  }
  if(board[0].length &lt; 5){
    throw new IllegalArgumentException("Board ...");
  }
  if(current_player != 1 && current_player != 2){
    throw new IllegalArgumentException("Current ...");
  }
  this.board = board;
  this.current_player = current_player;
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .32em"><code class="java">public boolean makeMove(int y){<br>
}</code></pre>
  </div>
</section><br>
<section>
  <img class="stretch plain" src="/cc210/images/14-mvc/13.4.connect_wiki.gif">
</section><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .32em"><code class="java">public boolean makeMove(int y){
  if(y &lt; 0 || y >= this.board[0].length){
    throw new IllegalArgumentException("Invalid column");
  }<br>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .32em"><code class="java">public boolean makeMove(int y){
  if(y &lt; 0 || y >= this.board[0].length){
    throw new IllegalArgumentException("Invalid column");
  }
  if(this.board[0][y] != 0){
    throw new IllegalArgumentException("Column full");
  }<br>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .32em"><code class="java">public boolean makeMove(int y){
  if(y &lt; 0 || y >= this.board[0].length){
    throw new IllegalArgumentException("Invalid column");
  }
  if(this.board[0][y] != 0){
    throw new IllegalArgumentException("Column full");
  }
  int row = this.board.length - 1;<br>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .32em"><code class="java">public boolean makeMove(int y){
  if(y &lt; 0 || y >= this.board[0].length){
    throw new IllegalArgumentException("Invalid column");
  }
  if(this.board[0][y] != 0){
    throw new IllegalArgumentException("Column full");
  }
  int row = this.board.length - 1;
  while(board[row][y] != 0){
    row = row - 1;
  }<br>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .32em"><code class="java">public boolean makeMove(int y){
  if(y &lt; 0 || y >= this.board[0].length){
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
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .32em"><code class="java">public boolean checkWin(){<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .32em"><code class="java">public boolean checkWin(){
  // check rows
  for(int i = 0; i &lt; this.board.length; i++){<br>
    for(int j = 0; j &lt; this.board[0].length; j++){<br>
    }
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .32em"><code class="java">public boolean checkWin(){
  // check rows
  for(int i = 0; i &lt; this.board.length; i++){
    int count = 0;
    for(int j = 0; j &lt; this.board[0].length; j++){<br>
    }
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .32em"><code class="java">public boolean checkWin(){
  // check rows
  for(int i = 0; i &lt; this.board.length; i++){
    int count = 0;
    for(int j = 0; j &lt; this.board[0].length; j++){
      if(this.board[i][j] == this.current_player){
        count += 1;
      }else{
        count = 0;
      }<br><br><br>
    }
  }<br>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .32em"><code class="java">public boolean checkWin(){
  // check rows
  for(int i = 0; i &lt; this.board.length; i++){
    int count = 0;
    for(int j = 0; j &lt; this.board[0].length; j++){
      if(this.board[i][j] == this.current_player){
        count += 1;
      }else{
        count = 0;
      }
      if(count >= 4){
        return true;
      }
    }
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .32em"><code class="java">public boolean checkWin(){
  // check rows
  for(int i = 0; i &lt; this.board.length; i++){
    int count = 0;
    for(int j = 0; j &lt; this.board[0].length; j++){
      if(this.board[i][j] == this.current_player){
        count += 1;
      }else{
        count = 0;
      }
      if(count >= 4){
        return true;
      }
    }
  }<br>
  // check columns
  <mark>for(int j = 0; j &lt; this.board[0].length; j++){</mark>
    int count = 0;
    <mark>for(int i = 0; i &lt; this.board.length; i++){</mark>
      if(this.board[i][j] == this.current_player){
        count += 1;
      }else{
        count = 0;
      }
      if(count >= 4){
        return true;
      }
    }
  }<br>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .32em"><code class="java">public boolean checkWin(){
  // check rows
  for(int i = 0; i &lt; this.board.length; i++){
    int count = 0;
    for(int j = 0; j &lt; this.board[0].length; j++){
      if(this.board[i][j] == this.current_player){
        count += 1;
      }else{
        count = 0;
      }
      if(count >= 4){
        return true;
      }
    }
  }<br>
  // check columns
  for(int j = 0; j &lt; this.board[0].length; j++){
    int count = 0;
    for(int i = 0; i &lt; this.board.length; i++){
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
  <mark>return false;</mark>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .32em"><code class="java">public boolean checkWin(){
  // check rows
  for(int i = 0; i &lt; this.board.length; i++){
    int count = 0;
    for(int j = 0; j &lt; this.board[0].length; j++){
      if(this.board[i][j] == this.current_player){
        count += 1;
      }else{
        count = 0;
      }
      if(count >= 4){
        return true;
      }
    }
  }<br>
  // check columns
  for(int j = 0; j &lt; this.board[0].length; j++){
    int count = 0;
    for(int i = 0; i &lt; this.board.length; i++){
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
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.m.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .32em"><code class="java">public boolean checkDraw(){
  for(int j = 0; j &lt; this.board[0].length; j++){
    if(this.board[0][j] == 0){
      return false;
    }
  }
  return true;
}<br>
public void nextPlayer(){
  if(this.current_player == 1){
    this.current_player = 2;
  }else{
    this.current_player = 1;
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <img class="stretch plain" src="/cc210/images/14-mvc/stop.png">
  <h3>Check Model Before Continuing!</h3>
</section><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.v.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .32em"><code class="java">import java.util.Scanner;
import java.lang.NumberFormatException;<br>
public class ConnectView{<br>
  public ConnectView(){
    //default constructor
  }<br>
  <mark>// more code here</mark>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.v.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .38em"><code class="java">public void showBoard(int[][] board){
  for(int i = 0; i &lt; board.length; i++){
    for(int j = 0; j &lt; board[0].length; j++){
      System.out.print("[" + board[i][j] + "]");
    }
    System.out.println();
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.v.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .38em"><code class="java">public void showBoard(int[][] board){
  for(int i = 0; i &lt; board.length; i++){
    for(int j = 0; j &lt; board[0].length; j++){
      System.out.print("[" + board[i][j] + "]");
    }
    System.out.println();
  }
}</code></pre><pre class="stretch" style="font-size: .5em"><code class="md">[1][2][1][2][1]
[1][2][1][2][1]
[1][2][1][2][1]
[1][2][1][2][1]
[1][2][1][2][1]</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .38em"><code class="java">public int showMenu(){
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
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .38em"><code class="java">public int showMenu(){
  <mark>while(true){</mark>
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
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .38em"><code class="java">public int showMenu(){
  while(true){
    try{
      Scanner reader = new Scanner(System.in);
      System.out.println("Which column would you like to place a token in?");
      String input = reader.nextLine().trim();
      <mark>int out = Integer.parseInt(input);</mark>
      return out;
    }catch(NumberFormatException e){
      System.out.println("Invalid input! Please enter a number");
    }catch(Exception e){
      System.out.println("Unable to read input!");
      return -1;
    }
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .38em"><code class="java">public int showMenu(){
  while(true){
    try{
      Scanner reader = new Scanner(System.in);
      System.out.println("Which column would you like to place a token in?");
      String input = reader.nextLine().trim();
      int out = Integer.parseInt(input);
      return out;
    }catch(<mark>NumberFormatException e</mark>){
      System.out.println("Invalid input! Please enter a number");
    }catch(Exception e){
      System.out.println("Unable to read input!");
      return -1;
    }
  }
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .38em"><code class="java">public int showMenu(){
  while(true){
    try{
      Scanner reader = new Scanner(System.in);
      System.out.println("Which column would you like to place a token in?");
      String input = reader.nextLine().trim();
      int out = Integer.parseInt(input);
      <mark>return out;</mark>
    }catch(NumberFormatException e){
      System.out.println("Invalid input! Please enter a number");
    }catch(Exception e){
      System.out.println("Unable to read input!");
      return -1;
    }
  }
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .38em"><code class="java">public int showMenu(){
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
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 40%">
    <img class="plain" style="width: 100%" src="/cc210/images/14-mvc/13.8.j.v.png">
  </div>
  <div style="width: 60%">
    <pre class="stretch" style="font-size: .31em"><code class="java">public void showTurn(int player){
  System.out.println("It is player " + player + "'s turn!");
}<br>
public void showEndGame(int winner){
  if(winner == 0){
    System.out.println("The game is a draw!");
  }else{
    System.out.println("Player " + winner + " wins!");
  }
}<br>
public void showError(String error){
  System.out.println("Error: " + error);
}</code></pre>
  </div>
</section><br><br>
<section>
  <img class="stretch plain" src="/cc210/images/14-mvc/stop.png">
  <h3>Check View Before Continuing!</h3>
</section><br>
<section>
  <img class="stretch plain" src="/cc210/images/14-mvc/13.8.j.uml.png">
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .38em"><code class="java">public class ConnectController{<br>
  public static void main(String[] args){<br>
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .38em"><code class="java">public class ConnectController{<br>
  public static void main(String[] args){
    ConnectModel model = new ConnectModel(6, 7);
    ConnectView view = new ConnectView();<br>
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .38em"><code class="java">public class ConnectController{<br>
  public static void main(String[] args){
    ConnectModel model = new ConnectModel(6, 7);
    ConnectView view = new ConnectView();
    while(true){<br>
    }
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .38em"><code class="java">public class ConnectController{<br>
  public static void main(String[] args){
    ConnectModel model = new ConnectModel(6, 7);
    ConnectView view = new ConnectView();
    while(true){
      view.showBoard(model.getBoard());
      view.showTurn(model.getCurrentPlayer());<br>
    }<br>
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .38em"><code class="java">public class ConnectController{<br>
  public static void main(String[] args){
    ConnectModel model = new ConnectModel(6, 7);
    ConnectView view = new ConnectView();
    while(true){
      view.showBoard(model.getBoard());
      view.showTurn(model.getCurrentPlayer());
      try{<br><br><br><br><br><br>
      }catch(Exception e){
        view.showError(e.getMessage());
      }
    }<br>
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .38em"><code class="java">public class ConnectController{<br>
  public static void main(String[] args){
    ConnectModel model = new ConnectModel(6, 7);
    ConnectView view = new ConnectView();
    while(true){
      view.showBoard(model.getBoard());
      view.showTurn(model.getCurrentPlayer());
      try{
        if(model.makeMove(view.showMenu())){<br><br><br><br>
        }
      }catch(Exception e){
        view.showError(e.getMessage());
      }
    }<br>
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .38em"><code class="java">public class ConnectController{<br>
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
    }<br>
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .38em"><code class="java">public class ConnectController{<br>
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
  }<br>
}</code></pre>
  </div>
</section><br>