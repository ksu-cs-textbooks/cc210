---
title: "Command-Line Arguments"
pre: "5. "
weight: 50
---

<!-- TODO Simplify? -->

The Linux command line consists of the command and the arguments.

![linux command line for java](/images/02-data/javacmdlne.png)

In this example, Linux will see the first part of the command, which is `java`, and that will tell it what program to execute. Everything else is packaged up as string-values and sent to the Java Virtual Machine. The JVM takes the name of the program, `SomeProgram`, from the command, and then starts the program with that file name, passing the remaining items (arguments) to the program.

### Accessing Command-line Arguments in a Object Oriented Program

By convention, the command line arguments are sent to the program's `main` method.  Java handles this automatically.

![linux command line for java](/images/02-data/J_cl2.png)

Inside Java, the command line arguments are mapped (assigned) to the parameter variable in the `main` method called `args`. In main `args` is an <b>array</b> of <b>Strings</b>.

![Java map of cmd line arguments](/images/02-data/J_cl3.png)

#### Accessing arguments

Arrays are ordered collections of data - we might think of it as a numbered list.  We access elements of the array using the indexing operator `[]`, the indexes start at 0[^1]. The syntax is `variableName[indexNumber]`.

[^1]: Staring at 0 saves memory and simplifies memory access. Nearly all languages start at 0. 

The parameter `args` is always an array of strings, in the order they appeared on the command line.  

#### Converting arguments

Since `args` is always an array of Strings, programmers must convert those arguments (values in the `args` array) to the appropriate type. For numbers, this is typically done using various `parse` methods that are provided as part of the Java language.

|Syntax | Semantics |
|---------|----------|
| `int x = Integer.parseInt(args[0])` | Take the string in args at index 0</br>Convert it to an int</br>Assign it to x  |
| `double x =Double.parseDouble(args[0])` |Take the string in args at index 0</br>Convert it to a double</br>Assign it to x  |

If we try and convert something that does not make sense, `Double.parseDouble("act")` or `Integer.parseInt("3.1415")`, we'll get an error when we run our program. Later in this class we'll learn about how to detect and handle those errors, but for now they will simply crash our program.

### Example

Consider the code below, which can be stored in a file named `SomeProgram.java` if we want to execute it.

```java {lineno=table}
public class SomeProgram{
    public static void main(String[] args){ 
        System.out.println("args[0] is a String"); 
        System.out.println("args[0]'s value is \""+ args[0] + "\"");
        int x = Integer.parseInt(args[0]);
        System.out.println("x is a int");
        System.out.println("x's value is " + x);
        int y = Integer.parseInt(args[1]);
        int z = x + y;
        System.out.println(x + " + " + y + " = " + z);
    }
}
```


A proper command line for running `SomeProgram.java` would be `java SomeProgram <int> <int>`, since it requires to command-line arguments that will be converted to integers. An example would be `java SomeProgram 2 3` which will store `"2"` as `args[0]` and `"3"` as `args[1]`.  At this point, let's trace the execution `SomeProgram.java` if we execute it using the command `java SomeProgram 2 3`.

1.  When we run this program we start on line 2, the beginning of the main method. 
1.  The array `{"2", "3"}` is assigned to `args`
1.  This line prints that `args[0]` is a String. We know this because `args` is **declared** to be an array of Strings (`String[] args`, line 2)
1.  This line prints the value of the string at index 0 of the array `args`
1.  This will convert the string `args[0]` to an `int`, assign that integer value to x
1.  This will print that `x` is an `int`. We know this because `x` is **declared** to be an int  (`int x`, line 5)
1.  Next we'll print the value of `x`
1.  Now we convert the string `args[1]` to an `int`, assign that integer value to y
1.  Add `x` and `y`, assign that sum to the int `z`
1.  Print the result of the computation.


Feel free to experiment with `SomeProgram.java` to explore more ways to use command-line arguments in code.  What happens if we give too few arguments? Or too many? What about the wrong types?