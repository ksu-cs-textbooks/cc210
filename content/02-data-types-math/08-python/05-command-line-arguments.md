---
title: "Command-Line Arguments"
pre: "5. "
weight: 50
---

<!-- TODO Simplify? -->

The Linux command line consists of the command and the arguments.

![linux command line for python](/images/02-data/P_cmdlnarg_1.png)

In our case the command, the word Linux translates into action, is "python3". Everything else is packaged up as string-values and sent to the Python3 interpreter.

## Python Interpreter and the Command-line Arguments

The Python3 interpreter does different things based on what it receives from Linux as arguments.   If it receives no arguments it starts the Python3 Read-Evaluate-PrintLine (REPL). This is an interactive session of Python3 which can be exited with the command `quit()`.

![Python3 interpreter](/images/02-data/P_interpret.png)

`python3 -h`  brings up all the various options for using the command `python3`.[^1]

[^1]: `-?` are often referred to as flags, as in the 'dash v' (`-v`) flag will print out the version number.

![linux command line options for python3](/images/02-data/python3_cmdlnarg_2.png)

Notice towards the bottom "file  : program read from script file".  This is the way you will typically use the `python3` command in CC 210.

### Accessing Command-line Arguments in a Object Oriented Program

![linux command line for python](/images/02-data/P_cmdlnarg_2.png)

Inside the Python3 interpreter, the command line arguments are mapped (assigned) to a special variable in the `sys` module called `sys.argv`[^2]. `sys.argv` is a <b>list</b> of <b>strings</b>.

[^2]: this stands for argument vector and comes from the earliest high level programming languages

``` text
 1  import sys
 2  class SomeProgram:   
 3     @staticmethod
 4     def main(args):
 5          #  Your code Below
 6          #  Your code above
 7  if __name__ == "__main__":
 8      SomeProgram.main(sys.argv)
```
In the starter code, line 1 tells the Python interpreter we want access to the `sys` module of methods and variables.  Line 8 sends `sys.argv` to the main method as an argument.

Inside of main, the parameter(variable) named `args` is mapped to the values of `sys.argv`.   In effect, inside of the main method, `args` becomes a alias for `sys.argv`.

{{% notice info "Python OOP Convention" %}}

In many languages, `argv` is essentially read-only, it cannot be altered. This allows multiple files of a complex program to access to the command-line arguments with the assurance that they have not been altered by some other code.  Unfortunately, Python does not really support the idea of constant (unchangeable) user defined data.  So BY CONVENTION, no class method should ever assign to `sys.argv` or its aliases:

<table>
        <tr><td> x &larr; args[0]</td><td> OK, `args` can appear on the Right Hand side of an assignment</td></tr>
        <tr><td> ars[0] &larr; "new string"</td><td> BAD, `args` <b>should never</b> appear on the Left Hand side of an assignment</td></tr>
       
</table>


Always pass in `sys.argv` as a parameter.  Never directly access `sys.argv` from inside a class definition (body).

{{% /notice %}}

#### Accessing arguments

`args[0]` is <b>always</b> the name of the file being run.  Additional command line arguments are space (tab) separated.  `args` is always a list of strings, in the order they appeared on the command line.  

You can add the line `print (args)` to main to see the list of elements (the values) in the list `args`.  As a reminder, you can access any element of a list by 
```
list_name [ index_number ]

```

#### Converting arguments

`args` is always a list of strings.  Programmers convert args-elements (values in the args-list) to the appropriate type. This is typically done using `int() or float()`, see the <a href="https://docs.python.org/3/library/functions.html"> Python Documentation</a>.

### SomeProgram.py

A proper command line for running `SomeProgram.py` would be `python3 SomeProgram.py <int> <int>`  or `python3 SomeProgram.py 2 3`.  At this juncture let's trace the execution `SomeProgram.py` as if the command line where `python3 SomeProgram.py 2 3`.

```
 1: import sys
 2: 
 3: class SomeProgram:   
 4: 
 5:     @staticmethod
 6:     def main(args):
 7:         #  Your code Below
 8:         print("args[1] = {} is type {}".format(args[1],type(args[1])))
 9:         x = int(args[1])
10:         print("x = {} is type {}".format(x,type(x)))
11:         y = int(args[2])
12:         z = x + y
13:         print("z is {}".format(z))
14:         #  Your code above
15: 
16: # Main Guard      
17: if __name__ == "__main__":
18:     SomeProgram.main(sys.argv)
19:
```

1. We start with line 1, importing the `sys` module.  {1}
2. The next line to execute is line 17, the Main Guard {1,17}
   * A properly written class definition (class body) will contain no executable lines when read
3. Because we are "running" SomeProgram.py from the terminal, the Main Guard is true and we goto the function call for SomeProgram.main() {1,17,18}
4. We jump to the function definition `{1, 17, 18,   6}``
   * at this point args[0] is sys.argv[0] and equals "SomeProgram.py"
   * at this point args[1] is sys.argv[1] and equals "2"
   * at this point args[2] is sys.argv[2] and equals "3"
5. We call print at line 8 `{1, 17, 18,   6, 8}`
   * args[1] = 2 is type class-str
6. On line 9, we call int on args[1], which returns the integer value 2 and we assign 2 to x `{1, 17, 18,   6, 8, 9 }`
   * x now equals 2
7. We call print() at line 10 `{1, 17, 18,   6, 8, 9, 10 }`
   * x = 2 is type class-int
8. On line 11, we call int on args[2], which returns the integer value 2 and we assign 2 to x `{1, 17, 18,   6, 8, 9, 10, 11 }`
   * y now equals 3
9. We now add the values of x and y (so ... 5) and assign that value to z `{1, 17, 18,   6, 8, 9, 10, 11, 12 }`
   * z equals 5
10. We hit the print() call at line 13 `{1, 17, 18,   6, 8, 9, 10, 11, 12, 13 }` 
    * z is 5
11. We hit the end of the function and jump back to were we came from (line 18)`{1, 17, 18,   6, 8, 9, 10, 11, 12, 13, 14     (18) }`
12. We are done with line 18 so we go to 19, the end of the program. `{1, 17, 18,   6, 8, 9, 10, 11, 12, 13, 14     (18), 19 }`

The trace of this program would typically be shortened to `{...  17, 18, call  6, 8, 9, 10, 11, 12, 13, 14, return  19 }`.  As you may recall from CC 110 , being able to trace the execution of code by hand is key to ensuring complete test case coverage and successful de-bugging.  More on tracing in module 4.

We encourage you to experiment with `SomeProgram.py`.  What happens if you give too few arguments, too many, the wrong types (the word "cat" for 2), etc.  







