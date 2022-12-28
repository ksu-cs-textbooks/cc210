---
title: "Features of OOP Languages"
pre: "4. "
weight: 40
---

We have chosen to approach the computational core from the object-oriented perspective.  Java and Python both support it.  However, it is easier to understand objects (and classes, the name for the code that implements them) after going over a few more fundamental concepts.  Thus, in the first few modules you will be asked to copy some code verbatim, with little explanation.  Alternatively, you may be asked to only write code between certain comment bars, where we have provided the "header" and "footer" code necessary to make the program.

Before we begin programming, let's go over some basic terminology and rules for high-level programming languages.

## Syntax

First all high programming languages have a syntax, a pattern of words and symbols that correct instructions follow.  When you receive a syntax error, it means the structure of one or more of your instructions does not follow the language's rules.  In a very real sense, this is the grammar that all correct programming lines will follow.

Natural languages also have a grammar, but most natural language listeners can understand improper grammar.  The question "Which room is the dog in", containing the dreaded dangling preposition, will almost certainly be correctly interpreted as "In which room is the dog".

Programming languages are not like this – the slightest violation of a grammar rule will result in code that most likely will not run.

## Semantic

Second, all programming instructions have a meaning, called a semantic.  When your program runs but does not do what you thought it would do, this is a semantic error.  Often a semantic error, a bug, occurs when the coder imperfectly understands the effect of the instruction.

## Initial Vocabulary

Finally, all programming languages have "parts of speech", by which the languages identify what kind of thing a word (number) is.  Common "parts of speech" include:
* **keywords** - a word that has a special meaning. These words tell the program exactly what to do, and we cannot use these words as identifiers.  For example, in both Java and Python the word "class" is a keyword; you cannot use a keyword for any purpose other than the one(s) intended by the programming language.
* **literal** – text evaluated as itself, for example numbers (i.e. 6.626) are meant to represent themselves. Similarly, text literals are most often enclosed in double quotation marks ("wildcat").  Text literals are most commonly referred to as strings.
* **identifiers** - any class, method, or variable name is considered an identifier.  Each language will have both rules (syntax) about what can be identifiers and conventions (style guides) about how to construct them.
* **variable** – a programmer-defined piece of data.  Programmers name their variables with an identifier.
* **method** - a piece of code that performs an action in our program. Methods are sometimes referred to as functions or subroutines as well, but we'll use the term method.  Programmers name their methods with an identifier.
* **class** – a collection of variables and the methods used to manipulate that data.  Classes lay at the heart of object-oriented programming and will be the focus of the last third of this course.
* **symbols** - any non-alphanumeric symbol which has special meaning.  Common ones include the math symbols (+ - / * =), brackets of all forms (() [] {}) and the some not so obvious ones ( .  ,  ;  "  !).

{{% notice note "Subroutine, Function, and Method" %}}

Properly, a **subroutine** is a generic term for a named code fragment that does something.  Your programming language may have a subroutine named `math.sqrt(x)` that calculates the square root of 'x' or one called `print (something)`  that prints what ever the value of 'something' is to the screen. The `print()` subroutine may be many lines long, but you gain access to it by calling (using) its name.

The issue is different programming languages use different words to refer to different kinds of subroutines. **Functions** in C may mean a different thing than **functions** in Fortran, Java, Python or mathematics.

We are not going to worry about the details, and will use **method** or occasionally **function** for callable subroutines.

{{% /notice %}}