---
title: "A Worked Example"
pre: "8. "
weight: 80
---

<!-- {{% youtube NAal-yrDrCM %}} -->

<!-- [Video Materials]({{<relref "./video">}}) -->

<!-- TODO Update Video -->

Now that we've learned how to work with loops and arrays, let's see if we can solve a more challenging problem using loops and arrays.

## Problem Statement

For this example, let's build a program that matches the following problem statement:

> Write a program to calculate weighted grades for a student taking a course. The program should begin by accepting the student's name and a single positive integer as keyboard input, giving the number of assignments in the course. If the input is invalid, simply print "Invalid Input!" and terminate.   All input is from the keyboard.

> The program should accept the test scores, as ints between 0 and 100, and the test weights, in order, as floats between 0. and 1. The input pattern will be: test 1, test weight, test 2, test weight 2, ...

> If an out of range score or weight is input, the program should simply print "Invalid Input!" and terminate.  If too many tests are entered, print "Invalid Input!" and terminate.

> The program should ensure that the total sum of the weights is equal to 1.0. If the weights do not add to 1.0, The program should print "Invalid Input!" and terminate.

> The program should print out the the student's final score. For each assignment, multiply the score and the weight, and then add that value to the total score for the student. The print out should be of the form `<name> earned a ##.##` or `Trace earned a 78.86` .  Use `String.format("%s earned a %5.2f",<name>, <final_score>)` to create the string for printing.

## Class Diagram

We'll start by roughing out a Driver and Object UML class diagram.  Since instances are about the data, lets put all the data and logic about the student and exams in a `Student` class. Next lets describe the methods which might be useful access and manipulate that data.

* The attributes would include a student's name and arrays of their exam scores and and weights.  To make arrays we will need to track the "maximum" number of test for a student and the <b>current</b> number of tests stored in the arrays.

* The methods would include
    * a constructor that accepts as parameter's the name and maximum number of tests.
    * a method to input a single tests score and weight, with a way to signal if some invalid input has happened
    * a method to check if the test weights sum to 1
    * a method to calculate the final score
    * a `toString` method that returns `<name> earned a ##.##`
    
Let's have the input method return `true` if everything with reading and storing the data goes ok, and `false` if any invalid data is used.

We'll actually run this program with a `Driver` class, which will perform the following actions:

* takes input for the name and number of tests
* creates a Student object
* calls the appropriate methods the right number of times to:
    * enter the correct number of scores and weight
    * print out the final score as indicated above
* If any `Student` method indicates invalid input was sent, prints "Invalid Input!" and terminates the program

![Student-Driver UML](/images/08-array/student_uml.png)   

###  The Student Class

First, we'll need to build the skeleton of our class.  By convention, all fields come before all methods and constructors come before other methods.

```java
public class Student{

    // Instance fields
    public String name;
    public int numTests;
    public int maxTests;
    public int[] testScores;
    public double[] testWeights;

    // Constructor(s)
    public Student (String name, int maxTests){

    }

    // Instance Methods
    public boolean addTest(int score, double weight) {
        return false;
    }

    public boolean sumWeights(){ 
        return false;
    }

    public double calcGrade() { 
        return 0.0;
    }

    public String toString() {
        return "";
    }
    
}
```

This class definition, will compile without errors. Note how each method with a return type <b>returns</b> some default value.  Each method has the correct signature and this skeleton should pass any structure test. 

#### Start with Constructor

We know the method `Student(name: string, tests: int)` on the UML is the constructor. It needs to set up all the instance attributes, of which there are five. It is common in constructors to use parameter names that match instance field names.  This necessitates the use of the key word `this` in the constructor to disambiguate the identifiers. 

```java
    public Student (String name, int maxTests){
        this.name = name;
        this.numTests = 0;
        this.maxTests = maxTests;
        this.testScores = new int[maxTests];
        this.testWeights = new double[maxTests];
    }
```

Here we have initialized the two arrays to the correct size.

{{% notice warning "Test Each Method As You Go!" %}}

A test for this constructor in the `Driver` class might be

```java
public static void main(String[] args){
    Student test = new Student("Willie", 3);
    System.out.println(test.name);
    System.out.println(test.maxTests);
    System.out.println(test.numTests);
    System.out.println(test.testScores.length);
    System.out.println(test.testWeights.length);       
}
```

You should be able to determine the values which should print from the code.

{{% /notice %}}

#### AddTest Method

First we need to check a few things when arriving in the `addTest` method.  First, we need to make sure the arrays are not at full.  This is the purpose of the `numTests` attribute. The `numTests` attribute starts at 0, and is incremented each time a test is added. Thus as long as `numTests < maxTests`, there is still room in the array of another test.

If there is room, we need to ensure that the parameters are in range.  If we see a problem in any of these areas, return false. Assuming the parameters are in range, add them to the arrays and increment `numTests`.

Finally, if the list of weights is now full, we need to check that it sums to `1.0`.  We have a method, `sumWeights()` which performs this check, so we just call it.

```java
    public boolean addTest(int score, double weight) {
        // check that we can add another test
        if (numTests < maxTests) {
            // check if score and weight are valid
            if (score < 0 || score > 100 || weight < 0.0 || weight > 1.0) {
                // return false if an error occurs
                // the Driver class will print the error
                return false;
            }
            // add the score and weight to the arrays
            testScores[numTests] = score;
            testWeights[numTests] = weight;
            numTests++;
            // check if arrays are full
            if (numTests == maxTests) {
                // if so, return an error if the sum is invalid
                return sumWeights();
            }
            // everything is good, so return true
            return true;
        } else {
            // cannot add a test, so return false
            return false;
        }
    }
```

In our `Driver` class, we might call this method in this way:

```java
Student student = new Student("Willie", 3);
if (!student.addTest(80, 0.25)){
    System.out.println("Invalid Input!");
    return;
}
```

If there is a problem in processing the parameters, the `addTest()` method should return `false`.  So, if the method returns `true` no error will be printed, but if it returns `false` then we will enter the if-statement and print an error instead.

#### SumWeights Method

This method is a great example of the **accumulator pattern** when working with arrays. In the accumulator pattern we typically use an **enhanced for** loop (a **for each** loop) to iterate through each element in the array/. Inside of the loop, we compute some value across all of those array elements, such as the sum, maximum, or average. 

Finally, recall that `double` data types are subject to some minor representation error, so when we test to see if the value is exactly `1.0` we should really check if it is within a very small range of values between `0.99999999` and `1.000000001` or similar.

```java
    public boolean sumWeights(){
        double sum = 0.0;
        for(double d : testWeights){
            sum += d;
        }
        // check if sum is very close to 1.0
        return 0.99999999 < sum && sum < 1.000000001;
    }

```
    
#### CalcGrade Method

Here we use the accumulator pattern again to sum up the contribution of each test (`testScores[i]` * `testWeights[i]`).  We can do this because we entered the scores and weights in order; so `testScores[0]` is matched with `testWeights[1]`. However, since we are using two different arrays, we cannot use an **enhanced for** loop, and must instead us a standard **for** loop, as we'll see in the code. 

This practice is called the **parallel array** pattern. Each array has different type of data, but each matching index in every array is related in some way.  This is a fairly common pattern in non-object-oriented programming. Later in this class, we'll see how to use our own classes to better store this data in an object-oriented way.

```java
    public double calcGrade() {
        double sum = 0.0;
        for (int i = 0; i < numTests; i++) {
            // multiply the score by the weight and add to total
            sum += testScores[i] * testWeights[i];
        }
        return sum;
    }

```

#### ToString Method

Here we use the given string format `String.format("%s earned a %5.2f",<name>, <final_score>)` to create our output. So, we just compute the final grade and return that string:

```java
    public String toString(){
        double sum = calcGrade();
        return String.format("%s earned a %5.2f", name, sum);
    }

```

At this point, our `Student` class should be complete. Feel free to stop a minute and test it by writing your own code in the `Driver` class before moving on.

## Driver Class

The `Driver` class should perform the following steps:

* take input for the name and number of tests
* create a `Student` object
* call the appropriate methods the right number of times to:
    * enter the correct number of scores and weight
    * print out the final score as indicated above
* If any `Student` method indicates invalid input was sent, print "Invalid Input!" and terminate the program

Since the `Driver` class only has a `main` method, we can start with this skeleton:

```java
public class Driver{

    public static void main(String[] args) {

    }
}
```

From there, we need to add the code to create a `Scanner` object to read input from the terminal. This involves importing the `java.util.Scanner` library, and then instantiating a `Scanner` inside of the `main` method to read from `System.in`:

```java
import java.util.Scanner;

public class Driver{

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

    }
}
```

Next, we can start by reading the name of the student and the number of tests from the terminal, and then instantiating our new `Student` object using that data:


```java
import java.util.Scanner;

public class Driver{

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter the student's name: ");
        String name = scanner.nextLine();
        System.out.print("Enter the total number of tests: ");
        int maxTests = Integer.parseInt(scanner.nextLine());
        Student s = new Student(name, maxTests);

    }
}
```

Now that we have created our student, we can read the input for each score and weight and slowly populate that `Student` object using that information. If any of those methods returns `false` we know that we've encountered an error and have to stop the program.

```java
import java.util.Scanner;

public class Driver{

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter the student's name: ");
        String name = scanner.nextLine();
        System.out.print("Enter the total number of tests: ");
        int maxTests = Integer.parseInt(scanner.nextLine());
        Student s = new Student(name, maxTests);
        for (int i = 0; i < maxTests; i++) {
            System.out.print("Enter score " + (i+1) + ": ");
            int score = Integer.parseInt(scanner.nextLine());
            System.out.print("Enter weight " + (i+1) + ": ");
            double weight = Double.parseDouble(scanner.nextLine());
            if (!s.addTest(score, weight)) {
                System.out.println("Invalid Input!");
                return;
            }
        }

    }
}

```

Finally, if we've entered all of the scores, we can just call the `toString` method of the `Student` class to print the final score earned by that student:

```java
import java.util.Scanner;

public class Driver{

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter the student's name: ");
        String name = scanner.nextLine();
        System.out.print("Enter the total number of tests: ");
        int maxTests = Integer.parseInt(scanner.nextLine());
        Student s = new Student(name, maxTests);
        for (int i = 0; i < maxTests; i++) {
            System.out.println("Enter score " + (i+1) + ": ");
            int score = Integer.parseInt(scanner.nextLine());
            System.out.println("Enter weight " + (i+1) + ": ");
            double weight = double.parseDouble(scanner.nextLine());
            if (!s.addTest(score, weight)) {
                System.out.println("Invalid Input!");
                return;
            }
        }
        System.out.println(s.toString());
    }
}

```

A sample execution of this program might look like this:

![Student Test Execution](/images/08-array/student_test.png)

