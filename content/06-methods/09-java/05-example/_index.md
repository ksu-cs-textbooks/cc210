---
title: "Example"
pre: "5. "
weight: 50
---

{{% youtube Af776SCHegE %}}

[Video Materials]({{<relref "./video">}})

<!-- TODO Update Video -->

Let's get some more practice creating our own methods by building another example program. This program will perform convert the volume-measurement "cups" into either fluid ounces, tablespoons or teaspoons.

## Problem Statement[^1]

[^1]: Idea adapted from Gaddis, Tony "Starting out with JAVA", 5th ed, Pearson: New York 2012

For this example, we'll need to build a program that matches this problem statement:

> Write a program that accepts terminal input, allowing the user to enter a number of cups, and then selecting the conversion output as: fluid ounces, tablespoons or teaspoons. The program will then calculate the correct value and display it with the correct units.

> The program should contain one class `Example`, and run from the command line with the command `java Example`

> When printing, all decimal values should be rounded to the nearest tenth (one decimal place), use `String.format("%.1f", <value>)` to produce the string. The final output of the program should look similar to the following: 

```tex
Please enter the number of cups to convert:
.5
Select 1 (ounces), 2 (tablespoons) or 3 (teaspoons):
3
24.0 teaspoons
```

That seems like a pretty straightforward problem statement. Lets see how we might structure the program.


## methods

First, we could look at the problem statement and try to divide the program into a number of methods to perform each action. In this case, it looks like we have a few important actions that could be made into methods

1. Getting the user input
1. Performing the conversion
1. Printing the converted value and units

Lets structure the class so it has the following methods


* public static void main(String [] args)-- gets input and prints output, needed so program runs from the command line
* public static String convert(double cups, int units) -- select proper conversion and returns string to print
* public static double toOunce(double cups) -- returns right number of ounces
* public static double toTablespoon(double cups) -- returns right number of tablespoons
* public static double toTeaspoon(double cups) -- returns right number of teaspoons

#### Program "flow"

`main` will get two keyboard entries and convert them to numbers.  `main` will call `convert`, printing the string `convert` supplies.

`convert` will get the correct value for the conversion by calling the proper `to_???` method based on the value it receives as a parameter.  It will use that value to build and return a string.

`to???` takes the value it receives for its parameter, and returns the proper amount.

###  Building the Scaffolding

We can already put together the skeleton of the program

```java
import java.util.Scanner;

public class Example{

    public static void main(String[] args){
        Scanner reader = new Scanner(System.in);
    }

    public static double toOunce(double cup ){
        return -1.;
    }

   public static double toTablespoon(double cup ){
        return -1.;
    }

    public static double toTeaspoon(double cup ){
      return -1.;
    }

    public static String convert (double cup, int units){
        return "";
    }

    private static void TEST(){
    }
}
```
Here we set up the class and the methods.  Notice we have added `TEST()` to hold our tests as we go along. 

For each method we establish its "signature"; its name, return type and parameters.  Because Java is a statically typed language, methods with a non-void return type <b>MUST</b> return a value of the appropriate type.  Here I have chosen the double `-1.` and the empty string (`""`).  This allows the skeleton above to compile. A better choice would have been to throw (cause) an `UnsupportedOperationException`, which would cause the program to crash if an unimplemented method was called--but we haven't gotten to exceptions yet. 

{{% notice info "Order of Method Definitions" %}}

Inside a Java class, it does not matter what order the methods occur. By course convention, `main()` will be the last method in a class.

{{% /notice %}}

### `to_` Methods

We know that 1 cup is 8 fluid ounces, or 16 tablespoons or 48 teaspoons.  So we can complete and test our `to_ounces` method as follows:

```java
import java.util.Scanner;

public class Example{


    public static double toOunce(double cup ){
        return cup * 8.0;
    }

    private static void TEST(){
        double volume = 0.0;  # 0 oz
        double value = Example.to_ounce(volume);
        System.out.println(String.format("%:.1f cups is: %.1f ounces",volume, value));
        System.out.println("Expect 0.0");

        volume = 1. # 8.0 oz
        value = Example.to_ounce(volume)
        System.out.println(String.format("%:.1f cups is: %.1f ounces",volume, value));
        System.out.println("Expect 8.0");

        volume = 0.6 # 4.8 oz
        value = Example.to_ounce(volume)
        System.out.println(String.format("%:.1f cups is: %.1f ounces",volume, value));
        System.out.println("Expect 4.8");
    }

    public static void main(String[] args){
        Scanner reader = new Scanner(System.in);
        TEST();
    }
```

Note how we write one method then test one method.  One could use an input for the tests, `volume = float(reader.readline())`.  However in unit testing (which covers the testing of one method in isolation), it is standard to "hard code" the test values, that way you can be sure you have covered boundary conditions and can pre-calculate the answers.

{{% notice tip "Test Method" %}}

We recommend defining your test method

```java
private static void TEST() {}
```

This will make it impossible for other programs (classes) to access the `TEST` method and provide it access to class features should there be any.  Both these topics will be expanded on in later modules.

{{% /notice %}}

We leave it to you to write and test the the other `to_` methods.

### Convert

`convert()` contains the logic for selecting the appropriate conversion function, calling it and then returning the string to be printed.  

Since the conversions are all mutually exclusive (you must pick exactly one conversion) we will use an IF-ELSE-IF construct.  Something like:

```java
public static String convert (double cup, int units){
    switch (units) {
        case 1: return String.format("%.1f onces", toOunce(cup)); 
        case 2: return String.format("%.1f Tablespoons", toTablespoon(cup));
        case 3: return String.format("%.1f Teaspoons", toTeaspoon(cup));
        default: return "";
    }
}    
    
private static void TEST(){
    double volume = 0.7;
    System.out.println(convert(volume, 1));
    System.out.println("Should be 5.6");                   

    System.out.println(convert(volume, 2));
    System.out.println("Should be 11.2");

    System.out.println(convert(volume, 3));
    System.out.println("Should be 33.6");
                
}

```

In `convert()` we call the appropriate function and build then return the string. Observe how we include an `default` that assigns the returns the empty string. Switch statements should always have a default branch.  Our spec does not tell us what to do if invalid inputs are given, so this is a good default until we learn to throw an `IllegalArgumentException`, wich would crash the program and indicate that an illegal value was passed to the method.

Notice how the test code uses only one value for volume.  We are testing the logic that picks the right method and returns the correct string.  We should have already tested that each `to_` method works correctly for volume conversions; there is no reason to test with different volumes here. 


### `main()`

Finally, we should write `main()`.  It should prompt the user for the number of cups and the units in which to convert it (as ints 1-3).  It should then call convert and print the answer.  We leave `main()` for you to do write and test.

```java
    public static void main(String[] args){
        Scanner reader = new Scanner(System.in);
        // TEST();
        System.out.println("\nPlease enter the number of cups to convert");
        double cup = Double.parseDouble(reader.nextLine());
        System.out.println("Select 1 (onces), 2 (Tablespoons), 3 (teaspoons)");
        int units = Integer.parseInt(reader.nextLine());
        String value = convert(cup,units);
        System.out.println(value);
    }

```

## Grading

When you are ready, use the two grading tests to make sure our program meets the expected specification. Specifically, the first grading test will check to make sure our program contains the following method definitions:

* public static void main(String [] args)
* public static String convert(double cups, int units)
* public static double toOunce(double cups) 
* public static double toTablespoon(double cups) 
* public static double toTeaspoon(double cups)

The second test will check that each method performs the correct operation as shown above. 

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}
