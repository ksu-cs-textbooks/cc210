---
title: "A Worked Example"
pre: "6. "
weight: 60
---

Let's put this all together by finishing our project with a full worked example. We want to use our `Ingredient` class to help us bake some sugar cookies. Unfortunately, the recipe uses both cups and milliliters interchangeably, and we want to be able to scale the recipe up or down depending on how many batches we need to make.

The recipe that we have is as follows:

* 2.75 cups of flour
* 1 cup of butter
* 1.5 cups of sugar
* 2.6 ml of baking powder
* 15.0 ml of baking soda
* 15.0 ml of vanilla extract

First, let's start with our existing `Ingredient` class from this module:

```java
public class Ingredient{
    public String name;
    public double amount;
    public String units;

    public Ingredient(){
        this.name = "flour";
        this.amount = 2.0;
        this.units = "cup";
    }

    public Ingredient(String name, int amount, String units){
        this.name = name;
        this.amount = amount;
        this.units = units;
    }

    public String toString(){
        return String.format("%.2f",amount) + " " + units + " of " + name;
    }

    public void convert(String units){
        if (this.units.equals("cups") && units.equals("ml")){
            this.units = "ml";
            amount *= 236.588;
        }else if(this.units.equals("ml") && units.equals("cups")){
            this.units = "cups";
            amount /= 236.588;
        }
    }

    public Ingredient scale(double factor){
        Ingredient output = new Ingredient();
        output.name = this.name;
        output.units = this.units;
        output.amount = this.amount * factor;
        return output;
    }

}

```

To complete this example, we want to write a `Driver` class that uses two user inputs - a value for units and a scaling factor. It should then print out the ingredient list for sugar cookies using those units, and scaled by the given scaling factor. 

## Setting up the Driver Program

First we write the generic driver program and class skeleton:

```java
import java.util.Scanner;

public class Driver{

   public static void main(String[] args){

   }
    
}
```

## Handling the Input

Our program takes 2 inputs. First, we should ask the user which units should be used. Since we only have two options, it makes sense to just offer those options and allow the user to input a number to select from them. For the scaling factor, we can just ask for any decimal value:

```java
public static void main(String[] args){
    Scanner scanner = new Scanner(System.in);
    System.out.println("Enter 1 for cups or 2 for ml: ")
    int option = scanner.nextInt();
    while(!(option == 1 || option == 2)){
        System.out.println("Error! Unrecognized option");
        System.out.println("Enter 1 for cups or 2 for ml: ")
        option = scanner.nextInt();
    }
    String units = "";
    if (option == 1){
        units = "cups";
    }else {
        units = "ml";
    }

    System.out.println("Enter a scaling factor as a decimal number: ");
    double scaleFactor = scanner.nextDouble();

    // more code here. 
        
}
```

## Handling an Ingredient

Now that we have our input, we can handle the first ingredient. We need to create an object that represents 2.75 cups of flour, then convert it, scale it, and print it.

```java
    // Create the object
    Ingredient flour = new Ingredient("flour", 2.75, "cups");

    // Scale the ingredient - this returns a new object
    Ingredient scaledFlour = flour.scale(scaleFactor);

    // Convert the units - this updates the object
    scaledFlour.convert(units);

    // Print the output
    System.out.println(scaledFlour);
```

To finish the program, we can repeat the same process for all ingredients. This is left as an exercise for the reader!
