---
title: "Putting it All Together"
pre: "6. "
weight: 60
---


First set the default values in `Ingredient()` to: "flour". 2.75, "cups".


Next lets write a driver program which takes 2 command line arguments, a scale factor and a units string, and prints out the ingredient list for sugar cookies.
The basic ingredients are 
* i1 ("flour", 2.75, "cups")
* i2 ("butter", 1, "cups")
* i3 ("sugar", 1.5, "cups")
* i4 ("baking powder", 2.6, "ml")
* i5 ("baking soda", 15.0, "ml")
* i5 ("vanilla extract", 15.0, "ml")

A typical run might look like:
```
$ java Driver 1 cups
2.75 cups of flour
1.00 cups of butter
1.50 cups of sugar
0.01 cups of baking powder
0.06 cups of baking soda
0.06 cups of vanilla extract
```

## Setting up the Driver Program

First we write the generic driver program and class skeleton:

```java
public class Driver{

   public static void main(String[] args){
   }
    
}
```

## Handling the Command Line

Our program takes 2 command line arguments,  Since it is reasonable to assume that a recipe can be halved or doubled, the scale-factor should be converted into a double.  We know from the UML that the conversion method expects a string for units, so no conversion is necessary.

```java
public static void main(String[] args){
    double scaleFact = Double.parseDouble( ...;
    String printUnits = ... ;
}
```

## Handling an Ingredient

Lets use `i2` as an example.  First we will need to create an object.  We will need to adjust its attributes from the default.  Next we will create a new object, 12_scaled using `.scale()`; then convert i2_scaled to the proper units.  Finally, we will need to print it out.


```java
public static void main (String[] args){
    double scaleFact = Double.parseDouble(...
    String printUnits = ...
    Ingredient i2 = new Ingredient();
    i2.name = "sugar";
    i2.amount = 1.5;
    i2.units="cups";

    // create the scaled ingrd objects
    Ingredient i2_scaled = i2.scale( ...

    // convert the scaled ingredient obj to the correct units
    i2_scaled.convert( ...

    // print the scaled, converted objects in order
    System.out.println(i2_scaled.toString());
```

## You do it

Finish the program.  When you are done, check it for 10 points. The check will verify both the structure and functionality of `main()`.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}
