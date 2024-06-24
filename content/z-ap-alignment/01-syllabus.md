---
title: "AP Syllabus"
pre: "1. "
weight: 10
---

## Big Ideas Guide

* **MOD** - Modularity
* **VAR** - Variables
* **CON** - Control
* **IOC** - Impact of Computing

## Computational Thinking Practices Guide

* **CT1** - Program Design & Algorithm Development
* **CT2** - Code Logic
* **CT3** - Code Implementation
* **CT4** - Code Testing
* **CT5** - Documentation

Reference: [AP Course and Exam Description](https://apcentral.collegeboard.org/media/pdf/ap-computer-science-a-course-and-exam-description.pdf)

## CR 1 - Resources

_Students and teachers have access to a college-level computer science textbook in print or electronic format._

The primary teaching resource in this course is _Fundamental Computer Programming Concepts_, an eTextbook authored by K-State faculty. The textbook consists of lecture material and videos developed and presented by K-State faculty, as well as an annotated bibliography of additional readings and videos from across the internet on each topic. The textbook is used in a college-level course taught at K-State:

* CC 210 - Fundamental Computer Programming Concepts

The textbook can be found online at:

* Primary Link: https://textbooks.cs.ksu.edu/cc210/
* Alternate Link: https://ksu-cs-textbooks.github.io/cc210/ 
* Authors & Contributors: https://core.cs.ksu.edu/authors/

Students will be directed to additional online resources such as official language documentation and tutorials. 

## CR 2 - Develop Understanding of Content

_The course provides opportunities to develop student understanding of the required content outlined in each of the units described in the AP Course and Exam Description (CED)_

The course consists of multiple modules of content. Each module generally includes three components:

* A written text portion introducing the concept in theory using a language-agnostic approach, followed by one or more multiple-choice quizzes to check for comprehension and understanding of the content. 
* A tutorial portion introducing the concept using a particular programming language (Java for the AP version of this course). The tutorial may include some guided coding exercises, a fully worked example problem, and a small coding exercise. 
* A project that uses the concept and reinforces previous concepts in a larger program. 

Below is an outline of the modules in this course and their alignment to the units in the [AP Course and Exam Description](https://apcentral.collegeboard.org/media/pdf/ap-computer-science-a-course-and-exam-description.pdf).

### Module 1 - Hello World

Students are introduced to the course and the Java programming language. Students will complete a project that confirms they are able to compile and run Java code, as well as produce text output to the terminal.

* Unit 1 - Primitive Types
  * 1.1 Why Programming? Why Java?

### Module 2 - Data Types & Math

Students learn about basic numerical data types (`int` and `double`) and how to store and retrieve values. Students also learn about the basic mathematical operators in Java and order of operations. Students learn to construct mathematical expressions to compute complex values and then use assignment statements to store them in a variable.

* Unit 1 - Primitive Types
  * 1.2 Variables and Data Types
  * 1.3 Expressions and Assignment Statements
  * 1.4 Compound Assignment Operators
  * 1.5 Casing and Range of Variables

### Module 3 - Boolean Logic

Students are introduced to the `boolean` data type and learn about `true` and `false` values. Students learn the basic Boolean operators and how to construct complex Boolean expressions. Students learn how to use comparators to generate Boolean values from numerical data. Students also learn the basics of Boolean algebra and how to perform basic simplifications of Boolean expressions or determine if two Boolean expressions are equivalent. 

* Unit 3 - Boolean Expressions and `if` Statements
  * 3.1 Boolean Expressions
  * 3.5 Compound Boolean Expressions
  * 3.6 Equivalent Boolean Expressions

### Module 4 - Conditional Statements

Students are introduced to the basic conditional statements in Java, including the `if` and `if-else` statements. Students learn how to develop programs with more advanced control flow structures, including best practices for nesting and/or chaining conditional statements (`else if` statements) to achieve mutual exclusion and make code easily readable and understandable. 

* Unit 3 - Boolean Expressions and `if` Statements
  * 3.2 `if` Statements and Control Flow
  * 3.3 `if-else` Statements
  * 3.4 `else if` Statements

  <!-- TODO Codify else if statements in Text -->

### Module 5 - Loops

Students are introduced to looping constructs in Java, including the `while` and `do-while` loops. Students learn how to construct loops that will continue based on a Boolean expression. Students learn the basics of analyzing loops to determine how many times they iterate and to verify that the loop will properly terminate. 

* Unit 4 - Iteration
  * 4.1 `while` Loops
  * 4.2 `for` loops
  * 4.4. Nested Iteration
  * 4.5. Informal Code Analysis

  <!-- TODO Add More Code Analysis and Termination Stuff from CC 110 -->

### Module 6 - Methods

Students are introduced to methods in Java. Students learn to create their own methods, including the use of parameters and return statements. Students learn to call methods by providing arguments and storing the returned results in a variable. Students learn about the importance of creating modular code that is easy to write, understand, test, and debug. Students are also introduced to the concept of developing tests that achieve code coverage across an entire method.

* Unit 2 - Using Objects
  * 2.3 Calling a Void Method
  * 2.4 Calling a Void Method with Parameters
  * 2.5 Calling a Non-void Method
* Unit 5 - Writing Classes
  * 5.6 Writing Methods
  * 5.7 Static Variables and Methods (_methods only_)

### Module 7 - Objects

Students are introduced to objects in Java.  This module is mostly focused on creating/instantiating objects from existing classes and developing simple classes with a few attributes, methods, and a constructor to add more modularity to their existing programs. Students are introduced to an "Instance and Driver" programming model, similar to the "Model" and "Controller" portions of the MVC design pattern.

* Unit 2 - Using Objects
  * 2.1 Objects: Instances of Classes
  * 2.2 Creating and Storing Objects (Instantiation)
  * 2.9 Using the `Math` Class
* Unit 5 - Writing Classes
  * 5.1 Anatomy of a Class
  * 5.2 Constructors
  * 5.5 Mutator Methods
  * 5.6 Writing Methods

<!-- TODO Add Documentation Comments -->

### Module 8 - Aggregate Data

Students are introduced to storing aggregate data using arrays in Java. Students learn how to create arrays, access and store data in individual elements, and iterate through arrays using a `for` loop or enhanced `for` loop. Students are also introduced to multi-dimensional arrays and methods for iterating in multiple dimensions. Students learn the accumulator pattern as a way to collect data while looping through an array.

* Unit 6 - Array
  * 6.1 Array Creation and Access
  * 6.2 Traversing Arrays
  * 6.3 Enhanced `for` Loop and Arrays
  * 6.4 Developing Algorithms using Arrays
* Unit 8 - 2D Array
  * 8.1 2D Arrays
  * 8.2 Traversing 2D Arrays

### Module 9 - Strings

Students are introduced to the `String` data type in Java. Students learn how to read input strings from the terminal and parse them into smaller parts. Students learn how to convert strings to numeric data types. Students learn about various string methods such as comparison, substring, concatenation, searching within strings, and manipulating strings. Students learn how to produce formatted string outputs.

* Unit 2 - Using Objects
  * 2.6 `String` Objects: Concatenation, Literals, and More
  * 2.7 `String` Methods
* Unit 3 - Boolean Expressions and `if` Statements
  * 3.7 Comparing Objects (_`String` objects only_)
* Unit 4 - Iteration
  * 4.3. Developing Algorithms using Strings

### Module 10 - Exceptions

Students learn about exceptions and errors in Java. Students are introduced to the `try-catch` statement to deal with exceptions as they occur. Students learn about checked and unchecked exceptions and which ones must be handled before compiling code. 

* Unit 5 - Writing Classes
  * 5.10 Ethical and Social Implications of Computing Systems (_brief discussion of risks if code does not properly handle exceptions_)

<!-- TODO Add More on Ethical/Social Implications Here -->

### Module 11 - File System

Students learn about file systems and how to interact with them in Java. Students learn to open and read text from files as well as write text to file. Students learn how to use the `try` with resources statement to ensure files are properly closed even if exceptions occur. Students learn some basic operations to manipulate files in a file system using Java.

* Unit 2 - Using Objects
  * 2.1 Objects: Instances of Classes (_using the `java.nio.file` library classes gives ample practice using objects and calling methods_)
  * 2.3 Calling a Void Method
  * 2.4 Calling a Void Method with Parameters
  * 2.5 Calling a Non-void Method
  * 2.6 `String` Objects: Concatenation, Literals, and More (_parsing strings from files_)

### Module 12 - Classes

Students learn to develop their own object-oriented classes. Students explore all aspects of class creation, including constructors, attributes, accessor methods, variable scope and access modifiers, and more. Students learn that any class they create is actually a new data type. Students learn how to write their own `equals()` method to compare two objects of the same type. 

* Unit 2 - Using Objects
  * 2.1 Objects: Instances of Classes
  * 2.2 Creating and Storing Objects (Instantiation)
  * 2.3 Calling a Void Method
  * 2.4 Calling a Void Method with Parameters
  * 2.5 Calling a Non-void Method
* Unit 3 - Boolean Expressions and `if` Statements
  * 3.7 Comparing Objects
* Unit 5 - Writing Classes
  * 5.1 Anatomy of a Class
  * 5.2 Constructors
  * 5.3 Documentation and Comments
  * 5.4 Accessor Methods
  * 5.5 Mutator Methods
  * 5.6 Writing Methods
  * 5.7 Static Variables amd Methods
  * 5.8 Scope and Access
  * 5.9 `this` Keyword

<!-- TODO Add Documentation and Comments Here -->
<!-- TODO Be clearer about accessor and mutator methods -->
<!-- TODO Be clearer about `this` keyword -->

### Module 13 - Inheritance

Students learn about inheritance in object-oriented programming. Students create abstract superclasses and learn to inherit both attributes and methods from the superclass. Students learn how to override methods in a subclass. Students learn how to access members of the superclass using the `super` keyword. Students learn about polymorphism and how a subclass can be treated as the same type as any of its superclasses. Students learn about the overall `Object` superclass in Java.

* Unit 9 - Inheritance
  * 9.1 Creating Superclasses and Subclasses 
  * 9.2 Writing Constructors for Subclasses
  * 9.3 Overriding Methods
  * 9.4 `super` Keyword
  * 9.5 Creating References using Inheritance Hierarchies
  * 9.6 Polymorphism
  * 9.7 `Object` Superclass

<!-- TODO Use superclass and subclass terminology -->

### Module 14 - MVC

Students are introduced to the Model View Controller (MVC) design pattern. Students learn how to use that design pattern to develop programs that follow a standard design structure and are easily understandable by other programmers. Students learn how to follow the concept of "separation of concerns" to divide the presentation logic in the View from the program logic in the Model and then combine the two using a Controller.

(_this module serves to reinforce concepts from prior modules but does not introduce any new content from the AP CED_)

### Module 15 - Collections

Students learn about several built-in collection types in Java, such as the `List` interface (`ArrayList` and `LinkedList`), the `Map` interface (`HashMap`), and creating and using simple tuple classes to allow storing compound data in a collection (_Java does not include a tuple as a basic collection but Python does, and many students find this structure useful_). Students learn how to store and retrieve data in lists and maps, and how to iterate through each collection. Students learn how to search for data in each collection, and how to sort data in an ordered collection such as a list. Students learn to create their own `compareTo()` methods for tuples and other objects.

* Unit 2 - Using Objects
  * 2.8 Wrapper Classes: `Integer` and `Double` (_collections store objects and not primitives_)
* Unit 7 - `ArrayList`
  * 7.1 Introduction to `ArrayList`
  * 7.2 `ArrayList` Methods
  * 7.3 Traversing ArrayLists
  * 7.4 Developing Algorithms using ArrayLists
  * 7.5 Searching
  * 7.6 Sorting
  * 7.7 Ethical Issues Around Data Collection

<!-- TODO Add more searching & sorting -->
<!-- TODO Add ethical issues around data collection -->

### Module 16 - Recursion

Students learn about recursion and how it can be used in place of iteration when developing repeating control flow structures. Students learn how to use recursion to search and sort in collections. 

* Unit 10 Recursion
  * 10.1 Recursion
  * 10.2 Recursive Searching & Sorting

<!-- TODO Port from CC 310 -->

### AP Outline

An inverse of the outline above, organized to follow the AP course units, is given below:

* Unit 1: Primitive Types - Module 1, Module 2
* Unit 2: Using Objects - Module 6, Module 7, Module 9, Module 11, Module 12
* Unit 3: Boolean Expressions and `if` Statements - Module 3, Module 4, Module 9, Module 12
* Unit 4: Iteration - Module 5, Module 9
* Unit 5: Writing Classes - Module 6, Module 7, Module 10, Module 12
* Unit 6: Array - Module 8
* Unit 7: `ArrayList` - Module 15
* Unit 8: 2D Array - Module 8
* Unit 9: Inheritance - Module 13
* Unit 10: Recursion - Module 16

## CR 3 - Develop Understanding of Big Ideas

_The course provides opportunities to develop student understanding of the big ideas, as outlined in the AP Course and Exam Description (CED)._

### Big Idea 1 - Modularity (MOD)

Students will construct several programming projects that focus on modular development. Some examples of current projects focusing on modularity:

* **Module 8 - TicTacToe Project** Students develop a TicTacToe style game on an arbitrarily-sized 2D board. Students develop several methods to fill in squares on the board, check for a valid move, check for a win condition, and check for a draw. Students use an "Instance and Driver" structure, where the instance is the TicTacToe board itself and a driver acts as a simple controller to play the game. 
* **Module 9 - Pig Latin Translator** Students develop a program to translate English text into Pig Latin following a simplified set of rules. Students write methods to break the input down into individual lines, then words, and create methods to handle items like punctuation and capitalization.
* **Module 12 - Store** Students develop an object-oriented model of a store, with classes representing an inventory, items in an inventory, a shopping cart, and more. Each class has several accessor and mutator methods, with the goal of simplifying the main controller class to a few straightforward method calls.
* **Module 13 - Inheritance Calculator** Students explore object-oriented inheritance by developing classes to represent real, rational, and integer numbers in a hierarchy, and then perform mathematical operations on those values. Each operation is modularized into its own method and can be overridden by subclasses. 

### Big Idea 2 - Variables (VAR)

Students will construct several programming projects that focus on using variables to store and retrieve data. Some examples of current projects focusing on variables:

* **Module 5 - Narcissistic Numbers** Students build several small pieces of code, culminating in a program that will determine if an input value is a [narcissistic number](https://en.wikipedia.org/wiki/Narcissistic_number). This involves storing many intermediate values such as the number of digits in the number and performing exponentiation.
* **Module 6 - Damage Calculator** Students write a program to simulate a simplified attack turn in a tabletop role-playing game (RPG) similar to _Dungeons & Dragons_. Students must deal with multiple inputs including dice rolls, conditions on each player, and the various rules for determining if an attack is successful and how much damage it causes.
* **Module 14 - MVC Battleship** Students use the Model View Controller (MVC) architecture to build a program simulating the classic _[Battleship](https://en.wikipedia.org/wiki/Battleship_(game))_ board game. Students will use 2D arrays to store and retrieve data and parse string inputs from the users.
* **Module 15 - Minesweeper** Students will build a simulated _[Minesweeper](https://en.wikipedia.org/wiki/Minesweeper_(video_game))_ game. However, students are not allowed to store the entire board as a 2D array. Instead, they must make use of Java collections such as `ArrayList` and `HashMap` to store all the data needed to represent the game, and then construct the board virtually as needed. 

### Big Idea 3 - Control (CON)

Students will construct several projects that focus on making decisions and altering control flow. Some examples of projects focusing on control flow:

* **Module 4 - 4 Conditional Problems** Students write four smaller projects that use control flow structures to answer simple questions such as whether a set of three inputs could represent the side lengths of a triangle, or how many days are in a given month.
* **Module 5 - Narcissistic Numbers** Students use many looping constructs to construct the parts needed to determine if an input value is a [narcissistic number](https://en.wikipedia.org/wiki/Narcissistic_number).
* **Module 6 - Damage Calculator** Students will use many control flow constructs to simulate a simplified attack turn in a tabletop role-playing game (RPG) similar to _Dungeons & Dragons_. This includes determining the conditions for the attack, whether it is successful, and how much damage is done using a variety of inputs. 
* **Module 11 - File Manipulator** Students use input commands and the state of files in a file system to print, concatenate, or otherwise manipulate existing files. Students much include proper control flow constructs to handle situations where inputs are invalid or files don't exist or can't be created.

### Big Ideas 4 - Impact of Computing (IOC)

Students will engage in several interactive discussions in class and using online tools to discuss the impacts of programs developed in this course. In addition, they will be given the opportunity to discuss and ask questions about technology stories in the news and how technology is shaping our modern world (for example, NFTs and cryptocurrency, data breaches, AI generated content, etc.). Students will learn and discuss ways that they can stay informed and consider ways to understand the impact of programs they develop on the larger world.

<!-- TODO Need to add more here -->

## CR 4 - CT Practice 1: Program Design & Algorithm Development

_The course provides opportunities for students to develop the skills related to Computational Thinking Practice 1: Program Design and Algorithm Development, as outlined in the AP Course and Exam Description (CED)._

Students will complete more than 10 programming projects of various types. Each project requires students to develop code from scratch to solve the problem or match the given specification. Later programs require students to develop multiple classes and methods to solve the project, and many programs involve development of novel algorithms. In several projects, students will be given either partial starter code or directed to Java libraries to find methods that can be used. (Skill 1.C)

## CR 5 - CT Practice 2: Code Logic

_The course provides opportunities for students to develop the skills related to Computational Thinking Practice 2: Code Logic, as outlined in the AP Course and Exam Description (CED)._

Students will develop many projects that involve determining and producing the correct output given a set of initial inputs. Examples include using Boolean logic operators, comparators, and math operators to answer questions about input values without any control flow (Skill 2.A) and determining the output produced by small sample code segments (Skill 2.B, 2.C).

<!-- TODO More Quiz Questions Here! -->

## CR 6 - CT Practice 3: Code Implementation

_The course provides opportunities for students to develop the skills related to Computational Thinking Practice 3: Code Implementation, as outlined in the AP Course and Exam Description (CED)._

Students will develop more than 10 programming projects of various types. A major focus of each project is implementing program code to meet a given specification (Skill 3.C). Later projects include using objects (Skill 3.A), developing new classes (Skill 3.B), and working with arrays (Skill 3.D) and 2D arrays (Skill 3.E)

## CR 7 - CT Practice 4: Code Testing

_The course provides opportunities for students to develop the skills related to Computational Thinking Practice 4: Code Testing, as outlined in the AP Course and Exam Description (CED)._

As part of the development process for many projects, students will be asked to develop their own test cases to ensure that the program is working correctly, and to identify and debug any errors that exist (Skill 4.A, 4.B).

## CR 8 - CT Practice 5: Documentation

_The course provides opportunities for students to develop the skills related to Computational Thinking Practice 5: Documentation, as outlined in the AP Course and Exam Description (CED)._

In several modules, students are given code examples and are asked to describe its output and trace the steps it takes (Skill 5.A). Other examples introduce code with known errors that the student must describe and correct (Skill 5.B)

<!-- TODO Add More of these -->

## CR 9 - Lab Experiences

_This course provides students with hands-on lab experiences to practice programming through designing and implementing computer-based solutions to problems._

Students will spend at least 20 hours of in-class time working on programming projects throughout the semester. A list of current projects is given below:

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
* Module 14 - MVC Battleship: Students use the Model View Controller (MVC) design pattern to develop a  _[Battleship](https://en.wikipedia.org/wiki/Battleship_(game))_ board game.
* Module 15 - Minesweeper: Students build a simulated _[Minesweeper](https://en.wikipedia.org/wiki/Minesweeper_(video_game))_ game using the built-in Java collections classes.
* Module 16 - Recursive Search & Sort: Students build a project to practice searching and sorting in a collection using recursive methods. 
