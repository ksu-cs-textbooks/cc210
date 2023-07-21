---
title: "Tuples"
pre: "5. "
weight: 50
---

<!-- TODO restore previous version from video? -->

The last data structure we will explore is the **tuple**. A _tuple_ in mathematics is defined as a "finite ordered list" of items. So, it is a list of items that is not infinite, and the ordering of the items in that list matters. 

Some languages, such as Python, provide support for tuples directly in the language itself or as part of the standard library. Java, however, does not provide native support for a data structure that is exactly like a tuple. Nearly every language implements the tuple as an immutable data type.

Instead, we'll learn how to construct our own tuple, and see how it could be used in a couple of useful contexts.

## Creating a Tuple

To create a tuple in Java, we must first create a class to store the data. This is a simple class that usually includes two or more public fields to store the data. For example, we could create a tuple that will store two integers like this:

```java
public class IntTuple{
  private final int FIRST;
  private final int SECOND;
  
  public IntTuple(int one, int two){
    this.FIRST = one;
    this.SECOND = two;
  }
  public int getFIRST(){
      return this.FIRST;
  }
  public int getSECOND(){
      return this.SECOND;
  }

}
```

This is a very simple class that stores two integers as fields `first` and `second`, and also includes a constructor to help populate those two values.  The data is made immutable by declaring the instance variables `private final`, assigning to them in the constructor, and only providing getters[^1].

[^1]: It is technically sufficient to declare them as `final`, the private and getter only is admittedly overkill.

We may also want to add a couple of features to our tuple class. First, we can implement the `toString()` method to provide a string representation of this item. This is helpful anytime we need to print some debugging output:

```java
@Override
public String toString(){
  return String.format("(%d, %d)", this.FIRST, this.SECOND);
}
```

In addition, we may want to implement an `equals()` method. That method is also included as part of every object in Java, and it is used to determine if two objects are equal to each other. By default, it will simply check to see if they are exactly the same _instance_ of the object. For tuples, we might want to simply check and see if they store the same _values_, regardless of whether they are the same instance. So, to implement that method, we could include the following code:

```java
@Override
public boolean equals(Object obj){
  //check of obj is null
  if(obj == null){
    return false;
  }

  // check if they are the same instance
  if(this == obj){
    return true;
  }
  
  // check if obj is same type
  if(!(obj instanceof IntTuple)){
    return false;
  }
  
  // cast to same type
  IntTuple tuple = (IntTuple)obj;
  
  // check if all fields are the same
  return tuple.getFIRST() == this.FIRST && tuple.getSECOND() == this.SECOND;
}
```

First, notice that the `equals()` method accepts a Java `Object` as input. This is because we can provide _any_ object as input. So, our `equals()` method must handle any type of object, so it has to include extra code to check the type of the object as well as the values it contains. 

Next, notice that we are very careful to first check that the parameter provide is not null before using it. Again, we have no guarantee that the value we are provided has even been initialized, so we must make sure it is before continuing. 

Finally, if we've determined that the object provided is indeed a valid `IntTuple` instance, we can _cast_ it to that type and check the values of each field to see if they match. 

## Using a Tuple

One of the most useful ways to use a tuple is when we need to store associated values in a data structure, or if we want to return multiple values from a function.

The classic example for tuples is representing coordinates in space, such as a two-dimensional game. In this way, we could create a list of tuples to represent items in the game, and we can even return both the `x` and `y` coordinates of an item in a single tuple. 

## Example

To really explore how we could use a tuple in our code, let's build a simple program. Here's a problem statement:

> Write a program that will read multiple lines of input from the terminal.

> The program should implement a simple search game. Players will guess coordinates on a 10x10 grid, trying to find a hidden item. So, input will take the form of two integers, separated by a space. If the program is unable to parse an input for any reason, it should print "Invalid Input!" and terminate the program.

> When a player makes a guess, the program should respond with one of the four cardinal directions: "North", "South", "East", "West", indicating the direction of the hidden item from the guess. For simplicity, the program will only respond "North" or "South" if the player's guess is not on the same row, or `x` coordinate, as the location, and "East" or "West" only if the player's guess is on the same row as the location. If the player guesses correctly, simply print "Found!" and terminate the program. If the player repeats a guess, the program should print "Repeat!" instead of a cardinal direction. 

> The hidden location should be randomly generated and stored in an instance of the `IntTuple` class defined above as a global variable, and the program should maintain a global list of `IntTuples` representing the locations already guessed.

> The program should be implemented as two functions: `main()` that handles reading input and printing output, and a `makeGuess()` function that accepts two integers, `x` and `y` as parameters, and responds with a string representing the result of that guess. 

Let's see if we can build this program using our `IntTuple` class as defined above. 

## `main` Function

First, let's look at the main function. Once again, we'll start with skeleton code that is very similar to the other examples in this chapter:

```java
import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;
import java.lang.ArrayIndexOutOfBoundsException;
import java.util.Random;
import java.util.List;
import java.util.LinkedList;

public class TupleExample{
  
  public static List<IntTuple> guesses;
  public static Random random;
  public static IntTuple location;
  
  public static void main(String[] args){
    try{
      Scanner reader = new Scanner(System.in);
      while(reader.hasNext()){
        String[] inp = reader.nextLine().split(" ");
        int x = Integer.parseInt(inp[0]);
        int y = Integer.parseInt(inp[1]);
        String out = makeGuess(x, y);
        System.out.println(out);
        if(out.equals("Found!")){
          return;
        }
      }
      
    }catch(Exception e){
      System.out.println("Invalid Input!");
      return;
    }
  }
  
  public static String makeGuess(int x, int y){

    // MORE CODE GOES HERE
  
  }
}
```

At the top of the class, we have included three static fields to store our list of previous guesses, an `IntTuple` of the correct location, and a random number generator. 

In this code, we are simply reading a line of input, splitting it into two tokens, and then parsing each token to an integer to get the `x` and `y` values of the guess. After that, we can call the `makeGuess()` function with those values, and print the result. Finally, we must check to see if the result is `"Found!"`. If so, we can terminate the program using the `return` keyword.

## `makeGuess` Function

{{% youtube geyyRmH-oIc %}}

[Video Materials]({{<relref "./video">}})

Now that we have our `main()` function written, let's work on the `makeGuess()` function. As we saw on the previous page, we must first make sure our list storing the guesses has been initialized, as well as our random number generator:

```java
public static String makeGuess(int x, int y){
  if(guesses == null){
    guesses = new LinkedList<IntTuple>();
  }
  if(random == null){
    random = new Random();
  }
}
```

In this example, we are using the `LinkedList` class as our list. Again, the choice really doesn't matter at this point, but there are some performance considerations that we could discuss in a future course. 

In addition, we must make sure our random location has been established. So, we'll do that in the code as well:

```java
public static String makeGuess(int x, int y){
  if(guesses == null){
    guesses = new LinkedList<IntTuple>();
  }
  if(random == null){
    random = new Random();
  }
  if(location == null){
    location = new IntTuple(random.nextInt(10), random.nextInt(10));
  }
}
```

Here, we are using the `nextInt()` method of `Random` to generate a number between `0` and `9`, inclusive.

Now we must handle producing the output. First, we need to create a new `IntTuple` for the guess, and then check and see if the guess is correct, or if it has already been guessed:

```java
public static String makeGuess(int x, int y){
  if(guesses == null){
    guesses = new LinkedList<IntTuple>();
  }
  if(random == null){
    random = new Random();
  }
  if(location == null){
    location = new IntTuple(random.nextInt(10), random.nextInt(10));
  }
  IntTuple guess = new IntTuple(x, y);
  if(guess.equals(location)){
    return "Found!";
  }
  if(guesses.contains(guess)){
    return "Repeat!";
  }
}
```

Here, we are using that important `equals()` method we created earlier to determine if two tuples contain the same values. In addition, it is important to remember that the `contains()` method of a list also uses the `equals()` method when determining if the list contains a particular item. In fact, most Java libraries always use the `equals()` method of an object to determine if two objects are equal, so it is important to implement that method in our tuple class.

If we find out that the guess is not the hidden location, then we should store it in our list of guesses:

```java
public static String makeGuess(int x, int y){
  if(guesses == null){
    guesses = new LinkedList<IntTuple>();
  }
  if(random == null){
    random = new Random();
  }
  if(location == null){
    location = new IntTuple(random.nextInt(10), random.nextInt(10));
  }
  IntTuple guess = new IntTuple(x, y);
  if(guess.equals(location)){
    return "Found!";
  }
  if(guesses.contains(guess)){
    return "Repeat!";
  }
  guesses.add(guess);
}
```

Finally, we can handle printing the hints for cases where the guess is not on the same row:

```java
public static String makeGuess(int x, int y){
  if(guesses == null){
    guesses = new LinkedList<IntTuple>();
  }
  if(random == null){
    random = new Random();
  }
  if(location == null){
    location = new IntTuple(random.nextInt(10), random.nextInt(10));
  }
  IntTuple guess = new IntTuple(x, y);
  if(guess.equals(location)){
    return "Found!";
  }
  if(guesses.contains(guess)){
    return "Repeat!";
  }
  guesses.add(guess);
  if(guess.getFIRST() > location.getFIRST()){
    return "North";
  }
  if(guess.getFIRST() < location.getFIRST()){
    return "South";
  }
}
```

Below that, we can assume that the guess is on the same row, so we'll have to handle the cases where the guess is east or west of the location:

```java
public static String makeGuess(int x, int y){
  if(guesses == null){
    guesses = new LinkedList<IntTuple>();
  }
  if(random == null){
    random = new Random();
  }
  if(location == null){
    location = new IntTuple(random.nextInt(10), random.nextInt(10));
  }
  IntTuple guess = new IntTuple(x, y);
  if(guess.equals(location)){
    return "Found!";
  }
  if(guesses.contains(guess)){
    return "Repeat!";
  }
  guesses.add(guess);
  if(guess.getFIRST() > location.getFIRST()){
    return "North";
  }
  if(guess.getFIRST() < location.getFIRST()){
    return "South";
  }
  if(guess.getSECOND() > location.getSECOND()){
    return "West";
  }else{
    return "East";
  }
}
```

There we go! That method will handle producing the output for any guess provided by the user. See if you can complete the code in `IntTuple.java` and `TupleExample.java` to the left, then use the two assessments below to check your program. 

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

