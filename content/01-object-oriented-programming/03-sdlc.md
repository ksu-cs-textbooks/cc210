---
title: "The Software Development Lifecycle"
pre: "3. "
weight: 30
---

![Five Step Software Development Cycle](/images/01-oop/1.1.1_SDC.png)

## Requirements Analysis

Software Development is more than just programming.  It is a disciplined process of converting requirement into finished product.  It consists of five phases, the first of which is requirements analysis.  In requirements analysis you try and describe the problem you are trying to solve and the features you want the solution to have. Throughout CC 210, the exercise or project statement serves as the requirements analysis phase.

## Design

Next comes the design phase.  In design we describe the solution.  In Object-oriented programming this generally consist of designing the classes and the interactions between them which meet the requirements.

A class is a collection of data and the methods (procedures) by which data is accessed and manipulated.  Classes are generally organized around things (the shopping cart from any online store is a classic example) or functions (communication with your computer’s WIFI card is probably handled by a class).  The design of many of CC 210 exercises and projects will be provided to you.

## Coding (Development)

Following design is the coding phase, where programs are written to build the design.  This is the emphasis area of CC 210.  Students will code classes, or fragments of classes--with their associated variables and methods; and test these methods as you write them.

Low level testing is organic to the coding process.  Imagine you were writing the Goldilocks Porridge Temperature Tester, which takes as input a temperature and outputs "too hot", "too cold" or "just right".  Better programmers would test their code with a value from each range to make certain the output is correct.  When a program fails a test, it is said to have a "bug" and the process of finding and fixing bugs is called debugging.

The advantages of testing as you code are

1. that **you** develop the test cases and therefore have a good understanding of what the code is supposed to accomplish and where the problems might be.
2. Any bugs must have been introduced or revealed by the last bit of code you wrote.  

So, if you follow a "code-a-little-test-a-little" approach, you can quickly narrow down the parts of the code which contain the error. If you write too much code before testing any of it, it can be hard to isolate the bugs.

## Formal Test

When the coders believe they have a properly working product, the development enters the formal test phase.  Generally, a separate set of developers put the software through its paces and report any bugs they find.  Some of these bugs will be fixed and retested, while others may be left in the code to be addressed at a future date.  When you run the autograder you have effectively entered the formal test phase.

## Deployment

Finally, there is the deployment phase.  This were people and systems start using your code. The analogous activity for CC 210 certifying your module is complete.