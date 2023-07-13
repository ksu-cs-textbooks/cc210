---
title: "A Worked Example"
pre: "8. "
weight: 80
---

{{% youtube fTKunowqEpM %}}

[Video Materials]({{<relref "./video">}})

{{% notice note "Updated Code" %}}

The code in this example video contains a slightly older version of the input code that also includes the ability to read from a file, which can be ignored. We recommend using the code shown below instead. The rest of the video is still applicable to this example.

<!-- TODO Update Video -->

{{% /notice %}}

Now that we've learned some of the different looping constructs in Java, let's work through a completed example to see how we can use loops to build more advanced programs.

## Problem Statement

For this example, we'd like to build a program that matches the following problem statement:

> Write a program that will accept a series of integers from the keyboard, one per line. It will continue to accept integers from the user until the user inputs 0. If the user inputs a negative number, the program should print `"Error! Positive Integers Only"` and continue to receive input. Once the user inputs 0, the program should print the sum and average of the positive integers input by the user. 

### Flowchart

Before we start coding, let's try to draw a flowchart for this program, just to make sure we understand the control flow it will use. We know that we need to get keyboard input, convert it to an integer then take some actions based on its value. 

![Initial Flow Chart](/images/05-loop/example_1.png)

We also know we will have to repeat this an indeterminate number of times, and a **While** loop is the preferred construct to use for this. So lets add a **While** loop. While we are at it, make sure that if 0 is input for `x`, we do nothing and let the program flow back to the start of the while loop. So, our final flowchart may look like this.

![Revised Flow Chart](/images/05-loop/example_2.png)

There are a few important items to note in this flowchart:

1. We added a conditional statement inside of the loop to check if `x > 0`. If this is false, we'll print the error and loop back to the top. This is keeps us from adding 0 or values less than 0 to our sum.
1. The `x < 0` and `x > 0` paths are mutually exclusive. We should probably consider using **If-Else If-Else** statements to communicate this intentional exclusivity when we write our code.
1. The flowchart is a "complete" example that shows the overall control flow of the program, but it skips many details:
    1. How can we check if `x != 0` that first time if we don't get a value for `x` until we are in the loop?
    1. How do we calculate the average?
    1. Where does the `Scanner` code to handle input go?

Keep in mind that a flowchart is an abstraction of the code we need to write; it is just a model containing some important subset of the details.  This one is sufficient to ensure we use the right loop and if statements.

## Code the Boiler Plate

Lets start by adding the boiler plate code for setting up the class, the main() method and input. Let's store this program in `Example.java` 
```java
import java.util.Scanner;

public class Example{
  
    public static void main(String[] args){
        // Create the Scanner object to read from the terminal
        Scanner scanner = new Scanner(System.in);
          
        /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */
      
    }
  
}
```

For the rest of this example, we'll look at a smaller portion of the code. That code can be placed where the `MORE CODE GOES HERE` comment is in the working copy above. 

## Handling Input

Next, we want to build a program that can accept a series of integers from the user. Since we don't know how many we'll get, we'll probably want to use some sort of a **While** loop. So, let's add in a **While** loop and start building from there:

```java
while(){
  
}
```

Inside of that loop, we know we need to read an integer from the user, so we can add the code for that as well:

```java
while(){
  int x = Integer.parseInt(reader.nextLine());
}
```

Next, we need to determine when the loop should terminate. In this case, we can go back to the problem statement above, where we see the line:

> It will continue to accept integers from the user until the user inputs 0.

So, we might be tempted to do something like this:

```java
while(x != 0){
  int x = Integer.parseInt(reader.nextLine());
}
```

However, that code has a very important error in it. We haven't declared `x` outside of the **While** loop, so when we try to compile this code we'll get a compiler error. So, let's resolve that error:

```java
int x = 0;
while(x != 0){
  x = Integer.parseInt(reader.nextLine());
}
```

When we compile and run this fragment, we should see that it never prompts for input.  We need to initialize `x` to some value, so we quickly chose to initialize it to {{< math >}}$ 0 ${{< /math >}}. However, by doing so, we should hopefully see that it will never enter the loop, since `x != 0` will immediately be `false`. So, let's set `x = 1` instead for now:

{{% notice info "Sentinel Values" %}}

In the above loop, "zero" may be referred to as a [**sentinel value**](https://en.wikipedia.org/wiki/Sentinel_value), which is a value to watch for and alter the program's behavior when it occurs.  It is important to ensure we don't inadvertently initialize our variable to a sentinel value.

{{% /notice %}}

```java
int x = 1;
while(x != 0){
   x = Integer.parseInt(reader.nextLine());
}
```
That's a good start! As we continue to work on this program, we'll revisit the structure of this code and see that there might be a better way to do it. For now, let's press on ahead.

## Invalid Inputs

Next, we can handle the error messages for any invalid inputs. From the problem statement:

> If the user inputs a negative number, the program should print "Error! Positive Integers Only" and continue to receive input.

This case is pretty simple. We want to check if the user has entered a number less than {{< math >}}$ 0 ${{< /math >}}. If so, we should just print out an error message, but continue to receive input. The word "continue" gives us an important clue toward how we can accomplish this task. Here's one way to build this test into our program:

```java
int x = 1;
while(x != 0){
  x = Integer.parseInt(reader.nextLine());
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  //logic here
}
```

In this code, if the user enters a negative number, we simply use an **If** statement to find that error, print out the error message, and then the `continue` keyword will cause the program to loop back to the beginning and read another input. Of course, we can do this without the `continue` keyword as well, using an **If-Else** statement instead:

```java
int x = 1;
while(x != 0){
  x = Integer.parseInt(reader.nextLine());
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
  }else{
    //logic here
  }
}
```

Either approach works equally well. Some developers prefer to avoid the use of `continue` and `break` keywords because they make it more difficult to understand loops, while other developers prefer to avoid having the logic of the loop nested several layers deep in many **If-Else** statements. It is really up to developer preference and the overall style guide that is in effect. 

For this example, we'll use the code with the `continue` keyword, just to get a better understanding of how it works.

## Program Logic

Once we've handled our user inputs, we can include our program's logic. In this case, we need to calculate both the sum and average of all of the numbers entered by the user. Calculating the sum is pretty simple! We can just include a `sum` variable and add each input to that variable:

```java
int x = 1;
int sum = 0;
while(x != 0){
  x = Integer.parseInt(reader.nextLine());
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  sum += x;
}
System.out.println("Sum: " + sum);
```

To calculate the average of a set of numbers, we must remember the formula {{< math >}}$ \text{Average} = \frac{\text{Sum}}{\text{Count}} ${{< /math >}}. Since we already are tracking the sum, we can just add another variable to keep track of the count of inputs:

```java
int x = 1;
int sum = 0;
int count = 0;
while(x != 0){
  x = Integer.parseInt(reader.nextLine());
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  sum += x;
  count++;
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
```

Notice in the code above we are casting `sum` as a double when we calculate the average. Otherwise, the program will perform floored integer division, which isn't what we want in this case.

Now, let's see if this works.

{{% notice tip "Try It!" %}}

See if you can complete the program using the example code above in a file name `Example.java`. Does it work correctly? 

There is a very important logic bug in the code above. See if you can figure out what it is before continuing!

{{% /notice %}}

## Logic Bug

The code above contains a very important logic error. To find that error, let's run the program by entering the numbers `1` and `3`, followed by `0` to end the program. Here's the output we should receive:

![Logic Error Output](/images/05-loop/5.7.j.5.error.png)

Notice that the sum of `4` is correct, but the average is `1.333333` instead of `2`. Why is that?

If we look closely at our program above, we notice that the program will still increment `count` when we input `0` to stop the program. So, it believes that we've entered three numbers, when we actually only entered two. Therefore, we need to figure out some way to prevent the program from incrementing `count` when we input `0`.

There are several ways we can accomplish this. One way is to simply wrap the program logic in another **If-Then** statement, as in this example:

```java
int x = 1;
int sum = 0;
int count = 0;
while(x != 0){
  x = Integer.parseInt(reader.nextLine());
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  if(x != 0){
    sum += x;
    count++;
  }
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
```

We could also use a `break` keyword to exit the loop as soon as we realize that the user's input is `0`:

```java
int x = 1;
int sum = 0;
int count = 0;
while(x != 0){
  x = Integer.parseInt(reader.nextLine());
  if(x == 0){
    break;
  }
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  sum += x;
  count++;
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
```

Either approach works. Again, it just depends on how we'd like to style our code so that it is clear and easy to understand. 

In addition, we could rearrange the code just a bit to make the **While** loop's Boolean expression a bit clearer:

```java
int sum = 0;
int count = 0;
int x = Integer.parseInt(reader.nextLine());
while(x != 0){
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
  }else{
    sum += x;
    count++;
  }
  x = Integer.parseInt(reader.nextLine());
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
```

In this example, we read an input from the user before entering the loop. So, if the user initially inputs `0`, it skips the loop entirely, which is fine. If the input is not `0`, then it will enter the loop and check to see if it is negative. If it is, it will print the error message, but if not, it will update the sum and count accordingly. Finally, at the end of the loop, it will read another input from the user, then immediately loop back to the beginning and make sure that the user has not input `0` before starting the next iteration. Also, notice that this code does not include any `break` or `continue` keywords.

However, this code does include two lines that read input from the user. This violates one principle of writing good code, which is **DRY**, or _**Don't Repeat Yourself**_. If at all possible, we want to avoid writing two lines of code that perform the same action. So, while this code may be a bit simpler to read, it may also be a bit more difficult to update later. For example, what if a future developer needs to change this program to read floating point numbers instead of integers? If that developer does not update both lines that read input from the file, it could make the program unusable!

Finally, it may be best to simply include several **If-Else If-Else** statements to make everything clear in the code, as in this example:

```java
int x = -1;
int sum = 0;
int count = 0;
while(x!= 0){
  x = Integer.parseInt(reader.nextLine());
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
  }else if (x > 0) {
    sum += x;
    count++;
  }
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
```

This code is probably one of the best ways to accomplish this task. We use a clear string of **If-Else If-Else** statements to show that there are two possible operations inside of the **While** loop. Either the input is negative, in which case we print an error message and restart the loop; or the input is positive and accepted for our calculations.  IF the input is `0`, we allow the program to flow up to while loop condition--which will terminate the loop.

