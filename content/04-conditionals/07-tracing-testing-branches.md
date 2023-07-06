---
title: "Tracing & Testing Branches"
pre: "7. "
weight: 70
---

With the introduction of conditional statements, our programs are starting to become more complex. Each time we run the program, it will produce different output based on the input, and some inputs may cause the program to execute different pieces of code entirely. So, we need to develop some more sophisticated testing strategies to help us debug our programs.

Every program should be thoroughly tested. By creating a large number of different test inputs, with each one testing a different part of the program, we can ensure that every line of code is executed at least once when all of our test inputs are used. This is referred to as test coverage.  

### Complete Coverage

Consider the following simple piece of code:

```java {linenos=table}
Scanner scanner = new Scanner(System.in);
// read an integer from input
int a = scanner.nextInt();
if (a % 2 == 0){
  System.out.println(a + " is odd");
} else {
  System.out.println(a + " is even");
}
```

To test this program, we have to provide as single value as input. If the value `2` is entered as input on line 3, then the program will execute the true branch of the if statement on line 5, but it will not execute the false branch on line 7. So, that input only executes some of the lines in the program.

However, if we also test the program with the input `1`, we'll see that it now executes line 7 that was skipped in the previous test. 

So, to fully test this program, we should use both `1` and `2` as inputs. This set of inputs will achieve **complete coverage** of the program.

However, achieving complete coverage by providing enough test inputs is not enough to say our program is correct. For that, we need to analyze the outputs that are provided by each test.

### Code Trace

Let's briefly trace through the program and see what output is produced when we provide the value `2` as input. 

On line 4, we see an if statement that checks to see if the value of `a % 2` is equal to 0. Since `a` is currently storing the value `2`, we can calculate that `2 % 2` is indeed equal to 0, so we should go to the true branch and execute the code on line 5. 

However, if we look at what this line of code does, it prints `"2 is odd"` as output. That is clearly incorrect! So, our program has a logic error in it somewhere.

As it turns out, we accidentally reversed the true and false branches of the if statement. So, to correct our program, let's switch them:

```java {linenos=table}
Scanner scanner = new Scanner(System.in);
// read an integer from input
int a = scanner.nextInt();
if (a % 2 == 0){
  System.out.println(a + " is even");
} else {
  System.out.println(a + " is odd");
}
```

Now when we provide the input `2` we should get the correct output. We can also do the same exercise for the input `1` to verify that it is also correct.

At this point we've achieved complete coverage and also proven that each of those inputs produces the correct output. However, there is still one more set of values we may want to consider

## Edge Cases

Unfortunately, just achieving complete code coverage is not enough to guarantee that we have tested all values that should be tested in our program.

In our code, we see that the if statement has the expression `a % 2 == 0`. This creates a boundary where some values will go into the true branch and other values will go into the false branch, and they all seem to revolve around the value 2 in the expression. So, we should choose our input values carefully to check the values on either side of the boundary value 2, just to be sure that it is correct.

So, we may want to add the value `3` to the set of values tested in our program, just to be sure that values greater than 2 also work correctly. If we look at our corrected code, we can see that it indeed will produce the correct output, since `3 % 2` is not equal to 0. 

{{% notice note "Boundary Values" %}}

Sometimes it is infeasible to use all boundary values.  Consider the expression `a > b` where `a` and `b` are integers. There are an infinite number of combinations of `a` and `b` to test, and testing all of these conditions is not realistic. So, instead we should make sure we test at least once where `a < b` is true and once where `a > b` is true, as well as a situation where `a == b` is true. These three tests are important in order to make sure that the boundary created by `a > b` is properly tested.

However, when one side of a comparison is a constant number, such as the `1` in `a / b > 1`, it is generally considered good practice to check the values at and near the boundary, such as `0`, `1`, and `2` in this example.

{{% /notice %}}

## Perfect Testing Is Impossible

Except for the most trivial programs, it is impossible to exhaustively test a program for correctness. However, using boundary testing and coverage testing as a guide, we will be able to develop fairly robust test sets for programs in this course.

In practice, exhaustive comprehensive testing is not even attempted in most situations. There is a special type of programming, called _high-assurance_ or _safety-critical_ programming that makes use of specialized languages, structures and techniques to logically prove certain properties are always true.  The symbolic math and logic background required for this types of programming lies beyond the scope of this course.
