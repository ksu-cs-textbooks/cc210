---
title: "A Worked Example"
pre: "4. "
weight: 40
---

{{% youtube n3_3dxzlMD4 %}}

[Video Materials]({{<relref "./video">}})

Now that we've seen how to handle working with files in Java, let's go through an example program to see how we can apply that knowledge to a real program.

## Problem Statement

Here's a problem statement we can use:

> Write a program that accepts three files as command line arguments. The first two represent input files, and the third one represents the desired output file. If there aren't three arguments provided, either input file is not an existing file, or the output file is an existing directory, print "Invalid Arguments" and exit the program. The output file may be an existing file, since it will be overwritten. 

> The program should open each input file and read the contents. Each input file will consist of a list of whole numbers, one per line. If there are any errors parsing the contents of either file, the program should print "Invalid Input" and exit. As the input is read, the program should keep track of both the count and sum of all even inputs and odd inputs. 

> Once all input is read, the program should create the output file and print the following four items, in this order, one per line: number of even inputs, sum of even inputs, number of odd inputs, sum of odd inputs.

> Finally, when the program is done, it should simply print "Complete" and exit. Don't forget to close any open files!

So, let's break down this problem statement and see if we can build a program to perform this action.

## Parsing Arguments

First, let's handle parsing the command line arguments. So, we can start with a simple program skeleton, containing both a class declaration and a main method declaration:

```java
public class Example{
  public static void main(String[] args){
    
  }
}
```

Next, we'll want to make sure there are exactly three arguments. This is probably best done using an **If-Then** statement, since it makes the code a bit simpler to read than if we would use a **Try-Catch** statement. However, either approach will work.

```java
public class Example{
  public static void main(String[] args){
    if(args.length != 3){
      System.out.println("Invalid Arguments");
      return;
    }
  }
}
```

Next, we'll need to check and make sure that each of the first two arguments is a valid file that we can open. Since we intend to open them anyway, let's just use a **Try with Resources** statement:

```java
import java.util.Scanner;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.nio.file.InvalidPathException;
import java.nio.file.NoSuchFileException;
import java.io.BufferedWriter;
import java.io.IOException;
import java.lang.NumberFormatException;

public class Example{
  public static void main(String[] args){
    if(args.length != 3){
      System.out.println("Invalid Arguments");
      return;
    }
    
    try(
      Scanner scanner1 = new Scanner(Paths.get(args[0]));
      Scanner scanner2 = new Scanner(Paths.get(args[1]));
      BufferedWriter writer = Files.newBufferedWriter(Paths.get(args[2]))
    ){
      
      /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */
      
    }catch(InvalidPathException e){
      System.out.println("Invalid Arguments");
      return;
    }catch(NoSuchFileException e){
      System.out.println("Invalid Arguments");
      return;
    }catch(IOException e){
      System.out.println("Invalid Arguments");
      return;
    }
    
    /* -=-=-=-=- MORE EXCEPTIONS GO HERE -=-=-=-=- */
  }
}
```

There are a few new things in this code that we haven't seen before:

* We can include multiple variables in a **Try with Resources** statement by simply separating them with a semicolon `;`. 
* Since we aren't worrying about reading input from `System.in`, we can just create our Scanner and BufferedWriter objects directly in the **Try with Resources** statement. Actually, this makes the code very straightforward.
* Recall that the `args` variable is actually an array, so we can access additional command line arguments by simply using different array indices. We haven't done that yet, but it should make sense.

Now that we've confirmed that we can open each file, we can start coding the program's logic. For the rest of this example, we'll look at a smaller portion of the code. That code can be placed where the `MORE CODE GOES HERE` comment is in the skeleton above. We'll also need to handle a few more exceptions, which can be added where the `MORE EXCEPTIONS GO HERE` comment is above.

## Logic 

The program's logic should be pretty straightforward. First, we'll need to create loops to read input from each input file:

```java
while(scanner1.hasNext()){
  String line = scanner1.nextLine().trim();
  
}

while(scanner2.hasNext()){
  String line = scanner2.nextLine().trim();
  
}
```

Notice that we are using two separate **While** loops here. Since we are dealing with two different input files that are unrelated, this is the simplest way to go.

Next, we can parse the input to an integer, and then determine if it is even or odd:

```java
while(scanner1.hasNext()){
  String line = scanner1.nextLine().trim();
  int input = Integer.parseInt(line);
  if(input % 2 == 0){
    //even
  }else{
    //odd
  }
}

while(scanner2.hasNext()){
  String line = scanner2.nextLine().trim();
  int input = Integer.parseInt(line);
  if(input % 2 == 0){
    //even
  }else{
    //odd
  }
}
```

Finally, we can add a few state variables to keep track of how many of each type we've had, and their sum as well:

```java
int countEven = 0;
int countOdd = 0;
int sumEven = 0;
int sumOdd = 0;

while(scanner1.hasNext()){
  String line = scanner1.nextLine().trim();
  int input = Integer.parseInt(line);
  if(input % 2 == 0){
    countEven += 1;
    sumEven += input;
  }else{
    countOdd += 1;
    sumOdd += input;
  }
}

while(scanner2.hasNext()){
  String line = scanner2.nextLine().trim();
  int input = Integer.parseInt(line);
  if(input % 2 == 0){
    countEven += 1;
    sumEven += input;
  }else{
    countOdd += 1;
    sumOdd += input;
  }
}
```

## Exceptions

In the new code above, we are converting strings to integers, which could result in a NumberFormatException. So, we'll need to add one more `catch` block to the **Try with Resources** statement in the skeleton at the top of this page:

```java
catch(NumberFormatException e){
  System.out.println("Invalid Input");
  return;
}
```

That will handle any problems with the input files themselves. 

## Printing Output

Finally, we can simply print our four variables to the output file:

```java
int countEven = 0;
int countOdd = 0;
int sumEven = 0;
int sumOdd = 0;

while(scanner1.hasNext()){
  String line = scanner1.nextLine().trim();
  int input = Integer.parseInt(line);
  if(input % 2 == 0){
    countEven += 1;
    sumEven += input;
  }else{
    countOdd += 1;
    sumOdd += input;
  }
}

while(scanner2.hasNext()){
  String line = scanner2.nextLine().trim();
  int input = Integer.parseInt(line);
  if(input % 2 == 0){
    countEven += 1;
    sumEven += input;
  }else{
    countOdd += 1;
    sumOdd += input;
  }
}

writer.write("" + countEven);
writer.newLine();
writer.write("" + sumEven);
writer.newLine();
writer.write("" + countOdd);
writer.newLine();
writer.write("" + sumOdd);
writer.newLine();

System.out.println("Complete");
```

The eight lines at the end should be pretty self-explanatory. We can simply print each number, but we'll need to convert them to a string first. The simplest way to do that is simply to use the concatenate operator `+` and concatenate each number with a string, which will automatically convert everything to a string. We'll  also need to remember to print a newline between each of them using the `newLine()` method. Of course, we also need to print `Complete` once we are finished!

## Testing

Once we've completed the code, we can use the button below to test it and see if it works. Don't forget to open the `example.pregrade.html` file that it creates to see detailed feedback from your program. 

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}