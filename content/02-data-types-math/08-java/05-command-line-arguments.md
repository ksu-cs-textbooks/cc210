---
title: "Command-Line Arguments"
pre: "5. "
weight: 50
---

<!-- TODO Simplify? -->

The Linux command line consists of the command and the arguments.

![linux command line for java](/images/02-data/javacmdlne.png)

In our case the command, the word Linux translates into action is "java". Everything else is packaged up as string-values and sent to the Java Virtual Machine. The JVM takes the file name, starts the program with that file name, and passes the remaining items (arguments) to the program.

### Accessing Command-line Arguments in a Object Oriented Program

By OOP convention, the command line arguments are sent to the programs's `main` method.  Java handles this automatically.

![linux command line for java](/images/02-data/J_cl2.png)

Inside Java, the command line arguments are mapped (assigned) to a the parameter variable in the `main` method called `args`. In main `args` is an <b>array</b> of <b>Strings</b>.

![Java map of cmd line arguments](/images/02-data/J_cl3.png)

#### Accessing arguments

Arrays are ordered collections of data, you might think of it as a numbered list.  You access elements of the array using the indexing operator `[]`, the indexes start at 0[^1]. The syntax is `variableName[indexNumber]`.

[^1]: Staring at 0 saves memory and simplifies memory access. Nearly all languages start at 0. 

`args` is always an array of strings, in the order they appeared on the command line.  

#### Converting arguments

Since `args` is always an array of Strings.  Programmers convert args-elements (values in the args-array) to the appropriate type.   This is typically done using `.parse..` methods.

|Syntax | Semantics |
|---------|----------|
| `int x = Integer.parseInt(args[0])` |Take the string in args at index 0</br>Convert it to an int</br>Assign it to x  |
| `double x =Double.parseDouble(args[0])` |Take the string in args at index 0</br>Convert it to a double</br>Assign it to x  |

If you try and convert something that doe not make sense, `Double.parseDouble("act")` or `Integer.parseInt("3.1415")`, you'll get an error.

### SomeProgram.java

A proper command line for running `SomeProgram.java` would be `java SomeProgram <int> <int>`  or `java SomeProgram 2 3`.  At this juncture let's trace the execution `SomeProgram.java` as if the command line where `java SomeProgram 2 3`.

```
 1: public class SomeProgram{
 2:    public static void main(String[] args){ 
 3:        System.out.println("args[0] is a String"); 
 4:        System.out.println("args[0]'s value is '"+args[0]+"'");
 5:        int x = Integer.parseInt(args[0]);
 6:        System.out.println("x is a int");
 7:        System.out.println("x's value is "+ x);
 8:        int y = Integer.parseInt(args[1]);
 9:        int z = x + y;
10:         System.out.println(x + " + " + y + " = " + z);
11:    }
12:} 
```

1.  When we run this program we start on line 2, the beginning of the main method. 
1.  The array `{"2", "3"}` is assigned to `args`
1.  print that `args[0]` is a String, we know this because `args` is **declared** to be an array of Strings (`String[] args`, line 2)
1.  print the value of the string at index 0 of the array `args`
1.  convert the string `args[0]` to an int, assign that int-value to x
1.  print that `x` is an int, we know this because `x` is **declared** to be an int  (`int x`, line 5)
1.  print the value of `x`
1.  convert the string `args[1]` to an int, assign that int-value to y
1.  add `x` and `y`, assign that sum to the int z
1.  final print

The trace of this program is `{ 2, 3, 4, 5, 6, 7, 8, 9, 10 }`.  As you may recall from CC 110 , being able to trace the execution of code by hand is key to ensuring complete test case coverage and successful de-bugging.  More on tracing in module 4.

We encourage you to experiment with `SomeProgram.java`.  What happens if you give too few arguments, too many, the wrong types (the word "cat" for 2), etc.  
