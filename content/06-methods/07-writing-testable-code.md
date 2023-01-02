---
title: "Writing Testable Code"
pre: "7. "
weight: 70
---

Another big idea related to writing methods in our code relates to testing. Specifically, how can we write methods that are easily testable?

## Unit Testing

We won't go deep into the details in this course, but most programming languages support _unit testing_, which is the use of automated testing tools to make sure each piece of code works as intended. They are very important for two big reasons:

1. A properly written set of tests will help confirm that the code works as intended in the first place
2. Tests that previously passed but fail after an update to our code may highlight an unintended side effect of the changes we made

In fact, many of the automated grading tools in this course make extensive use of unit testing to confirm that our code is working properly, both within this tutorial textbook and in the standalone projects. Now that we are writing code that contains methods, unit tests will become an even bigger part of the grading process in this course.

## Writing Testable methods

There are entire textbooks written about the theory of writing code that can be easily tested, and not everyone agrees exactly what the best model is. However, there are a few things that we can keep in mind as we write methods to make them easily testable:

1. **Each method should only perform one action:** a method should only do one thing. For example, if a program needs to read data from a file and then write that data to another file, those are two different actions and could be considered two separate methods.
1. **Avoid non-deterministic effects:** where possible, avoid a method that returns different values for the same inputs. This could include choosing a random value, or using the system time or other uncontrollable input in the method. These methods are difficult to test due to their random nature.  If your method needs a random number, have that number passed in as a parameter.

In the examples later in this course, we'll see explicitly how to follow some of these guidelines when writing our own code. For now, they are just handy things for us to keep in mind. 