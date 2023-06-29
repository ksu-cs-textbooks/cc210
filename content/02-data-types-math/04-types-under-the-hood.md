---
title: "Data Types in Detail"
pre: "4. "
weight: 40
---

A variable in a high level language is just a memory address.  It tells the compiler/interpreter where to start looking for the binary string of data.

### Decoding the binary

All high-level programming languages use a type system to tell the system *how* to decode the binary data it finds there.  All types have a size and a semantic which describes how many bits are in the data and how to interpret each bit. Consider the 2-byte (16-bit) binary sequence `1100 0110 1110 0100`, it can be interpreted as many values based on its type.

|TYPE           | value            |
|---|---|
|16-bit floating point|-6.891 |
|16-bit unsigned integer|50916|
|16-bit 2's complement integer|-14620|
|8-bit ASCII| Æ ä|

### Performing Operations

Operations and methods are only defined for specific types. For example, we can divide two integers, but not two characters. Likewise, integer division works differently than floating point division, which we'll cover later in this chapter.  It is up to the programmer to select the appropriate type for a variable and keep track of it.

### Implications for Object-Oriented Programming (OOP)

All objects are created from a class definition. For example, an object created from a class named `Cat` is itself a new data type. A key part of object-oriented programming is that objects modify their own data. So, understanding the type of each variable is vital to understanding program state, which allows us to verify correct behavior and troubleshoot buggy code.

## Typing Systems

### Static (i.e. Java) 

One typing system, often used by compiled languages, is the static type system.  In this scheme the programmer explicitly tells the compiler the type of each variable when the is declared or defined.  The statement `int x = 5;` tells the compiler that:

1. it should reserve a memory address for an integer variable
2. that the programmer is going to use the variable name `x` for that memory address
3. it should always interpret the bits stored in `x` as an integer
4. it should put the binary string which, when evaluated as an `int` is equal to the decimal number 5 into the reserved memory address

### Dynamic (i.e. Python)

Another typing system, often used by interpreted languages, is the dynamic type system.  In this system, the interpreter infers (guesses) the type of the variable based on the literal or variable in the definition. The statement `x = 5` tells the interpreter:

1. to infer a type based on the literal `5`
2. to reserve a memory address for the inferred type 
3. that the programmer is going to use the variable name `x` for that memory address
4. to put the binary string which, when evaluated as the inferred type is equal to the decimal number 5 into the reserved memory address

## Converting Between Types

High-level languages typically have operations or methods to convert from one data type to another.  

For example, in Java, to print a line to the terminal, we use the `System.out.println()` method. As input, this method expects to receive a value that is a `String` data type. So, many languages include methods such as the `toString()` method built into all Java classes, as well as the `str()` method provided by Python, to convert most data types into a string. When a programmer explicitly tells the computer to convert one variable Type to another, the process is called **casting**.   

Thankfully, many languages also allow some data conversions to happen automatically through a process known as *coercion*. In most modern high-level languages, when a method is supplied the wrong type of parameter, the language checks to see if there is an automatic conversion from the supplied type to the required type. If so, the language first converts the incorrect parameter to the correct type, then calls the method.  The same procedure is used for operators.  Depending on coercion for simple types is a common practice.  Depending on it for more complex types or programmer developed classes can be more difficult and result in errors.

In practice, we generally should prefer explicitly casting variables to convert their types instead of relying on coercion. Casting ensures the program does exactly what we expect it to do.
