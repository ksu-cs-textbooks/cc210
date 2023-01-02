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

## You need to test your code

Up to this point you may have been relying on the `check-it` buttons to "test" your code.  These buttons are not guaranteed to provide complete code coverage and boundary value checking.  The amount of code they "skip" will increase as we proceed through the course.

## Consider adding a `TEST` method 

You may feel free to add a `TEST` method to any class.

```tex
FUNCTION TEST(){
    ...
}
```

We will not check for the existence of `TEST` or penalize you if you have it.

### How to use `TEST`

Consider the quadratic example.  Lets say it has 3 methods:
* `main`: Take 3 inputs (a,c,b) and causes the real number roots of ax<sup>2</sup> + bx + c to be displayed.
* `root`: Calculates and displays the real number roots, or "complex roots" if the discriminant is negative. Takes three parameters (a,b,c).
* `discriminant`: Calculates and returns the discriminant. Takes three parameters (a,b,c).


### Testing Methods

#### Test `discriminant`

Start by writing a `main` that calls `TEST`, then write `discriminant`.  We are now ready to test discriminant.

```tex
1  FUNCTION discriminant(a,b,c){
2     RETURN b*b - 4*a*c
3  }
```

In order to test a method, we have to understand what the method does.  `discriminant` calculates a number so we'll need to calculate some values.

| a | b  |  c  |  discriminant  |
|---------|----------|------|---|
| 1 | 3 | 1 | 5 |
| 3 | 3 | 3 | -27 |

The number of values you need to test is based on getting complete code and special values coverage. In our case one value is enough.  the trace of any valid call is `{ 1, 2}`, 100% code coverage.

Next we set up the tests.  Tests generally have 3-parts
* set up, assign values used for testing
* call the method we are testing (called the Unit Under Test (UUT))
* display the expected and actual behavior of the UUT.

so 

```tex
FUNCTION TEST(){
  // set up
  a <- 1.
  b <- 3. 
  c <- 1.
  // call UUT
  ans <- discriminant(a, b, c)
  // display the expected and actual
  DISPLAY ("Answer should be 5")
  DISPLAY (ans)

  // alternative
  ans <- discriminant(3, 3, 3)
  DISPLAY (ans)

}
```

Running the program will run `main` which calls `TEST`.

{{% notice note "This Seems Like A LOT More Programming" %}}

It is a lot more coding.  To test a method you must really understand its function and how it fits with other methods.  Understanding how methods work and work together is a key computational thinking skill.

It is normal to write several times more lines of code testing a method than are contained in UUT.  You can shortcut this (see the alternative style of the second test); relying on your memory of that "correct answers" should be.  For most of the projects in CC-210 this shortcut is not a bad approach.  If you work on a project with a life span of more than a few days, being verbose in the TEST function can help save time.

The advantage testing each method as you code them is that the amount of code you have to search for errors is small.  An error you detect must be in the method you just coded. 

By the end of the course, projects will be 3-5 classes each with 3-5 methods. If you only do functional checks of the completed project, isolating an error to single method in this case is extremely time consuming.  

{{% /notice %}}

#### Testing `root`

Write root.

```tex
FUNCTION root(a,b,c){
    d<- discriminant(a,b,c)
    IF ( d < 0 ){
        DISPLAY("Complex Roots")
    } ELSE {
        r1 <- (-b + SQUAREROOT(d)) / (4 * a* c)
        DISPLAY(r1)
        r2 <- (-b + SQUAREROOT(d)) / (4 * a* c)
        DISPLAY(r2)
    }
}
```

We see to get complete ocde coverage we need to use an `{a,b,c}` that produces a positive discriminant and a set that produces a negative discriminant.  So first calculate answers


| a | b  |  c  |  discriminant  |
|---------|----------|------|---|
| 1 | 3 | 1 | -0.38 </br> -2.62 |
| 3 | 3 | 3 | "Complex Roots"|

Then write TEST

```tex
FUNCTION TEST(){
  // set up
  a <- 1.
  b <- 3. 
  c <- 1.
  // call UUT
  root( a, b, c)
  // display the expected and actual
  DISPLAY ("Answer should be -.38, -2.62")


  // alternative
  ans <- discriminant(3, 3, 3)

}
```
Whether to delete TEST's content after testing a method (so it only tests on method at a time), or append to it (so it is a running log of all tested methods) is up to you.  

### Testing `main`

On usually tests `main` directly.  Rewrite it and test it for known values.  Use command line/keyboard/file input as directed.

```tex
FUNCTION main(){
    a <- INPUT()
    b <- INPUT()
    c <- INPUT()
    root (a , b, c)    
    }
```

