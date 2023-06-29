---
title: "The Software Development Lifecycle"
pre: "3. "
weight: 30
---

Another big idea in computer programming is the **software development lifecycle**. There are many different ways to approach developing a large computer program, but most of them can be divided into a few clear steps, as shown in this diagram.

![Five Step Software Development Cycle](/images/01-oop/1.1.1_SDC.png)

## Requirements

The first step is the **requirements analysis** phase. In this phase, a software developer works to clearly describe and understand the problem to solve and the features that the solution should have. Throughout this course, the problem statement or programming project description will form the requirements for the program to be written.

## Design

Next comes the **design** phase.  In this phase, we describe the solution in terms of the actual structure of the code. In Object-oriented programming, this generally consist of designing the classes and the interactions between them which meet the requirements.

A class is a collection of data and the methods (procedures) by which data is accessed and manipulated.  Classes are generally organized around things (the shopping cart from any online store is a classic example) or functions (communication with your computer’s network card is probably handled by a class). Similar to the requirements, the design of most of the projects in this course will be provided, but it is important to pay attention to those designs since later courses may leave the design up to the developer.

## Code

Following the design phase is the **development**, or coding, phase. In this phase, actual code is written to match the requirements and design from the previous phases. 

**This course primarily focuses on this phase of the software development lifecycle.** In this course, we'll cover how to write code in classes and methods to perform various operations on data. We'll also learn how to store and manipulate data in variables and data structures. 

### Testing During Development

Testing while coding is an important part of the coding process. Good programmers constantly test small parts of their code, both by running the code and by continually thinking about the code, any time they complete a task. When a program fails to run correctly, we say that it contains a "bug" and the process of finding and fixing those bugs is known as "debugging."

There are many advantages to testing while coding:

1. This allows the developer to develop their own test cases and have a better understanding of what the code is supposed to do and where any problems may be.
2. Any bugs introduced or revealed by the most recent addition of code become much easer to find.

We recommend a "code a little, test a little" approach in this class. This helps us narrow down which parts of the code are working properly and which ones contain bugs to be removed. If we write too much code without testing any of it, it can be very difficult to isolate and fix the bugs. 

## Test

When the development phase is complete, we move on to the formal **testing** phase of development. In this phase, the software is formally tested to ensure that is matches the specifications and design, usually by specially trained test engineers who can report any bugs that are found back to the developers. 

In this class, the **autograder** that we use serves as a formal test process. It isn't perfect and won't catch every bug, but it does a good job of helping you determine if your program meets the specifications for the project. 

## Deploy

Finally, there is the **deployment** phase. This is where the code is packaged and released to the users. In this course, this is analogous to turning in our project and marking it complete. At this point, it is very difficult to fix any bugs without making a new release of the software. 