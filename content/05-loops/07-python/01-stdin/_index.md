---
title: "Reading from Stdin"
pre: "1. "
weight: 10
---

<!-- {{% youtube WLOOldm9GJM %}} -->

<!--[Video Materials]({{<relref "./video">}}) -->

<!-- TODO Update Video -->

In Python, the stream object that grants access to Linux standard input is in the `sys` module and called `stdin`.  Since `sys.stdin` is a tyoe of built in stream object, it has many different methods which you can call.  The only one we will use is the `readline()` method.

`sys.stdin.readline()` causes Python to read characters from the keyboard until the &crarr; (enter key) is pressed.  At that point in makes a string, terminated with the '\n' character and returns the string to the program.  The result of calling `.readine()` on `sys.stdin` is ALWAYS a string terminated with '\n' character.  The minimum length of a `.readline()` is 1, and it will be the string `"\n"`.

## Reading standard input in practice

Consider the following program.

```python
import sys

class Demo:

    @staticmethod
    def main(args):
        
        #x <- INPUT
        x = sys.stdin.readline()
        print("the Value of x is {}".format(x))
        print("the Type of x is {}".format(type(x)))
        print("The LENGTH of x is {} characters, this accounts for the '\n' character".format(len(x)))

if __name__ == "__main__":
    Demo.main(sys.argv)
```

When `Demo.main()` is called, the standard input is read and returned as a string to be assigned to the variable `x`.  If you call `.readline()` multiple times, each call will result in Python reading the characters from the keyboard until the &crarr; is hit.  

### Conventions

#### Aliasing the Input Stream

Sometimes program will have the options for which source (keyboard, file, network, etc) the program should use for input.  To avoid littering every input with `IF` statements, there is often a "preamble" section where an alias (variable) is assigned the appropriate stream and that alias is used everywhere else in the code. 

```python 

if args[1] === "0":
    reader= sys.stdin  # use keyboard
elif args[1] == "1"
    reader = open("input.data",r)  # use a file

# the variable reader is now used everywhere input is needed
# 'reader' is an alias for the correct stream

x = reader.readline()
```

We will use this approach, so always alias `sys.stdin`.

```python
import sys

class Demo:

    @staticmethod
    def main(args):
        
        reader = sys.stdin
        
        #x <- INPUT
        x = reader.readline()
        print("the Value of x is {}".format(x))
        print("the Type of x is {}".format(type(x)))
        print("The LENGTH of x is {} characters, this accounts for the '\n' character".format(len(x)))


if __name__ == "__main__":
    Demo.main(sys.argv)
```

#### Strip the trailing new-live

Often the string method <a href="https://docs.python.org/3/library/stdtypes.html">`.rstrp('\n')`</a> is used to get rid of the trailing new-line character: `x = sys.stdin.readline().rstrip('\n')`.  

{{% youtube KOZ3Zk66NFg %}}

You should complete and experiment with Demo.py.  How does it behave if you add more inputs?  What must one do to convert inputs to integers, floats?

#### Naked Prompts (usually avoided)

You'll note that Demo.py does not have a  prompt for input.

![no prompt](/images/05-loop/naked_prompt.png)

This is called a naked prompt.  There is no indication to the user that input is expected.  This is generally considered a bad practice.  Better would be a user prompt.

![user prompt](/images/05-loop/BetterPrompt_p.png)

HOWEVER, because you are graded on exactly matching expected output, we have chosen to use "naked prompts" so you don't waste valuable time hunting for typos in the input prompts.

This means you program may appear to "hang".  When this happens, try typing in some input.

{{% notice note "My Program is Hung" %}}

With the introduction of reading from standard input and loops; it may appear that your program is "hung". When this happens:

1. First try entering a string, if text appears in the terminal, your program is not hung, it is waiting for input.
2. Try forcing a keyboard interrupt: cntrl-C on windows and cmd-. (command 'period') on mac at the time of this writing.
3. Close the terminal tab.
4. Close the Codio tab.

{{% /notice %}}


   

