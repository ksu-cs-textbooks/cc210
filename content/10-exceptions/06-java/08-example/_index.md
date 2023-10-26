---
title: "A Worked Example"
pre: "8. "
weight: 80
---

<!-- {{% youtube j-glHqHHWBQ %}} -->

<!-- [Video Materials]({{<relref "./video">}}) -->

<!-- TODO Update Video -->

Let's work through an entire example program together to see how we can build programs that handle exceptions quickly and easily, without allowing the program to crash when invalid input is received.

## Problem Statement


Consider the following problem statement for a driver-class program `Example.java`:

> Write a program to accept a list of numbers, one per line from the terminal. 

> The numbers can either be positive whole numbers or positive floating point numbers. The program should continue to accept input until a negative number is received. Zero is an acceptable input.

> Once a negative number is received, the program should print the largest and smallest number provided as input (not including the the negative number end input). Sample outputs are shown below.

> The program should catch and handle all common exceptions. When an exception is caught, the program should print the name of the exception. It should then continue to accept input (if possible) or exit the program (if not possible).


## Sample Inputs & Outputs

Here's an example of an expected input for the program:

```tex
5.0
3
8.5
7
k
2.3.6
-1
```

Here is the correct output for that input:

```tex
NumberFormatException
NumberFormatException
Maximum: 8.5
Minimum: 3.0
```

Pause a moment to think about control flow, loops and exceptions you might need to handle.

When first starting out in coding and exception handling, it is often best to first write the code **without** exception handling, test it, then add the exception stuff.  Exception handlers can hide logic errors.

### The code without exception handling

We'll start out with the code to "attach" a Scanner to the correct input source.

```java
import java.util.Scanner;


public class Example{
    public static void main (String[] args) {
        Scanner scanner = new Scanner(System.in);

    }
}

```

Next let's use a do-while loop to handle input until there is a negative number.  We will treat all inputs as doubles.

```java
double input;
do{
    input = Double.parseDouble(scanner.nextLine().trim());

}while(input >= 0.0);
```

If the input is negative, we do nothing.  Otherwise we keep  track of the minimum and maximum number seen.  Note, that the first number input is both the min and max number seen.  We'll handle this by observing that an acceptable entered number cannot be less than zero so initial values for the min and max can bet set to `-1.0` as a sentinel value.


```java
double max = -1.0;
double min = -1.0;
double input;
boolean first = true;

do{
    input = Double.parseDouble(scanner.nextLine().trim());
      if (input >= 0.0 ){
        if (min > input || min < 0.0){
          min = input;
        }
        if (max < input || max < 0.0){
          max = input;
        }
      }
} while (input >= 0.0);
```

Lastly we would print the min and max out.

We leave it for you to finish the "without exception handling" program and test it from the terminal.  

### Adding Exception handling

Although rare, a `Scanner` object connected to `System.in` can throw a `NoSuchElementException` when `nextLine()` is called.  This can occur when:  
*  the program has inadvertently closed `System.in` (more on this is discussed in the chapter on Files)
*  a redirected stream lacks the proper number and/or types of inputs (see below)

{{% notice note "Directing a File to Stdin" %}}

In Linux, the `<` operator can be used at the terminal to send the contents of a file in place of `stdin`.

```bash
java Example < tests/example1.txt
```

You can see this "trick" if you have `Example.java` working.  The command `java Example < tests/example1.txt` will provide the input from the file `example1.txt` that is stored in the `tests` folder to the program, just as if it was typed directly in the terminal by hand.

{{% /notice %}}

Let's catch the `NoSuchElementException`,

``` java
do{
  try{
      input = Double.parseDouble(scanner.nextLine().trim()); 
  }
  catch (NoSuchElementException e){
      System.out.println("NoSuchElementException");
      return;  //exits the program
  }

  if (input >= 0.0 ){
    if (min > input || min < 0.0){
      min = input;
    }
    if (max < input || max < 0.0){
      max = input;
    }
  }

} while (input >= 0.0);
```
Here we catch the Exception and exit the program. Remember to catch a specific Exception you must import it.

The other thing that can go awry is the parsing. Reading a String that would not parse into a Double, which will throw a `NumberFormatException`.  However, from the example inputs it is clear that we should not exit on this condition but instead keep accepting input. `continue` will reset us to the next loop.

```java
do{
  try{
      input = Double.parseDouble(scanner.nextLine().trim()); 
  }
  catch (NoSuchElementException e){
      System.out.println("NoSuchElementException");
      return;  //exits the program
  }
  catch(NumberFormatException e ){
      System.out.println("NumberFormatException");
      continue;
  }

  if (input >= 0.0 ){
    if (min > input || min < 0.0){
      min = input;
    }
    if (max < input || max < 0.0){
      max = input;
    }
  }

} while (input >= 0.0);
```

## Testing

Finally, we may want to do some quick testing of our program. In theory, it should handle any inputs provided. When testing, we should always see if we can find some input that breaks our program, then adjust the program as needed to prevent that problem. Of course, we should always make sure that it produces the correct answers, too. 

