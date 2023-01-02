---
title: "A Worked Example"
pre: "9. "
weight: 90
---

<!-- {{% youtube NAal-yrDrCM %}} -->

<!-- [Video Materials]({{<relref "./video">}}) -->

<!-- TODO Update Video -->

Now that we've learned how to work with loops and arrays, let's see if we can solve a more challenging problem using loops and arrays.

## Problem Statement

For this example, let's build a program that matches the following problem statement:

> Write a program to calculate weighted grades for a student taking a course. The program should begin by accepting the student's name and a single positive integer as input, giving the number of assignments in the course. If the input is invalid, simply print "Invalid Input!" and terminate.   All input is from the keyboard.

> The program should accept the test scores, as ints between 0 and 100, and the test weights, in order, as floats between 0. and 1. The input pattern will be: test 1, test weight, test 2, test weight 2, ...

> If an out of range score or weight is input, the program should simply print "Invalid Input!" and terminate.  If too many test are entered, print "Invalid Input!" and terminate.

> The program should ensure that the total sum of the weights is equal to 1.0. If the weights do not add to 1.0, The program should print "Invalid Input!" and terminate.

> The program should print out the the student's final final score. For each assignment, multiply the score and the weight, and then add that value to the total score for the student. The print out should be of the form `<name> earned a ##.##` or `Trace earned a 78.86` .  Use `"{} earned a {:.2f}".format(<name>, <final_score>)` to create the string for printing.

## Class Diagram

We'll start by roughing out a Driver-Object class UML.  Since instances are about the data, lets put all the data and logic about the student and exams in a `Student` class. Next lets describe the methods which might be useful access and manipulate that data.

* The attributes would include a student's name and arrays of their exam scores and and weights.  To make arrays we will need to track the "maximum" number of test for a student and the <b>current</b> number of tests stored in the arrays.

* The methods would include
    * a constructor that accepts as parameter's the name and maximum number of tests.
    * a method to input a single tests score and weight, with a way to signal if some invalid input has happened
    * a method to check if the test weights sum to 1
    * a method to calculate the final score
    * a toString method that returns `<name> earned a ##.##`
    
Lets have the input method return True if everything with reading and storing the data goes ok, and False it any invalid data is used.

We'll run it with a driver class, which will:

* takes input for the name and number of tests
* creates a Student object
* Calls the appropriate methods the right number of times to 
    * enter the correct number of scores and weight
    * print out the final score as indicated above
* If any Student method indicates invalid input was sent, prints "Invalid Input!" and terminates the program

![Student-Driver UML](/images/08-array/Student_scores_uml_j.png)   

###  The Student Class

First, we'll need to build the skeleton of our class.  By convention, all fields come before all methods and constructors come before other methods.

```java

public class Student{

    // instance fields
    private String name;
    private int maxTests;
    private int currentTests;
    private int[] testScores;
    private double[] testWeights;

    // Constructor(s)
    public Student (String name, int tests){ }

    // Instance Methods
    
    public boolean addTest( int score, double weight) { return false;}

    private boolean sumWeights(){ return false;}

    private double calcGrade() { return 0.0;}

    public String toString() { return "";}
    
}
```

This class definition, will compile without errors. Note how each method with a return type <b>returns</b> some default value.  Each method has the correct signature and  this skeleton should pass any structure test. 

<b>Note</b>: The minus (`-`) access modifier in the UML diagram stands for private.  Right now, just substitute `private` for `public` in your method/filed declarations.  We will explain more later in this example.


#### Start with Constructor

We know the method , `Student(name: string, tests: int)` on the UML the constructor. It needs to set up all the instance attributes, of which there are four. It is common in constructors to use parameter names that match instance field names.  This necessitates the use of the key word `this` in the constructor to disambiguate the identifiers. 

```java
    public Student (String name, int tests){
        this.name = name;
        this.maxTests = tests;
        this.testScores = new int[maxTests];
        this.testWeights = new double[maxTests];
        this.currentTests = 0; // no tests have been stored
     }
```

Here we have initialized the two arrays to the correct size.

{{% notice warning "Test Each Method As You Go!" %}}

A test for this constructor might be

```java
public static void main(String[] args){
    Student test = new Student("bob", 3);
    System.out.println(test.name);
    System.out.println(test.maxTests);
    System.out.println(test.currentTests);
    System.out.println(test.testScores.length);
    System.out.println(test.testWeights.length);       
}
```

You should be able to determine the values which should print from the code.


{{% /notice %}}

#### Move to `add_test()`

First we need to check a few things when arriving in `add_test`.  We need to make sure the arrays are not at full.  This is the purpose of `currentTests`. `currentTests` starts at 0, and is incremented each time a test is added. Thus as long as `currentTests < maxTests`, there is still room in the array of anohter test.

If there is room, we need to ensure that the parameters are in range.  If we see a problem in any of these areas, return false. Assuming the parameters are in range, add them to the arrays and increment `currentTests`.

Finally, if the weights-list is now full, we need to check that is sums to `1.0`.  We have a method, `__sum_weights()` which performs this check so we just call it.


```java
    public boolean addTest( int score, double weight) { 
        if (currentTests < maxTests){
            if (score < 0 || score > 100 ||
                weight <0. || weight > 1.){
                return false;
                }
            testScores[currentTests] = score;
            testWeights[currentTests]  = weight;
            currentTests++;
            if (currentTests == maxTests){
                return sumWeights();
            } 
            return true;
        } else {
            return false;
        }
    }
```

Thus the method might get used like

```
IF (NOT <obj>.add_test(80, .25)) {
   DISPLAY(ERROR)
   EXIT
}
```
If there is a problem in processing the parameters, `add_tests()` returns FALSE.  `NOT FALSE` is TRUE so we go into the IF-body, display an error then quit.

#### `__sum_weights()` 

Here we use an accumulator pattern and an enhanced for-loop through the weights .  Recall that `float == float` is subject to representation errors.  We use a range (`0.999<sum<1.0001`)[^1] which returns TRUE if the sum  is within a ten-thousandth (1E-4) of one.

[^1]: With double precision we can probably go to 7-12 decimal places

```java
double sum = 0.;
for(double d:testWeights){
    sum += d;
}
return .9999 < sum && 1.0001> sum;
```
    
#### `__calc_grade()`

Here we use the accumulator pattern to sum up the contribution of each test (testScore[i] * testWeight[i]).  We can do this because we entered the scores ad weights in order: test_score[1] is matched with test_weights[1].

This practice is called parallel-lists or parallel-array pattern.  Each array has different type of data , but each index in the all lists the refer to the same thing.  This is a fairly common pattern in non-object oriented programming.  

```java
private double calcGrade() {
    double sum = 0.;
    for(int index = 0; index < testWeights.length; index++){
        sum += testWeights[index] * testScores[index];
    }
    return sum;
}
```


#### `toString()`

Here we use the given string `String.format("%s earned a %5.2f",<name>, <final_score>)`.  We just return it.

```java
double sum = calcGrade();
return String.format("%s earned a %5.2f",name,sum);
```

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}


## Driver Class

* takes input for the name and number of tests
* creates a Student object
* Calls the appropriate methods the right number of times to 
    * enter the correct number of scores and weight
    * print out the final score as indicated above
* If any Student method indicates invalid input was sent, prints "Invalid Input!" and terminates the program

Below is a shell we leave for you to complete.

```java

public class Driver{
    
    public static void main(String[] args){
        Scanner keybrd = 
        String name = keybrd.nextLine().trim();
        int n_test = 
        Student s = 
        for (int i = 0; i < tests; i++){
            int score = 
            double weight = 
            if (!temp.addTest(score, weight)){
                System.out.println("Invalid Input!");
                return;
            }
        }
        System.out.println(temp);

    }
}        


```

A sample run might look like

```text
~/workspace/java$ java Driver
bob 
2
100
.5
60
.5
bob earned a 81.00
```

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}
