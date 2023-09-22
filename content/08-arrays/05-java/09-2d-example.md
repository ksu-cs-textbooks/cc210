---
title: "A 2D Worked Example"
pre: "9. "
weight: 90
---

<!-- {{% youtube UifEDirtLl8 %}} -->

<!-- [Video Materials]() -->

<!-- TODO Update Video -->

Let's do one more example, this time with multidimensional arrays using `Matrix.java` and `MatrixDriver.java`.

## Problem Statement

Let's see if we can write a program that solves this problem statement:

> Write a program to print the transposition of a two dimensional array. Begin reading two numbers, `m` and `n`, as input from the keyboard, with `m` representing the number of rows in the array and `n` representing the number of columns. If either input is 0 or less, output "Error - Invalid Input!" and terminate the program.

> Otherwise, the program should then read `m * n` integer inputs from the keyboard and place them into the array, filling up each row before moving to the next row. 

> Once all inputs have been accepted, the program should print the transposed version of the array, where the orientation is adjusted so that row i is now column i and column i is row i.

Let's see if we can build a driver and object class program that meets that specification.

## UML Class Diagram

The data is simply an `m * n` 2-dimensional array, or a `m * n` matrix. The `Matrix` class should know its basic dimensions, it should have a way to fill up the matrix and a way to print out its transpose. This class will need access to the keyboard.

The `MatrixDriver` should take keyboard input, instantiate a `Matrix` object, fill it up and then call the object's print transpose method.

![Matrix-Driver UML](/images/08-array/matrix_uml.png)

## Matrix Class

Lets set up the following methods:

* `Matrix(int r, int c)`:  lets have the constructor take the number of rows a columns as parameters AND build an empty `r * c` int array filled with `0`.
* `fillData()`: lets write a function that accepts keyboard input and fills up the matrix, row-by-row, column-by-column.
* `printTranspose()`: print out the transpose of the matrix, or the rows and columns switched.

The transpose and fill operations can be tricky.  As always, start with a sketch of their control flow, paying attention to the types of loops you may want to use as well as the number of arrays you will need.  Don't forget to import `java.util.Scanner`.

Start by declaring `Matrix`'s instance attributes

```java
public int rows;
public int columns;
public int[][] matrix;
```

### `Matrix()`

Our constructor should accept two integer arguments, `rows` and `columns` and initialize three instance attributes.

```java
public Matrix(int rows, int columns){
    this.rows = rows;
    this.columns =  columns;
    matrix = new int[rows][columns];
}
```

### `fillData()`

This method should accept `m * n` keyboard inputs and place them in the matrix.  It actually makes sense to use multiple nested **For** loops, one for each dimension of the array. Consider the following code:

```java
Scanner scanner = new Scanner(System.in);
for(int row = 0; row < this.rows; row++){          // each row
    for(int col = 0; col < this.columns; col++){   // each column or element
        matrix[row][col] = scanner.nextInt();      //get keyboard input
    }
}
```

In this code, we have one **For** loop that loops through each row in the list; here `row` is the index of the row .  Then, inside of that loop, there is a second **For** loop using `col` to march through each column (element) of that row. 

Inside of that loop, we can use `row` and `col` as indices to access a particular element in our list. In this way, we'll fill up the list, starting with the entire first row, then the second row, and so on.


### `printTranspose()`

Finally, we want to print the transposed version of this list. As it turns out, it is very simple to do that by changing the order of our **For** loops:  

```java
for(int col = 0; col < this.columns; col++){
    for(int row = 0; row < this.rows; row++){ 
        System.out.print( matrix[row][col] + " ");
    }
    System.out.println();
}
```

We iterate first through the columns, then through the rows.  In this case, we will print each item in the first column from each row, but they will be printed on a single line, separated by spaces. So, in this way, the first column will be displayed as a row. Then, we'll go to the next column, and print it as a single row. 

Finally, notice the inclusion of an empty `println` after the innermost **For** loop, but still inside the other loop. This will simply end the line of output for the current column by printing a new line to the terminal.

## The Driver

The driver should take command line arguments as input, instantiate a Matrix object, fill it up and then call the object's print transpose method. The number of rows will be the first command-line argument, and the number of columns will be the second command-line argument.

The skeleton of `MatrixDriver` might look like

```java
import java.util.Scanner;

public class MatrixDriver{
    
    public static void main(String[] args){
        // read a number of rows and columns from the keyboard
        // check if the numbers are valid - if not print an error and quit
        // create a matrix object of that size
        // fill the matrix with data
        // print the transposed matrix
    }
}
```

The rest is straight forward and left for you to do. The `Driver` class is not graded for this example.