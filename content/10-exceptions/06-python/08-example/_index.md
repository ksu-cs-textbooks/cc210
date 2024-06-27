---
title: "A Worked Example"
pre: "8. "
weight: 80
---

<!--{{< youtube XaDEahMnjgU  >}}-->

<!--[Video Materials]({{% relref "./video" %}})-->

<!-- TODO Redo Video -->

Let's work through an entire example program together to see how we can build programs that handle exceptions quickly and easily, without allowing the program to crash when invalid input is received.

## Problem Statement

Consider the following problem statement for a driver-class program `Example.py`:

> Write a program to accept a list of numbers, one per line from the terminal. 

> The numbers can either be whole numbers or floating point numbers. The program should continue to accept input until a number equal to $0$ is input, or a blank line is received. Of course, if the input in a file ends before a $0$, that can be treated as the end of the input.

> Once $0$ is received or the input ends, the program should print the largest and smallest number provided as input (not including the $0$ to end input). Sample outputs are shown below.

> The program should catch and handle all common exceptions. When an exception is caught, the program should print the name of the exception, followed by the message included in the exception. It should then continue to accept input (if possible).

## Sample Inputs & Outputs

Here's an example of an expected input for the program:

```tex
5.0
3
8.5
7
k
2.3.6
0.0
```

Here is the correct output for that input:

```tex
ValueError: could not convert string to float: 'k'
ValueError: could not convert string to float: '2.3.6'
Maximum: 8.5
Minimum: 3.0
```

Pause a moment to think about control flow, loops and exceptions you might need to handle.

When first starting out in coding and exception handling, it is often best to first write the code **without** exception handling, test it, then add the exception stuff.  Exception handlers can hide logic errors.  


## Handle Input

First, we can write code to handle user input. The problem statement tells us to read inputs, one per line, until the user inputs 0. We also know that the user can input either whole numbers or floating point numbers. So, to make it simple, we'll just use floating point numbers for everything-- this will require us to import math for number comparisons.  Now, math.isclose() cannot handle None, so instead we'll need to pick an initial value for our loop condition variable that will allow us to enter the loop, i.e. make the loop condition `True`.

```python
x = 1.0  # math.isclose() cannot handle None, wo instead we pick an initial value for x 
while not math.isclose(x,0.0):
  string = reader.readline()
  if len(string) == 0: 
    x = 0.0
  else:
    x = float(string)
```

If there is a a blank line, the `strip()` method will return the empty string.  Our program should take the the same action as if seeing a 0.0 so we assign 0.0 to x.  You should at this point test your logic , then add exception handlers.  Here we know that if `string` cannot convert until we'll get a ValueError. 

```python
x = 1.0
while not math.isclose(x, 0.0):
    try:
        string = reader.readline().strip()
        if len(string) == 0:
            x = 0.0
        else:
            x = float(string)
            if not math.isclose(x, 0.0):  
                if x < minimum or math.isclose(minimum, 0.0):
                    minimum = x
                if x > maximum or math.isclose(maximum, 0.0):
                    maximum = x
    except ValueError as e:
        print("ValueError: {}".format(e))

```

This should handle most exceptions that will occur in this program. Of course, there are many other ways that this code could be structured as well.

## Logic

Once we have the code to handle input, we can write the code to deal with logic. Keeping track of the minimum and maximum of a set of inputs is pretty simple:

```python
maximum = 0.0
minimum = 0.0
x = 1.0
while not math.isclose(x, 0.0):
    try:
        string = reader.readline().strip()
        if len(string) == 0:
            x = 0.0
        else:
            x = float(string)
            if not math.isclose(x, 0.0):  
                if x < minimum or math.isclose(minimum, 0.0):
                    minimum = x
                if x > maximum or math.isclose(maximum, 0.0):
                    maximum = x
    except ValueError as e:
        print("ValueError: {}".format(e))

    
print("Maximum: {}".format(maximum))
print("Minimum: {}".format(minimum))
```

We can simply create variables to track the minimum and maximum values. Since our program won't accept $0$ as an input, we can use that as the default value for these variables.  Our logic does not use any functions likely to throw new errors, so no more exception handling is required.

## Testing

Finally, we may want to do some quick testing of our program. In theory, it should handle any inputs provided, including files that don't exist as command-line arguments and more. When testing, we should always see if we can find some input that breaks our program, then adjust the program as needed to prevent that problem. Of course, we should always make sure that it produces the correct answers, too. 

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

