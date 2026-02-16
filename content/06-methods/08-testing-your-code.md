---
title: "Testing Your Code"
pre: "8. "
weight: 80
---

{{% notice warning "Read Carefully!" %}}

Many students fail to read this section carefully and understand what it means. From this point forward, the grading tools that you have access to before you submit a project **ARE NOT** the same grading tools used to fully grade your project. This means that the grader in the project may tell you that you have completed the project, but when you submit it you could receive a significantly lower grade.

**WHY?**

One important skill for a programmer to learn is properly testing your code. So, from this point forward, we're not going to give you all of the test cases in the project. Instead, you'll have to carefully read the project description, identify what test cases should be used, and then create and run those test cases yourself. 

Consider this - for most of the history of programming, students had to learn without **ANY** access to automated testing and grading tools, and in fact they may not have been able to run their program many times at all due to the high cost of computing time on early systems. So, students and professional programmers alike had to learn how to properly test and verify their programs either by hand or by careful use of test cases. 

To help you develop this skill, we are "taking off the training wheels" and giving you more room to fail. As always, if you find that you are stuck or unsure where to begin, don't be afraid to contact your instructors for assistance. 

{{% /notice %}}

## Developers are also Testers

Up to this point in the class we've had various automated grading tools available to test our code and make sure it works correctly. However, it is important to understand that these buttons are just running code written by other developers (in this case, the instructors of the course), and these tests can have the same limitations as any other program. For example, it is often impossible to guarantee that these tests will accurately test all possible inputs or reach 100% code coverage. Likewise, depending on how the solution is written, the edge cases and boundary conditions may be different than the ones that were originally used for testing. 

At this point, we have learned enough programming syntax and terminology to start running our programs manually and developing our own tests. So, from this point forward, many of the projects will not give us access to the full automated grading process before we submit it. In effect, it is now our job to properly test our program using various inputs, both the ones provided and ones that we develop ourselves, in order to be sure that it is working properly. 

After we submit the project, the full autograder will still be used to grade our work. The autograder will confirm that your project matches the specification within a reasonable limit. However, we won't be able to go back in and make any changes after we submit the project. So, we'll have to be extra careful and make sure our programs are fully tested before we submit them.

## Write a `test` Method

One thing that we can do is add an explicit `test` method to any class in our program. Our `test` method may contain any code needed to test our program. We are always allowed to add additional methods to any class as needed - we won't be penalized for that in grading.

For example, we could add a `test` method to the previous example to test some of the functions:

```java
import java.lang.Math;

public class Dry{

    public static void main(String[] args){
        quadratic(1, 0, -4);
        quadratic(2, 7, 3);
    }

    public static void quadratic(int a, int b, int c){
        d = discriminant(a, b, c);
        rootOne = (-b - Math.sqrt(d)) / (2 * a);
        rootTwo = (-b + Math.sqrt(d)) / (2 * a);
        System.out.println(rootOne);
        System.out.println(rootTwo);
    }

    public static int discriminant(int a, int b, int c){
        return b * b - 4 * a * c;
    }

    public static void test(){
        int answer1 = discriminant(1, 3, 1);
        System.out.println("Answer 1 was " + answer1 + " and should be 5");
        int answer2 = discriminant(3, 3, 3);
        System.out.println("Answer 2 was " + answer2 + " and should be 27");
    }
}
```

In the method, we see that we are calling the `discriminant` method with a few different values. The expected answer values we see in the print statements can be manually calculated and verified using a calculator. It is important that we calculate these manually instead of relying on our program to calculate them - if we did, how would we ever know if it was actually incorrect?

## Using a `test` Method

Once we've written a `test` method, we have to change our program so that it calls the method. The simplest way to do this is to just add that function call at the very top of the `main()` method:

```java
    public static void main(String[] args){
        test();
        quadratic(1, 0, -4);
        quadratic(2, 7, 3);
    }
```

Since the `test` method may produce output or change the functionality of our program, it is always important to remember to **REMOVE** the `test` method from our `main` method before we submit the program. 

{{% notice note "This Seems Like A LOT More Code" %}}

It _is_ a lot more coding.  To test a method, we must really understand its function and how it fits with other methods.  Understanding how methods work and work together is a key computational thinking skill.

It is very common practice in industry to write several times more lines of code in test methods than the actual method that is being tested. This can be reduced a bit by hard-coding some of the correct answers and just checking a few boundary values, as shown above. However, for more complex projects, we may end up writing many complex tests. This is usually covered in an advanced programming class, so we won't spend much time on it here.

The advantage testing each method as you write them is that the amount of code you have to search for errors is small.  An error you detect must be in the method you just coded. 

By the end of the course, projects will be 3-5 classes each with 3-5 methods. If you only do functional checks of the completed project, isolating an error to single method in this case is extremely time consuming.  

{{% /notice %}}
