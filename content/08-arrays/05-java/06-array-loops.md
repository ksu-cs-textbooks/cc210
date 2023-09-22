---
title: "Array Loops"
pre: "6. "
weight: 60
---

One of the most powerful ways to use arrays is to combine them with loops. Loops provide an easy way to perform operations on all elements in an array, no matter what the size of the array is.

Let's go back to the flowchart seen earlier in this chapter, and see if we can implement that program in Java.

![Array Iteration Flowchart](/images/08-array/6.3.iteratearray.png)

First, we'll need to start with a program that reads information from the keyboard. Let's place this code in `ArrayLoops.java`, which should be open to the left:

```java
// Load required classes
import java.util.Scanner;

public class ArrayLoops{
  
  public static void main(String[] args) throws Exception{
    
    // Scanner variable
    Scanner reader = new Scanner(System.in);
    
    /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */
    
  }
  
}
```

For the rest of this example, we'll look at a smaller portion of the code. That code can be placed where the `MORE CODE GOES HERE` comment is in the skeleton above. 

## Creating the Array

Looking at the flowchart above, we must first accept one input from the user, an integer `x` that gives the size of the array. Then, we want to create an array named `a` which is able to store those elements. 

```java
int x = Integer.parseInt(reader.nextline());
int[] a = new int[x];
```

In the code, we use our reader to read an integer from the user and store it in `x`. Then, we can declare and initialize an array named `a`, using the value stored in `x` as the size of the array.

## Filling the Array

Next, we'll enter a for loop that reads input from the user, and then places that input into the array we created. Here's what that might look like in Java:

```java
int x = Integer.parseInt(reader.nextLine());
int[] a = new int[x];

for(int i = 0; i < x; i++){
  int y =Integer.parseInt(reader.nextLine());
  a[i] = y;
}
```

Here, we are using a standard **For** loop to iterate over the array. Inside of the loop, we simply read another input from the user, then store that input into the element in the array indicated by our iterator variable `i`. 

## Finding the Sum

Finally, once we've filled the array, we must iterate over each element to find the sum and then print that to the terminal:

```java
int x = Integer.parseInt(reader.nextLine());
int[] a = new int[x];

for(int i = 0; i < x; i++){
  int y = Integer.parseInt(reader.nextLine());
  a[i] = y;
}

int sum = 0;
for(int j : a){
  sum += j;
}

System.out.println(sum);
```

Here, we are using Java's version of a **For Each** loop, known as an **Enhanced For** loop, to iterate over each element stored in the array `a`. The syntax for an **Enhanced For** loop in Java is very simple. Inside of the parentheses, we must provide a variable to use as an iterator. Typically we just declare a new variable there, such as `int j` in this example. Then, following a colon, we give the array that we'd like to iterate over. 

{{% notice warning "Enhanced For Loops are Read Only!" %}}

When using an **Enhanced For** loop in Java to iterate over an array, the array itself cannot be changed from within the loop. If that happens, the Java program will throw an error and stop. 

So, we must make sure we don't try to edit the array from within an **Enhanced For** loop. Instead, we would use a standard **For** loop to iterate over the _indices_ of the elements in the array, as seen in the first loop in this example. Using that approach, we can edit the array from within the loop. 

{{% /notice %}}

Once inside of the loop, we can use `j` to refer to the current element in `a` that we are looking at. Notice that it is not the _index_ of that element, but the actual value of the _element_ itself. 

So, we can simply add the value of `j` to the `sum` variable. Once the loop has terminated, we can just print the `sum` variable to the terminal. 

## Two Approaches

This example shows both ways we can use a loop to iterate over the elements in an array. The first approach, using a standard **For** loop, will iterate over the indices of the array, from 0 up to the length of the array. The second approach, using an **Enhanced For** loop, iterates over the items themselves, but we cannot edit the array from within the loop. 

In general, it is recommended to always use an **Enhanced For** loop whenever we wish to iterate over an array without making changes to the array itself. However, if we plan on making changes, we should use a standard **For** loop and iterate over the indices instead. 

**Reference:** [The for Statement](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/for.html)
