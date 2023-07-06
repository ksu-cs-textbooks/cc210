---
title: "A Worked Example"
pre: "8. "
weight: 80
---

{{% youtube pTqSqh3gHos %}}

[Video Materials]({{<relref "./video">}})

We've covered quite a bit of new material so far in this chapter. Let's work through a complete example from start to finish, just to see how we can put all of those pieces together to make a very powerful program.

## Problem Statement

First, let's start with a problem statement. Here's an interesting problem that we can try to solve:

> Write a program that receives a positive integer as input from the user that represents a year, and prints whether that year is a leap year or not. If the year is a leap year, it should print output similar to `2000 is a Leap Year`. If not, it should print output similar to `2001 is not a Leap Year`. 

While this sounds like a simple problem, there are actually several rules we'll have to handle. According to the United States Naval Observatory, the Gregorian calendar (the calendar in use throughout much of the world) calculates whether a year is a leap year based on the following rule:

> Every year that is exactly divisible by four is a leap year, except for years that are exactly divisible by 100, but these centurial years are leap years if they are exactly divisible by 400. For example, the years 1700, 1800, and 1900 are not leap years, but the year 2000 is. - [Source](https://en.wikipedia.org/wiki/Leap_year#cite_note-5)

So, we'll be writing a program that can handle all of those rules to determine if a year is a leap year or not. 

## Getting Started

To begin building this program, we need to first build the basic skeleton of a program. For this example, store your code in a file called `Example.java`

{{% notice tip "Codio Tutorial" %}}

If you are following along with this course in Codio, this example will be a graded exercise in that tutorial. So, you may wish to make sure Codio is open and follow along with this example from there. 

{{% /notice %}}

First, we'll need to include a _class declaration_ and a _main method declaration_ in the file. Our code should be similar to this:

```java
public class Example{
  
  public static void main(String[] args){
    
  }
  
}
```


## Breaking Down the Problem Statement

Before we start writing more code, let's break down the problem statement a bit and see how we can use it to help us identify parts of the program we need to write. 

Here's our problem statement again:

> Write a program that accepts a positive integer from the command line, that represents a year as a command line argument, and prints whether that year is a leap year or not. If the year is a leap year, it should print output similar to `2000 is a Leap Year`. If not, it should print output similar to `2001 is not a Leap Year`. 

Looking at this problem statement, we see that we need at least one variable to store the year that is provided as input from the user. Similarly, we need at least one conditional construct, which will allow us to print whether the given year is a leap year or not. Here's the problem statement again, with those parts highlighted:

> Write a program that accepts a positive integer (**variable**) from the command line, that represents a year, and prints whether that year is a leap year or not (**conditional construct**). If the year is a leap year (**true branch**), it should print output similar to `2000 is a Leap Year`. If not (**false branch**), it should print output similar to `2001 is not a Leap Year`. 

Similarly, we can look at the second part of the problem statement and break it down as well:

> Every year that is exactly divisible by four is a leap year, except for years that are exactly divisible by 100, but these centurial years are leap years if they are exactly divisible by 400. For example, the years 1700, 1800, and 1900 are not leap years, but the year 2000 is. - [Source](https://en.wikipedia.org/wiki/Leap_year#cite_note-5)

Looking at this, we see that there are actually three conditional constructs we need to build. Let's mark them in the statement:

> Every year that is exactly divisible by four (**conditional construct 1**) is a leap year, except for years that are exactly divisible by 100 (**conditional construct 2**), but these centurial years are leap years if they are exactly divisible by 400 (**conditional construct 3**). For example, the years 1700, 1800, and 1900 are not leap years, but the year 2000 is. - [Source](https://en.wikipedia.org/wiki/Leap_year#cite_note-5)

Of course, we'll have to be careful to make sure that each branch of these three conditional statements produces the correct output. Below, we'll see how we can construct code for this problem. 

## Reading Input

Generally, one of the first things our program should do is read and process the input. So, we'll add the few lines we need to create a `Scanner` object and read an input from the user:

```java
import java.util.Scanner;

public class Example{
  
    public static void main(String[] args){
        Scanner scanner = new Scanner(System.in);
        int year = scanner.nextInt();

        // MORE CODE GOES HERE  
    }
}
```

We've used code similar to this in several of our projects at this point, so it should be familiar to us, even if we haven't written it before. We'll explain more about the structure of this code later in this course.

Once we have that code in place, we are ready to begin working on the actual logic of our program. The code examples below will just include the logic portion of the program, which can be placed where the `MORE CODE GOES HERE` line is in the structure above. 

## Verifying Input

Now that we've read the input, we can start writing the logic of our program. However, the problem statement has one very important part in it that we'll need to handle as well:

> Write a program that accepts a **positive integer** that represents a year...

So, we'll need to make sure the user has input a positive integer into our program. We can do that using a simple **if-else** statement:

```java
if(year <= 0){
    System.out.println("Error");
}else{
  
}
```

In this case, we might be tempted to use an **if** statement instead. However, we need to make sure our program only calculates a result if the input is positive. If it is negative, we should just print an error. Since that means our program needs two distinct branches, we should use an **if-else** statement here. 

## Calculating Output

Once we've read our input, we need to calculate our output. Let's handle the three rules one at a time.

### Divisible by {{< math >}}$ 4 ${{< /math >}}

For the first rule, we must check to see if the year is divisible by {{< math >}}$ 4 ${{< /math >}}. We can use the modulo operator to do this. Remember that the modulo operator performs a division and returns the remainder. So, if the remainder is {{< math >}}$ 0 ${{< /math >}}, then we know that the number is evenly divisible by the divisor.

In code, we could do the following:

```java
if(year <= 0){
    System.out.println("Error");
}else{
    if(year % 4 == 0){
        //divisible by 4
    }else{
        //not divisible by 4
        System.out.println(year + " is not a Leap Year");
    }
}
```

In each of these **if-else** statements, let's place a quick comment in the code to keep track of what we know within each branch. 

### Not Divisible by {{< math >}}$ 100 ${{< /math >}}

Next, we need to handle the rule that any year divisible by {{< math >}}$ 100 ${{< /math >}} is not a leap year, even if it is divisible by {{< math >}}$ 4 ${{< /math >}}. Of course, we can easily determine mathematically that all years divisible by {{< math >}}$ 100 ${{< /math >}} are also divisible by {{< math >}}$ 4 ${{< /math >}}, so we don't have to worry about the other case in this instance. So, we can add another **if-else** to our program:

```java
if(year <= 0){
    System.out.println("Error");
}else{
    if(year % 4 == 0){
        //divisible by 4
        if(year % 100 == 0){
            //divisible by 4 and 100
            System.out.println(year + " is not a Leap Year");
        }else{
            //divisible by 4 but not 100
            System.out.println(year + " is a Leap Year");
        }
    }else{
        //not divisible by 4
        System.out.println(year + " is not a Leap Year");
    }
}
```

In this case, we chose to next our **if-else** statement inside of the previous statement. So, if the year is divisible by {{< math >}}$ 4 ${{< /math >}} and also divisible by {{< math >}}$ 100 ${{< /math >}}, we print `Not a Leap Year`. If it is divisible by {{< math >}}$ 4 ${{< /math >}} and not divisible by {{< math >}}$ 100 ${{< /math >}}, which is the `false` branch of the innermost **if-else**, we know that it must be a leap year, so we can print `Leap Year`.

### Unless Divisible by {{< math >}}$ 400 ${{< /math >}}

There's one more rule we must add, which is the rule that a year divisible by {{< math >}}$ 400 ${{< /math >}} must be a leap year, even though it is also divisible by {{< math >}}$ 100 ${{< /math >}}. So, we must add one additional **if-else** statement. But where?

If we think back through the rules, we know that this rule is only in effect when the year is both divisible by {{< math >}}$ 4 ${{< /math >}} and {{< math >}}$ 100 ${{< /math >}}. So, we'll need to add one more statement in the `true` branch of the innermost **if-else**:

```java

if(year <= 0){
    System.out.println("Error");
}else{
    if(year % 4 == 0){
        //divisible by 4
        if(year % 100 == 0){
            //divisible by 4 and 100
            if(year % 400 == 0){
                //divisible by 4 and 100 and 400
                System.out.println(year + " is a Leap Year");
            }else{
                //divisible by 4 and 100 but not 400
                System.out.println(year + " is not a Leap Year");
            }
        }else{
            //divisible by 4 but not 100
            System.out.println(year + " is a Leap Year");
        }
    }else{
        //not divisible by 4
        System.out.println(year + " is not a Leap Year");
    }
}
```

Now we've created a program that should be able to tell us if a year is a leap year or not. 

## Other Solutions

Of course, there are many other ways this program could have been structured that would produce the same output. For example, instead of using nested **if-else** statements, we could rearrange them a bit to make them inline **if-else if-else** statements, as in this example below:

```java

if(year <= 0){
    System.out.println("Error");
}else if(year % 400 == 0){
    //divisible by 400
    System.out.println(year + " is a Leap Year");
}else if(year % 100 == 0){
    //divisible by 100 but not 400
    System.out.println(year + " is not a Leap Year");
}else if(year % 4 == 0){
    //divisible by 4 but not 100
    System.out.println(year + " is a Leap Year");
}else{
    //not divisible by 4
    System.out.println(year + " is not a Leap Year");
}
```

In fact, with a bit of thinking, we could reduce most of this program to a single Boolean logic expression, as in this example

```java

if(year <= 0){
    System.out.println("Error");
}else if(((year % 4 == 0) && (year % 100 != 0)) || (year % 400 == 0)){
    System.out.println(year + " is a Leap Year");
}else{
    System.out.println(year + " is not a Leap Year");
}
```

Any of these solutions is just as correct as the one we built above. It really only depends on which solution makes the most sense to us and is the easiest for us to write and debug. 