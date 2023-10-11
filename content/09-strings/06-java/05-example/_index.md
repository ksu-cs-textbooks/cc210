---
title: "A Worked Example"
pre: "5. "
weight: 50
---

<!-- {{% youtube OFE9NpUkJXo %}}-->

<!-- [Video Materials]({{<relref "./video">}}) -->

<!-- TODO Update Video -->

Now that we've explored all of the different ways we can use strings in our programs, let's walk through a worked example to see how we would go about building a useful program that uses everything we've learned so far. 

## Problem Statement

Consider the following problem statement:

> Write a program that will calculate weighted grades for students in a college course. This program should only have a `main` method.  

> The input will be given in a comma-delimited format. The first line will contain a number of weights as floating-point numbers, separated by commas. The first entry should be ignored.

> All input will be via the keyboard.

> Each subsequent line of input will contain information for a student. The first entry on that line will contain that student's name. The rest of the line will contain that student's scores on each assignment as an integer value, separated by commas. Input will be terminated by the end of the input file, or by a blank line when input is provided via the terminal. 

> It is guaranteed that at least two lines of input will be provided, the first containing the weights and at least one additional line containing data for a student. In addition, it is guaranteed that each line of input will contain the same number of parts. 

> The program should output the student's name, followed by a colon, and a space, and then the student's score. The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point. 

Complete your solution to this example in `Example.java`, which is open to the left. 

## Sample Inputs & Outputs

Here's an example of the expected input for the program:

```tex
Name,0.125,0.125,0.25,0.50
StudentA,75,80,85,90
StudentB,5,15,75,20
StudentC,85,90,70,75
```

Here is the correct output for that input:

```tex
StudentA: 85.63
StudentB: 31.25
StudentC: 76.88
```
##  Think and Design Before Coding

Start by sketching the control flow, what kind of loops are appropriate, what variables and arrays will be necessary?   What packages will need to be imported?

## Handling Input

Next, start with our standard program preamble that we've worked with previously in this course:

```java
// Load required classes
import java.util.Scanner;


public class Example{
  
  public static void main(String[] args) throws Exception{
    
    // Scanner variable
    Scanner reader;
    reader = new Scanner(System.in);
   
    /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */
    
  }
  
}
```

For the rest of this example, we'll look at a smaller portion of the code. That code can be placed where the `MORE CODE GOES HERE` comment is in the skeleton above. 

## Parsing Weights

Next, we'll need to parse the weights provided on the first line of the input. So, we can begin by reading that line of input:

```java
String weightLine = reader.nextLine();
```

Then, we can separate that line into its individual parts using the `split()` method:

```java
String weightLine = reader.nextLine();
String[] weightParts = weightLine.split(",");
```

Once we've done that, we can populate an array of floating point numbers containing the weights. To do this, we know that the number of weights is one less than the size of the `weightParts` array. However, to make things simpler, we'll simply create an array with the same size and leave the first element blank. This will help us when we perform the second step below.

```java
String weightLine = reader.nextLine();
String[] weightParts = weightLine.split(",");

double[] weights = new double[weightParts.length];
```

Next, we can iterate through the `weightParts` array, and parse each entry to a floating point value and store it in the `weights` array. In this case, we'll use a **For** loop, but this time we'll start iterating at 1 instead of 0. In this way, we'll skip the first entry in `weightParts`, which cannot be converted to a floating point value.

```java
String weightLine = reader.nextLine();
String[] weightParts = weightLine.split(",");

double[] weights = new double[weightParts.length];

for(int i = 1; i < weights.length; i++){
  weights[i] = Double.parseDouble(weightParts[i].trim());
}
```

Inside of the **For** loop, we are simply converting each element of `weightParts` to a floating point value, and then storing the result in the corresponding element in `weights`.

Also, notice that we're using `weights.length` in the Boolean condition of this **For** loop. In this case, we know that both arrays are the same size, so we can use either `weights.length` or `weightParts.length` here. 

{{% notice info "String.trim()" %}}

It is a generally good habit to always `.trim()` your inputs before parsing if leading/trailing whitespace is unimportant.  In our example

```
Name, 0.125, 0.125, 0.25, 0.50
```
would crash the program if `.trim()` were not used.  

{{% /notice %}}

## Parsing Each Student

Once we've read the weights, we can parse the data for each student, calculate the result, and print the output, all in a single step. 

First, since we are reading an unknown number of lines of input, we'll need to use a **While** loop. We saw this loop earlier in this chapter, when we learned about how to handle parsing input of an unknown length. 

```java

String line = " ";
while(line.length() > 0){
  line = reader.nextLine();
  if(line.length() > 0){
     // parse the input
  }
  
}
```

Inside of that loop, once we've determined that we've indeed read a valid line of input, we can use the same `split()` method as before to split the input into parts:

```java
  
  String[] parts = line.split(",");


```

Then, we want to calculate the student's final grade. So, once again, we'll create a sum variable and iterate through all of the parts. As before, we'll start the **For** loop at 1, just to skip the first element for now:

```java
  String[] parts = line.split(",");
  
  double totalScore = 0.0;
  for(int j = 1; j < parts.length; j++){
    totalScore += weights[j] * Integer.parseInt(parts[j].trim());
  }

```

Inside of the **For** loop, we'll multiply the weight of the assignment by the score. Since we don't need to store the integer value of each score, we can simply convert it to an integer and then directly use it in our expression. 

## Formatting Output

Finally, we'll need to provide our output as a formatted string. Since we want to make sure the output of the `totalScore` variable is exactly 5 characters wide, with 2 characters after the decimal point, we'll use the placeholder `%5.2f` in the format string:

```java
  System.out.println(String.format("%s: %5.2f", parts[0], totalScore));

```

In the output line, we are providing `"%s: %5.2f"` as the first input to the `String.format()` method. In this way, we don't have to create a separate variable to store the format string, simplifying our code. Then, the second input is the first element in the `parts` array, which will contain the student's name. Finally, the last input is the `totalScore` variable, giving the student's total score. 

