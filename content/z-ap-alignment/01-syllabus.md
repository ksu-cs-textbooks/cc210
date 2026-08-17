---
title: "AP Syllabus"
pre: "1. "
weight: 10
---

## Computational Thinking Practices Guide

* **CT1** - Design Code
* **CT2** - Develop Code
* **CT3** - Analyze Code
* **CT4** - Document Code and Computing Systems
* **CT5** - Use Computers Responsibly

Reference: [AP Course and Exam Description](https://apcentral.collegeboard.org/media/pdf/ap-computer-science-a-course-and-exam-description.pdf)

## CR 1 - Resources

_Students and teachers have access to a college-level computer science textbook or resource in print or electronic format. Each student has a college-level text for individual use both inside and outside of the classroom, and the teacher has a copy of the most recent edition of a college-level computer science textbook or other appropriate materials to support instruction._

The primary teaching resource in this course is _Fundamental Computer Programming Concepts_, an eTextbook authored by K-State faculty. The textbook consists of lecture material and videos developed and presented by K-State faculty, as well as an annotated bibliography of additional readings and videos from across the internet on each topic. The textbook is used in a college-level course taught at K-State:

* CC 210 - Fundamental Computer Programming Concepts

The textbook can be found online, free of charge, at:

* Primary Link: https://textbooks.cs.ksu.edu/cc210/
* Alternate Link: https://ksu-cs-textbooks.github.io/cc210/
* Authors & Contributors: https://core.cs.ksu.edu/authors/

Because the textbook is a free, always-available website, every student has individual access to it both inside and outside of class, and the instructor has access to the same current edition used by students. Students are directed to additional online resources such as official language documentation and tutorials to supplement the textbook where needed.

## CR 2 - Develop Understanding of Content

_The course provides opportunities to deepen student understanding of the required content outlined in each unit described in the course and exam description (CED)._

The course consists of multiple modules of content. Each module generally includes three components:

* A written text portion introducing the concept in theory using a language-agnostic approach, followed by one or more multiple-choice quizzes to check for comprehension and understanding of the content.
* A tutorial portion introducing the concept using a particular programming language (Java for the AP version of this course). The tutorial may include some guided coding exercises, a fully worked example problem, and a small coding exercise.
* A project that uses the concept and reinforces previous concepts in a larger program.

Below is an outline of the modules in this course and their alignment to the units in the [AP Course and Exam Description](https://apcentral.collegeboard.org/media/pdf/ap-computer-science-a-course-and-exam-description.pdf). The CED organizes required content into four units:

* Unit 1 - Using Objects and Methods
* Unit 2 - Selection and Iteration
* Unit 3 - Class Creation
* Unit 4 - Data Collections

Some sections of this course go beyond the content required by the CED (for example, designing inheritance hierarchies, writing recursive methods, and overriding `equals()`). These sections are noted below; they are not assessed on the AP Exam but are included to give students a more complete grounding in object-oriented programming.

### Module 1 - Hello World

Students are introduced to the course and the Java programming language. Students will complete a project that confirms they are able to compile and run Java code, as well as produce text output to the terminal.

* Unit 1 - Using Objects and Methods
  * 1.1 Introduction to Algorithms, Programming, and Compilers

### Module 2 - Data Types & Math

Students learn about basic numerical data types (`int` and `double`) and how to store and retrieve values. Students also learn about the basic mathematical operators in Java and order of operations. Students learn to construct mathematical expressions to compute complex values and then use assignment statements to store them in a variable, and learn to read input values from the keyboard using the `Scanner` class.

* Unit 1 - Using Objects and Methods
  * 1.2 Variables and Data Types
  * 1.3 Expressions and Output
  * 1.4 Assignment Statements and Input
  * 1.5 Casting and Range of Variables
  * 1.6 Compound Assignment Operators

<!-- TODO Confirm Scanner-based keyboard input (Topic 1.4) is explicitly taught in this module -->

### Module 3 - Boolean Logic

Students are introduced to the `boolean` data type and learn about `true` and `false` values. Students learn the basic Boolean operators and how to construct complex Boolean expressions. Students learn how to use comparators to generate Boolean values from numerical data. Students also learn the basics of Boolean algebra and how to perform basic simplifications of Boolean expressions or determine if two Boolean expressions are equivalent.

* Unit 2 - Selection and Iteration
  * 2.2 Boolean Expressions
  * 2.5 Compound Boolean Expressions
  * 2.6 Comparing Boolean Expressions

### Module 4 - Conditional Statements

Students are introduced to the basic conditional statements in Java, including the `if` and `if-else` statements. Students learn how to develop programs with more advanced control flow structures, including best practices for nesting and/or chaining conditional statements (`else if` statements) to achieve mutual exclusion and make code easily readable and understandable.

* Unit 2 - Selection and Iteration
  * 2.1 Algorithms with Selection and Repetition
  * 2.3 `if` Statements
  * 2.4 Nested `if` Statements

### Module 5 - Loops

Students are introduced to looping constructs in Java, including the `while` and `do-while` loops. Students learn how to construct loops that will continue based on a Boolean expression. Students learn the basics of analyzing loops to determine how many times they iterate and to verify that the loop will properly terminate.

* Unit 2 - Selection and Iteration
  * 2.7 `while` Loops
  * 2.8 `for` Loops
  * 2.9 Implementing Selection and Iteration Algorithms
  * 2.11 Nested Iteration
  * 2.12 Informal Run-Time Analysis

### Module 6 - Methods

Students are introduced to methods in Java. Students learn to create their own methods, including the use of parameters and return statements. Students learn to call methods by providing arguments and storing the returned results in a variable. Students learn about the importance of creating modular code that is easy to write, understand, test, and debug. Students are also introduced to the concept of developing tests that achieve code coverage across an entire method.

* Unit 1 - Using Objects and Methods
  * 1.7 Application Program Interface (API) and Libraries
  * 1.9 Method Signatures
  * 1.10 Calling Class Methods
  * 1.11 Math Class
  * 1.14 Calling Instance Methods
* Unit 3 - Class Creation
  * 3.5 Methods: How to Write Them
  * 3.7 Class Variables and Methods (_static methods only_)

### Module 7 - Objects

Students are introduced to objects in Java. This module is mostly focused on creating/instantiating objects from existing classes and developing simple classes with a few attributes, methods, and a constructor to add more modularity to their existing programs. Students are introduced to an "Instance and Driver" programming model, similar to the "Model" and "Controller" portions of the MVC design pattern.

* Unit 1 - Using Objects and Methods
  * 1.11 Math Class
  * 1.12 Objects: Instances of Classes
  * 1.13 Object Creation and Storage (Instantiation)
* Unit 3 - Class Creation
  * 3.3 Anatomy of a Class
  * 3.4 Constructors
  * 3.5 Methods: How to Write Them (_mutator methods_)

<!-- TODO Add Documentation Comments -->

### Module 8 - Aggregate Data

Students are introduced to storing aggregate data using arrays in Java. Students learn how to create arrays, access and store data in individual elements, and iterate through arrays using a `for` loop or enhanced `for` loop. Students are also introduced to multi-dimensional arrays and methods for iterating in multiple dimensions. Students learn the accumulator pattern as a way to collect data while looping through an array.

* Unit 4 - Data Collections
  * 4.3 Array Creation and Access
  * 4.4 Array Traversals
  * 4.5 Implementing Array Algorithms
  * 4.11 2D Array Creation and Access
  * 4.12 2D Array Traversals
  * 4.13 Implementing 2D Array Algorithms

### Module 9 - Strings

Students are introduced to the `String` data type in Java. Students learn how to read input strings from the terminal and parse them into smaller parts. Students learn how to convert strings to numeric data types. Students learn about various string methods such as comparison, substring, concatenation, searching within strings, and manipulating strings. Students learn how to produce formatted string outputs.

* Unit 1 - Using Objects and Methods
  * 1.15 String Manipulation
* Unit 2 - Selection and Iteration
  * 2.6 Comparing Boolean Expressions (_`String` comparisons only_)
  * 2.10 Implementing String Algorithms

### Module 10 - Exceptions

Students learn about exceptions and errors in Java. Students are introduced to the `try-catch` statement to deal with exceptions as they occur. Students learn about checked and unchecked exceptions and which ones must be handled before compiling code.

* Unit 1 - Using Objects and Methods
  * 1.1 Introduction to Algorithms, Programming, and Compilers (_identifying logic errors, run-time errors, and exceptions as distinct types of programming errors_)
* Unit 4 - Data Collections
  * 4.6 Using Text Files (_handling `IOException` when working with files_)

Writing full `try-catch` blocks to handle exceptions goes beyond the CED, which only requires students to declare `throws IOException` when working with files. This module gives students a more complete, practical treatment of error handling.

### Module 11 - File System

Students learn about file systems and how to interact with them in Java. Students learn to open and read text from files as well as write text to file. Students learn how to use the `try` with resources statement to ensure files are properly closed even if exceptions occur. Students learn some basic operations to manipulate files in a file system using Java.

* Unit 4 - Data Collections
  * 4.6 Using Text Files

### Module 12 - Classes

Students learn to develop their own object-oriented classes. Students explore all aspects of class creation, including constructors, attributes, accessor methods, variable scope and access modifiers, and more. Students learn that any class they create is actually a new data type. Students learn how to write their own `equals()` method to compare two objects of the same type.

* Unit 1 - Using Objects and Methods
  * 1.8 Documentation with Comments (_including preconditions and postconditions_)
* Unit 3 - Class Creation
  * 3.1 Abstraction and Program Design
  * 3.3 Anatomy of a Class
  * 3.4 Constructors
  * 3.5 Methods: How to Write Them
  * 3.6 Methods: Passing and Returning References of an Object
  * 3.7 Class Variables and Methods
  * 3.8 Scope and Access
  * 3.9 `this` Keyword

Writing a custom `equals()` method goes beyond the CED, which excludes overriding `equals()` from the AP Exam.

<!-- TODO Be clearer about accessor and mutator methods -->

### Module 13 - Inheritance

Students learn about inheritance in object-oriented programming. Students create abstract superclasses and learn to inherit both attributes and methods from the superclass. Students learn how to override methods in a subclass. Students learn how to access members of the superclass using the `super` keyword. Students learn about polymorphism and how a subclass can be treated as the same type as any of its superclasses. Students learn about the overall `Object` superclass in Java.

* Unit 1 - Using Objects and Methods
  * 1.12 Objects: Instances of Classes (_class hierarchies, and the fact that every class is a subclass of `Object`_)

Designing and implementing inheritance relationships, including this module's use of the `super` keyword and method overriding, goes beyond the CED, which explicitly excludes this content from the AP Exam. This module gives students hands-on experience with a foundational object-oriented concept that the current CED only requires them to recognize conceptually.

### Module 14 - MVC

Students are introduced to the Model View Controller (MVC) design pattern. Students learn how to use that design pattern to develop programs that follow a standard design structure and are easily understandable by other programmers. Students learn how to follow the concept of "separation of concerns" to divide the presentation logic in the View from the program logic in the Model and then combine the two using a Controller.

(_this module reinforces concepts from prior modules, including Unit 3's 3.1 Abstraction and Program Design and 3.2 Impact of Program Design, but does not introduce any new required content from the CED_)

### Module 15 - Collections

Students learn about several built-in collection types in Java, such as the `List` interface (`ArrayList` and `LinkedList`), the `Map` interface (`HashMap`), and creating and using simple tuple classes to allow storing compound data in a collection (_Java does not include a tuple as a basic collection but Python does, and many students find this structure useful_). Students learn how to store and retrieve data in lists and maps, and how to iterate through each collection. Students learn how to search for data in each collection, and how to sort data in an ordered collection such as a list. Students learn to create their own `compareTo()` methods for tuples and other objects.

* Unit 4 - Data Collections
  * 4.1 Ethical and Social Issues Around Data Collection
  * 4.7 Wrapper Classes
  * 4.8 `ArrayList` Methods
  * 4.9 `ArrayList` Traversals
  * 4.10 Implementing `ArrayList` Algorithms
  * 4.14 Searching Algorithms
  * 4.15 Sorting Algorithms

The `Map` interface, `HashMap`, and tuple classes are not part of the CED and go beyond its required content.

### Module 16 - Recursion

Students learn about recursion and how it can be used in place of iteration when developing repeating control flow structures. Students learn how to use recursion to search and sort in collections.

* Unit 4 - Data Collections
  * 4.16 Recursion
  * 4.17 Recursive Searching and Sorting

Tracing and analyzing recursive code, including recursive searching and sorting algorithms, is required by the CED. Writing original recursive methods, as this module asks students to do, goes beyond the CED, which excludes writing recursive code from the AP Exam.

### AP Outline

An inverse of the outline above, organized to follow the AP course units, is given below:

* Unit 1: Using Objects and Methods - Module 1, Module 2, Module 6, Module 7, Module 9, Module 10, Module 12, Module 13
* Unit 2: Selection and Iteration - Module 3, Module 4, Module 5, Module 9
* Unit 3: Class Creation - Module 6, Module 7, Module 12
* Unit 4: Data Collections - Module 8, Module 10, Module 11, Module 15, Module 16

## CR 3 - CT Practice 1: Design Code

_The course provides opportunities for students to develop the skills related to Computational Thinking Practice 1: Design Code, as outlined in the AP Course and Exam Description (CED)._

Students will complete more than 10 programming projects of various types. Each project requires students to determine an appropriate design and develop an algorithm to solve the problem or match the given specification, often working from only a written specification rather than starter code (Skill 1.A). Several projects, such as the Module 15 Minesweeper project, also require students to determine what data or structure can be extracted from a given problem in order to represent it in code (Skill 1.B).

## CR 4 - CT Practice 2: Develop Code

_The course provides opportunities for students to develop the skills related to Computational Thinking Practice 2: Develop Code, as outlined in the AP Course and Exam Description (CED)._

Students will develop more than 10 programming projects of various types. A major focus of each project is writing code to implement an algorithm (Skill 2.A). Many projects require students to write code involving data abstractions, such as arrays, `ArrayList`s, and objects (Skill 2.B), and code involving procedural abstractions, such as user-defined methods and classes (Skill 2.C).

## CR 5 - CT Practice 3: Analyze Code

_The course provides opportunities for students to develop the skills related to Computational Thinking Practice 3: Analyze Code, as outlined in the AP Course and Exam Description (CED)._

Students will develop many projects that involve determining and producing the correct output given a set of initial inputs. Examples include determining the output produced by small sample code segments based on their execution order (Skill 3.A), by data abstractions such as arrays and objects (Skill 3.B), and by procedural abstractions such as method calls (Skill 3.C). Students are also given code segments containing intentional errors and are asked to explain why the code will not compile or work as intended, and to correct it (Skill 3.D).

<!-- TODO More Quiz Questions Here! -->

## CR 6 - CT Practice 4: Document Code and Computing Systems

_The course provides opportunities for students to develop the skills related to Computational Thinking Practice 4: Document Code and Computing Systems, as outlined in the AP Course and Exam Description (CED)._

In several modules, students are given code examples and are asked to describe, in writing, the behavior of a code segment or program and trace the steps it takes (Skill 4.A). Other examples ask students to describe the initial conditions that must be met for a code segment to work as intended or described (Skill 4.B).

<!-- TODO Add More of these -->

## CR 7 - CT Practice 5: Use Computers Responsibly

_The course provides opportunities for students to develop the skills related to Computational Thinking Practice 5: Use Computers Responsibly, as outlined in the AP Course and Exam Description (CED)._

Students will engage in several interactive discussions in class and using online tools to explain how computing impacts society, the economy, and culture (Skill 5.A). Module 15 includes a dedicated discussion of the ethical issues surrounding data collection (CED Topic 4.1). In addition, students are given the opportunity to discuss and ask questions about technology stories in the news and how technology is shaping our modern world (for example, NFTs and cryptocurrency, data breaches, AI generated content, etc.). Students will learn and discuss ways that they can stay informed and consider ways to understand the impact of programs they develop on the larger world.

<!-- TODO Need to add more here -->

## CR 8 - Lab Experiences

_This course provides students with hands-on lab experiences to practice programming through designing and implementing computer-based solutions to problems._

The CED requires a minimum of 20 hours of hands-on, structured lab experience. Students in this course will spend at least 20 hours of in-class time working on programming projects throughout the semester. A list of current projects is given below:

* Module 2 - Data Types: Students perform various math operations on inputs values that are both `int` and `double` data types and observe the outputs produced.
* Module 3 - Boolean 20 Questions: Students must answer 20 questions about an input value (such as "Is the value between -5 and 9, inclusive?") using only Boolean operators, comparators, and math operators.
* Module 4 - 4 Problems: Students use conditional constructs to build programs that answer questions such as "could these inputs make a triangle?" or "how many days are in this month?".
* Module 5 - Narcissistic Numbers: Students use loops to develop a program to determine if an input is a [narcissistic number](https://en.wikipedia.org/wiki/Narcissistic_number).
* Module 6 - Damage Calculator: Students write a program to simulate a simplified attack turn in a tabletop role-playing game (RPG) similar to _Dungeons & Dragons_.
* Module 8 - TicTacToe: Students develop a program to play TicTacToe on an arbitrarily-sized 2D game grid.
* Module 9 - Pig Latin: Students develop a program to convert English to Pig Latin following a simplified set of rules.
* Module 10 - Exceptions Calculator: Students develop a calculator program that catches and handles most common exceptions related to numeric values and input.
* Module 11 - File Manipulator: Students develop a program to read, write and manipulate files in a file system.
* Module 12 - Store: Students develop a set of object-oriented classes to represent a simple store inventory and cart system.
* Module 13 - Inheritance Calculator: Students develop a calculator for real, rational, and integer numbers that uses object-oriented inheritance to represent the various types of numbers.
* Module 14 - MVC Battleship: Students use the Model View Controller (MVC) design pattern to develop a _[Battleship](https://en.wikipedia.org/wiki/Battleship_(game))_ board game.
* Module 15 - Minesweeper: Students build a simulated _[Minesweeper](https://en.wikipedia.org/wiki/Minesweeper_(video_game))_ game using the built-in Java collections classes.
* Module 16 - Recursive Search & Sort: Students build a project to practice searching and sorting in a collection using recursive methods.

## CR 9 - Resource Requirements

_Each student has access to a college-level textbook, the AP Computer Science A labs, and a computer for a minimum of three hours a week that can create, edit, and quickly compile programs comparable in size to the AP Computer Science A labs, with internet access._

Every student and the instructor have free, individual access to the course textbook described in CR 1, both in and out of class.

Students complete every module's tutorials and projects in Codio, a cloud-based Java development environment integrated directly into the course's learning management system. Because Codio runs in any modern web browser, students can access it from school or personal computers alike, and it inherently requires and provides internet access. Codio compiles and runs student programs, which are comparable in size to the AP Computer Science A labs, in a matter of seconds. Students have access to this environment during scheduled class time as well as outside of class, exceeding the three-hour weekly minimum; the hands-on lab experiences described in CR 8 are completed in this same environment and serve the same purpose as the College Board's own AP Computer Science A labs.

<!-- TODO Confirm in-class computer lab access details (hours/week, hardware) with instructor -->

## Known Gaps

The following CED content is not yet fully covered by this course. These are noted here for future course development rather than mapped above, since coverage cannot currently be confirmed against the assignment content:

* **Topic 3.2 - Impact of Program Design**: covers system reliability through testing, and the legal/intellectual property issues that arise when reusing code (e.g., open-source licensing, obtaining permission before incorporating others' code). No current module explicitly teaches the legal/IP portion of this topic.
* **Topic 4.2 - Introduction to Using Data Sets**: covers representing data-processing algorithms with diagrams or charts before writing code. Module 8 introduces arrays and the accumulator pattern but does not include this pre-coding planning step.
* **Topic 4.1 - Ethical and Social Issues Around Data Collection**: currently addressed only briefly, as a single discussion within Module 15's Collections content. This topic would benefit from more depth.
