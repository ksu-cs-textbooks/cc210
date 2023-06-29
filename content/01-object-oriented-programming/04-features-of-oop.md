---
title: "OOP Features"
pre: "4. "
weight: 40
---

In this course, we will be teaching programming from the object-oriented perspective. Both Java and Python support this programming paradigm, and it is commonly used in industry today. However, it is easier to understand some of these concepts (such as classes and objects), after first covering some of the fundamental concepts. 

Thus, the first few modules of this course will contains some pieces of starter code that we'll use without really explaining much about how they work, but rest assured that we'll cover those concepts at the correct time in the course. Likewise, many of the early programming assignments will include some frozen starter code that provides the structure, and the point of the assignment will be simply to fill in the middle portion of the program that contains the actual code. 

Before we begin programming, let's go over some basic terminology and rules for high-level programming languages.

## Syntax

First, all high programming languages have a **syntax**, which is a pattern of words and symbols that all correct instructions in the language much follow. So, when we receive a syntax error from the compiler or interpreter, we should know that one or more lines of code in our program doesn't follow the rules of the language.  In a very real sense, this is the grammar that all correct programming lines will follow.

Natural languages also have a grammar, but most natural language listeners can understand improper grammar. The question "Which room is the dog in?" which contains the dreaded dangling preposition, will almost certainly be correctly interpreted as "in which room is the dog?" by most listeners.

Programming languages are not like this – the slightest violation of a grammar rule will result in code that most likely will not run. So, as developers we must learn to be very precise and exact in our code. This is a difficult skill to learn, but we'll develop it over time with practice.

## Semantic

Second, all programming instructions have a specific meaning, known as the **semantics** of the language. When one of our programs compiles and executes but produces an incorrect result, this is due to a semantic error (sometimes known as a logic error) in our code.

Unfortunately, the compiler or interpreter isn't able to help us find any semantic errors, but we can find them through careful testing of our code. 

## Initial Vocabulary

Finally, all programming languages have various defined structures, which we can think of as the "parts of speech" in the programming language. This is similar to the concept of nouns, verbs, and adjectives in the English language. 

This is a list of some of the most common parts in a programming language:

* **keywords** - a word that has a special meaning. These words tell the program exactly what to do, and we cannot use these words as identifiers.  For example, in both Java and Python the word `class` is a keyword. We cannot use a keyword for any purpose other than the one(s) intended by the programming language.
* **literal** – text evaluated as itself, for example numbers (such as `6.626`) are meant to represent themselves. Similarly, text literals are most often enclosed in double quotation marks (such as `"wildcat"`).  Text literals are most commonly referred to as strings.
* **identifiers** - any class, method, or variable name is considered an identifier.  Each language will have both rules (syntax) about what can be identifiers and conventions (style guides) about how to construct them.
* **variable** – a programmer-defined piece of data.  Programmers name their variables with an identifier.
* **method** - a piece of code that performs an action in our program. Methods are sometimes referred to as functions or subroutines as well, but we'll use the term method. Programmers name their methods with an identifier.
* **class** – a collection of variables and the methods used to manipulate that data.  Classes lay at the heart of object-oriented programming and will be the focus of the last third of this course.
* **symbols** - any non-alphanumeric character which has special meaning.  Common ones include the math symbols (`+ - / * =`), brackets of all forms (`() [] {}`), and then some not so obvious ones (` .  ,  ;  "  !`).

{{% notice note "Subroutine, Function, and Method" %}}

Properly, a **subroutine** is a generic term for a named code fragment that does something.  Your programming language may have a subroutine named `math.sqrt(x)` that calculates the square root of `x` or one called `print (something)`  that prints what ever the value of 'something' is to the screen. The `print()` subroutine may be many lines long, but you gain access to it by calling (using) its name.

The issue is different programming languages use different words to refer to different kinds of subroutines. **Functions** in C may mean a different thing than **functions** in Fortran, Java, Python, or mathematics.

We are not going to worry about the details, and will use **method** or occasionally **function** to refer to callable subroutines.

{{% /notice %}}