---
title: "Types"
pre: "1. "
weight: 10
---

The Java programming language is a _statically typed_ language. This means that each and every variable we use in our programs must be _declared_ with a name and a type before we can use it. The Java compiler can then perform a step known as _type checking_, which verifies that we are using the proper data types in our program. 

The major advantage of this approach is that many errors in our computer programs can be discovered by the compiler, well before we ever try to run the program directly. It can also help us determine what the cause of the error is by stating that it is a _type error_, giving us a clue toward how it could be solved. 

One downside to this approach is that it makes our programs a bit more complex, as we must think ahead about what types of data we'll be storing in each variable, and we'll need to write our programs carefully to avoid type errors. However, it may also make our programs easier to manage later on, as we'll know exactly what type of data is stored in each variable at any given point in the program's execution.

To make dealing with types a bit easier, Java will automatically coerce data from a "narrower" data type to a "wider" data type without any additional code. For example, an integer in Java can be stored in a floating point variable.

However, the opposite case is not true. In Java, we cannot store a floating point number in an integer without explicitly converting the data type. We'll see how to do that later in this chapter. 

