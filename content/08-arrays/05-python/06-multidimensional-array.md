---
title: "Multidimensional List as Array"
pre: "6. "
weight: 60
---

![Checkers board](/images/08-array/checkers.png)

Sometimes you really want an array.  Take a 8 x 8 square checkers[^1] board as an example.  The spaces exist whether or not there is a checker on them, and you don't want moving a piece to "accidentally" change the size of the board. 

[^1]: See <a href= "https://en.wikipedia.org/wiki/Draughts">checkers</a>

Now you can program checkers without a board, just a single list of tuples[^2] showing piece, row and column location--and do a bunch of abstract math every time you want to move, jump or print the board.

[^2]: A `tuple` is an immutable ordered aggregate data type used when the element are of mixed data type are necessary; ex: `a = ("red",2,4 )`

A more conventional approach is to represent the board as an array.  In Python we will "fake" an array using multidimensional lists and the keyword `None`.

A typical 2-D array is `array[row][col]`.  To make a 2-D array with m-rows and n-columns we use an outer list, whose elements represent the rows of a board.  Each board row is represented by a list showing what is in every column.  In the following example we will say empty squares are represented by `None`, regular pieces by "R" or "B" depending on the player and kings by "KR" and "KB".

First we would make the board

```python
board = []
m = 8
n = 8
for row in range(m):    # row is the index number of the current row
    board.append([])    # add an empty list for the column data
    for col in range(n):  # col is the index number of the current column
        board[row].append(None)  # adds a none for each column, the board is empty
print(board)

```
 which will give us something like
 
 ```tex
 [[None, None, None, None, None, None, None, None], [None, None, None, None, None, None, None, None], 
  [None, None, None, None, None, None, None, None], [None, None, None, None, None, None, None, None], 
  [None, None, None, None, None, None, None, None], [None, None, None, None, None, None, None, None], 
  [None, None, None, None, None, None, None, None], [None, None, None, None, None, None, None, None]]
 ```
 
 To put a red piece on row 0, column 1 (a starting location) we would program `board[0][1] = "R"` and the `board` becomes 
  ```tex
 [[None, "R", None, None, None, None, None, None], [None, None, None, None, None, None, None, None], 
  [None, None, None, None, None, None, None, None], [None, None, None, None, None, None, None, None], 
  [None, None, None, None, None, None, None, None], [None, None, None, None, None, None, None, None], 
  [None, None, None, None, None, None, None, None], [None, None, None, None, None, None, None, None]]
 ```
 
Of course you would want to place all the initial pieces, maybe using some kind of loop.

{{% notice info "Checking for None" %}}

In checkers, a piece must move to an empty square.  In our case that square would be represented by `None`.  For the board above `board[4][3] is None` evaluates to `True`, the 4th list's 3rd element is `None`. `board[0][1] is None` evaluates to `False`, we put "R" there. It probably goes without saying that `"None" is None` is False.

For technical reasons, `is None` and `is not None` are a better choices than `== None` and `!= None`; although they often appear to do the same thing.  

{{% /notice %}}

## Keys to using Lists as Arrays

1. Pick a sentinel value to represent "empty" array positions -- this is critical.  We recommend `None`.
1. Always use range and a For-loop to iterate through the array by indices; it will keep the array the correct size.
1. After the initial array is built, always use direct assignment (`board[0][7] = None`) rather than list methods like append(), insert() or remove().  These method resize the array --which is not allowed.

Feel free to use the code to make a 2-D array anywhere you need to.  It can easily be adapted to any dimensions.

## When to use List as an Array

In Python, the default choice should be a list or multi-dimensional used as list (allow the size to vary).  

However, when it is critical the size of the list is constant, allowing you to assign to any set of indices at all times, implement the list as an array (like we did above).  Map applications and board game representations are two areas where arrays tend to be better choices.

<p style="color:red;padding:10"><b>Note:</b> There are also performance reasons to use arrays in some data science and mathematical operations.  Our "fake" array approach does not provide these benefits.  Math frameworks (modules) will implement "real" arrays (which also deal with how the data is organized in computer memory).</p>

