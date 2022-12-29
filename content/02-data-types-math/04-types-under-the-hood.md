---
title: "Data Types Under the Hood"
pre: "4. "
weight: 40
---

A variable in a high level language is just a memory address.  It tells the compiler/interpreter where to start looking for the binary string of data.

### Decoding the binary

All high-level programming languages use a type system to tell the system *how* to decode the binary data it finds there.  All types have a size and a semantic, how many bits to grab and how to interpret each bit. Consider the 2-byte (16-bit) binary sequence `1100 0110 1110 0100`, it can be interpreted as many values based on its type.

|TYPE           | value            |
|---|---|
|16-bit floating point|-6.891 |
|16-bit unsigned integer|50916|
|16-bit 2's complement integer|-14620|
|8-bit ASCII| Æ ä|

### Performing Operations

Operations and methods are only defined for specific types: you can divide two integers, but not two characters;  integer division works differently than floating point division (more on this later in this chapter).  It is up to the programmer to select the appropriate type for a variable and keep track of it.

### Implications for Object-Oriented Programming (OOP)

All objects are created from a class definition.  An object made from the class definition, `class Cat ...` would be a variable of type Cat. A key part of OOP is that objects modify their own data. So, understanding what types your variables are is vital to understanding program state, which allows you to verify correct behavior and troubleshoot buggy code.

## Typing Systems

### Explicit Static (i.e. Java) 

One typing system, often used by compiled languages, is the explicit static type system.  In this scheme the programmer explicitly tells the compiler the type of each variable when the is declared or defined.  The statement `uint16 x = 5;` tells the compiler that:

1. it should reserve a memory address for a 16-bit variable (the size of unint16)
2. that the programmer is going to use the alias 'x' for that memory address
3. it should always interpret the 16-bits of 'x' as an unsigned integer
4. it should put the binary string which, when evaluated as a `uint16` is equal to the decimal number 5 into the reserved memory address

### Implicit Dynamic (i.e. Python)
Another typing system, often used by interpreted languages, is the implicit dynamic system.  In this system, the interpreter infers (guesses) the type of the variable based on the literal or variable in the definition. The statement ```x = 5``` tells the interpreter:

1. to infer a type based on the literal "5"
2. to reserve a memory address for the inferred type 
3. that the programmer is going to use the alias 'x' for that memory address
4. to put the binary string which, when evaluated as the inferred type is equal to the decimal number 5 into the reserved memory address


## Converting Between Types
High-level languages typically have operations or methods to convert from one data type to another.  

For example, in Java, to print a line to the terminal (the ```System.out``` object), one uses its ```println()``` method.  This method takes as a parameter a literal or variable of type String.  

If you have integer, and you want to print it to the terminal, you can use the Integer class's ```tostring()``` method which takes as a parameter an int and provides (returns) the text equivalent.

``` java
         //  Java    
1        int x = 5;
2        String xString = Integer.toString(x); 
3        System.out.println(xString);
```

Here on line 1 we declare x to be variable of type int (an integer), and assign it the initial value of 5.  
Line 2 declares `xString` to be a variable of type String, and assigns it the String value of evaluating the method `Integer.toString(x)`.  This will be "5".
Line 3 prints out `xString`.

Similarly Python's built in `print()` method also takes a parameter of type String.
``` python
         #  Python    
1        x = 5
2        x_String = str(x)
3        print(xString)
```
Where types are implicitly determined and where built the in functions `str()` and `print()` serve the same purpose as `toString()` and `println()` in Java.  

When a programmer explicitly tells the computer to convert one variable Type to another, the process is called *casting*.   

However, both languages will accept their version of the following

```
     x <- 5
     DISPLAY (x)
```

through a process call *coercion*. 

In most modern high-level languages, when a method is supplied the wrong type of parameter the language checks to see if there is an automatic conversion from the supplied type to the required type. If so the language first converts the offending parameter, then calls the method.  The same procedure is used for operators.  Depending of coercion for simple types is a common practice.  Depending on it for more complex types or programmer developed classes can be perilous.

In practice, prefer casting over coercion.  Casting ensures the program does exactly what you want.

### Pseudo Code for Variable Assignment

The above code is an example of pseudo code. It is not an actual programming language, but rather an outlining language with an informal syntax. The focus is on what to do, not how to do it. A programmer might first write the pseudo code for a stretch of code, ensure it makes sense, then code it up in the proper implementation language.  Together with flowcharting, pseudo code is one of the modeling techniques you might use to "mock up" your program during the code phase of the software development cycle.  The two tools are complementary, with some concepts more clearly expressed as flowcharts and others as pseudo code.

Generically
<p style="text-align:center"><em>identifier</em> &larr; <em>expression</em></p>
is the syntax for variable assignment.

Where 

* identifier is the programmer selected name of the variable
* expression is the "ultimate value" of the right hand side
  * y <- 7     # 7 is evaluated to be the number seven
  * x <- y + 3 # first y gets evaluated to 7, then 3 is evaluated to 3, the addition is evaluated to be the number ten

Note: Pseudo code typically ignore type.  The consumer of the pseudo code is expected to figure out the language (implementation) details.