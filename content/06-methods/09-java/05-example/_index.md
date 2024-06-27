---
title: "A Worked Example"
pre: "5. "
weight: 50
---

<!-- youtube Af776SCHegE -->

[Video Materials]({{% relref "./video" %}})

<!-- TODO Update Video -->

Let's try one more example to get some practice building code that contains multiple methods. This program will convert volumes measured in U.S. standard cups into either fluid ounces, tablespoons, or teaspoons. A program that makes these conversions is useful for anyone cooking or baking.

## Problem Statement[^1]

[^1]: Idea adapted from Gaddis, Tony "Starting out with JAVA", 5th ed, Pearson: New York 2012

For this example, we'll need to build a program that matches this problem statement:

> Write a program that accepts interactive keyboard input. It should first ask the user to enter a number of cups, and then have the user select the desired conversion from a list of options. The program will then calculate the correct value and display it with the correct units.

> The program should contain one class named `Converter`, but may contain several methods.

```tex
Please enter the number of cups to convert as a floating-point value: .5
Select conversion: 1 (ounces), 2 (tablespoons) or 3 (teaspoons): 3
24.0 teaspoons
```
That seems like a pretty straightforward problem statement. Let's see how we might structure the program.

## Methods

First, we could look at the problem statement and try to divide the program into a number of methods to perform each action. In this case, it looks like we have a few important actions that could be made into methods:

1. Getting the user input
1. Performing the conversion
1. Printing the converted value and units

Based on that breakdown, we can structure the class so it has the following methods:

* `void main(String[] args)` - this is the usual main method for Java. In this case, we'll handle input and output in this method
* `String convert(double cups, int units)` - this method will help us select the proper conversion to be performed based on user input
* `double toOunces(double cups)` - this method will convert the given number of cups to fluid ounces
* `double toTablespoons(double cups)` - this method will convert the given number of cups to tablespoons
* `double toTeaspoons(double cups)` - this method will convert the given number of cups to teaspoons

## Control Flow

Now that we have an idea of what methods we need, let's discuss the overall control flow of the program and the order in which the methods will be used.

The program will start in the `main` method, just like any other Java program. That method will prompt the user to input a number of cups to be converted, and also will ask the user to choose which conversion to be performed. Once we have those two inputs, we can then perform the computation in the program.

At that point, the `main` method will call the `convert` method and provide the two inputs as arguments to that method call. We'll use the `convert` method to determine which of the other methods to call, based on the `units` parameter. That method will then call the appropriate conversion method (either `toOunces`, `toTablespoons` or `toTeaspoons`) and then use the value returned by that method to build the output string.

Each conversion method is very simple - it just uses a bit of math to convert the value in `cups` to the appropriate value for a different unit of measurement, and then it will return that value.

## Scaffolding the Program

Now that we've decided what methods to include, we can go ahead and start building the overall structure for our program. It should contain a single class named `Converter` and the methods listed above. Finally, since we are reading input interactively from the terminal, we'll also need to remember to import the `java.util.Scanner` class. So, our overall structure might look like this:

```java
import java.util.Scanner;

public class Converter{

    public static void main(String[] args){
        // Create scanner to read input
        Scanner scanner = new Scanner(System.in);
        // more code here
    }

    static String convert(double cups, int units) {
        // more code here
        return "";
    }

    static double toOunces(double cups){
        // more code here
        return -1.0;
    }

    static double toTablespoons(double cups){
        // more code here
        return -1.0;
    }

    static double toTeaspoons(double cups){
        // more code here
        return -1.0;
    }
}
```

Notice that each method signature includes the modifiers `public` and `static` along with the return type, name of the method, and a list of parameters expected. For every method that returns a value, we've also included a default `return` statement so that the code will compile at this point. Methods that have `void` as a return type, such as the `main` method, don't need to include a `return` statement.

Also, the order in which the methods are declared inside of a class does not matter in Java. By convention, the `main` method is typically either the first or the last method declared in the class. 

## Conversion Methods

Next, we can start filling in the code for the methods. Typically we'd either want to start with the main method, or start with the methods that will be called last in the control flow. In this example, let's start with the methods that will be called last, which are the conversion methods `toOunces`, `toTablespoons`, and `toTeaspoons`. 

We can start with the `toOunces` method. A standard cup is 8 fluid ounces. So, our method would include this code:

```java
public static double toOunces(double cups){
    return cups * 8.0;
}
```

That method turns out to be very simple! We can use the same process to write the other two methods. Some helpful conversions:

* 1 cup is 8 fluid ounces
* 1 cup is 16 tablespoons
* 1 cup is 48 teaspoons

### Testing Methods

At this point we've written some code, and we may want to test these methods just to make sure they are working before moving on. So, we can write some code in our `main` method to quickly call these methods and check their return values. Here's a quick example:

```java
public static void main(String[] args){
    // testing code - DELETE BEFORE SUBMITTING
    System.out.println("1 cup should be 8 ounces : " + toOunces(1.0));
    System.out.println("1 cup should be 16 tablespoons : " + toTablespoons(1.0));
    System.out.println("1 cup should be 48 teaspoons : " + toTeaspoons(1.0));

    // Create scanner to read input
    Scanner scanner = new Scanner(System.in);
    // more code here
}
```

If we put that code in the `main` method and run it, we should see output similar to this:

![Converter Example](/images/06-method/converter_example.png)

That's great! That means our methods are working and seem to be returning the correct values. We may want to try a few other values besides 1 cup just to be sure that the output exactly matches what it should be. 

## `convert` Method

The `convert` method contains the logic for selecting the appropriate conversion method, calling it, and then returning a formatted string to be printed. This method requires two parameters: the `cups` value to be sent to the conversion method, and the `units` selection from the user that can be used to determine which method to call.

Since the `units` item is a mutually-exclusive choice, it makes sense to use an **if-else if-else** structure in this method:

```java
static String convert(double cups, int units) {
    if(units == 1){
        return toOunces(cups) + " ounces";
    } else if (units == 2){
        return toTablespoons(cups) + " tablespoons";
    } else if (units == 3){
        return toTeaspoons(cups) + " teaspoons";
    } else {
        // error condition
        return "";
    }
}
```

## Main Method

Finally, we can write our `main` method. It should prompt the user for the number of cups and the units to be converted to. It will then call the `convert` method and print the answer. We should delete our testing code from the `main` method at this point.

```java
public static void main(String[] args){
    // Create scanner to read input
    Scanner scanner = new Scanner(System.in);
    System.out.print("Please enter the number of cups to convert as a floating-point value: ");
    double cups = Double.parseDouble(scanner.nextLine());
    System.out.print("Select conversion: 1 (ounces), 2 (tablespoons) or 3 (teaspoons): ");
    int units = Integer.parseInt(scanner.nextLine());
    String output = convert(cups, units);
    System.out.prinltn(output);
}
```

With that code in place, we should be able to compile and test our program!