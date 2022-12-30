---
title: "A Worked Example"
pre: "8. "
weight: 80
---

{{% youtube YuN4EovAWy8 %}}

[Video Materials]({{<relref "./video">}})

<!-- TODO Update Video -->

We've covered quite a bit of new material so far in this chapter. Let's work through a complete example from start to finish, just to see how we can put all of those pieces together to make a very powerful program.

## Problem Statement

First, let's start with a problem statement. Here's an interesting problem that we can try to solve:

> Write an object oriented program that accepts a command line argument that is a positive integer representing a year, and prints whether that year is a leap year or not. If the year is a leap year, it should print output similar to `2000 is a Leap Year`. If not, it should print output similar to `2001 is not a Leap Year`. 

While this sounds like a simple problem, there are actually several rules we'll have to handle. According to the United States Naval Observatory, the Gregorian calendar (the calendar in use throughout much of the world) calculates whether a year is a leap year based on the following rule:

> Every year that is exactly divisible by four is a leap year, except for years that are exactly divisible by 100, but these centurial years are leap years if they are exactly divisible by 400. For example, the years 1700, 1800, and 1900 are not leap years, but the year 2000 is. - [Source](https://en.wikipedia.org/wiki/Leap_year#cite_note-5)

So, we'll be writing a program that can handle all of those rules to determine if a year is a leap year or not. 

## Class Set-up and Handling Input

First, we know that our program needs to handle command line input, so we'll need to add the _import statements_ at the top of the file:

```python
# Load required modules
import sys
```

Then, we'll need to create the skeleton, or boiler plate, code associated with an object oriented program in Example.py.  

```python
# Load required modules
import sys

class Example:
    @staticmethod 
    def main(args):
        year = int(args[1])
        
        # -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- 
    
    
        # -=-=-=-=- YOUR CODE ENDS HERE -=-=-=-=- 
    
# Main Guard
if __name__ == "__main__":
    Example.main(sys.argv)
```


### The Main Guard

#### Namespace

Namespace management is one of the complex aspects of translating to machine-code the interpreter handles for you.  You do not need to know how this works, but this brief explanation is included for completeness.

All compilers and interpreters have a concept of "namespace".  Namespace is a set of <b>unique</b> identifiers used to refer to memory locations.  These locations may contain data or instructions. The critical thing is that <b>at a particular place in a program</b> the interpreter knows <b>exactly</b> the memory location to which each identifier refers. 

This can be a problem as good variable names are hard to come by.  The identifier `name` may be used dozens of times for different things in a large program.  To make these names unique, interpreters often prepend extra information in the namespace version of the identifier name.  `year` above might be `Example.Example.main.year` in the interpreter's official namespace: `year` in the file Example.py, in the class Example, in the method.main.


#### `__name__`

The built in attribute (variable) `__name__` is part of the the Python namespace schema.  The program which is executed (run) gets the special name: `__main__`^[files or modules which are imported get different `__name__`s].  So if we were to run Example.py with the command `python3 Example.py 1984`, the variable `year` is probably tracked in the namespace as `__main__.Example.main.year.`  Without regard to how many import statements or files a finished program might use, the stuff in the start-up file is always `__main__ ...`.


#### `if __name__ == "__main__" `

So now we can see how the Main Guard works.  If and only if Example.py is executed from the command line, its `__name__` will be `"__main__"`.  And if it is run form the command line, we run the body or `Example.main(sys,argv)`.


## Breaking Down the Problem Statement

Before we start writing more code, let's break down the problem statement a bit and see how we can use it to help us identify parts of the program we need to write. 

Here's our problem statement again:

> Write an object oriented program that accepts a positive integer from the command line which represents a year, and prints whether that year is a leap year or not. If the year is a leap year, it should print output similar to `2000 is a Leap Year`. If not, it should print output similar to `2001 is not a Leap Year`. 

Looking at this problem statement, we see that we need at least one variable to store the year that is provided as input from the user. Similarly, we need at least one conditional construct, which will allow us to print whether the given year is a leap year or not. Here's the problem statement again, with those parts highlighted:

> Write an object oriented program that accepts a positive integer(**variable**) from the command line which represents a year, and prints whether that year is a leap year or not (**conditional construct**). If the year is a leap year (**true branch**), it should print output similar to `2000 is a Leap Year`. If not (**false branch**), it should print output similar to `2001 is not a Leap Year`. 

Similarly, we can look at the second part of the problem statement and break it down as well:

> Every year that is exactly divisible by four is a leap year, except for years that are exactly divisible by 100, but these centurial years are leap years if they are exactly divisible by 400. For example, the years 1700, 1800, and 1900 are not leap years, but the year 2000 is. - [Source](https://en.wikipedia.org/wiki/Leap_year#cite_note-5)

Looking at this, we see that there are actually three conditional constructs we need to build. Let's mark them in the statement:

> Every year that is exactly divisible by four (**conditional construct 1**) is a leap year, except for years that are exactly divisible by 100 (**conditional construct 2**), but these centurial years are leap years if they are exactly divisible by 400 (**conditional construct 3**). For example, the years 1700, 1800, and 1900 are not leap years, but the year 2000 is. - [Source](https://en.wikipedia.org/wiki/Leap_year#cite_note-5)

Of course, we'll have to be careful to make sure that each branch of these three conditional statements produces the correct output. Below, we'll see how we can construct code for this problem. 

## Reading Input

Generally, one of the first things our program should do is read the input from the command line, and then store it in an appropriate variable type. In this case, we want to read a single integer, so we'd add the following line:

```python
year = int(sys[1])    
```

However, the problem statement has one very important part in it that we'll need to handle as well:

> Write a program that accepts a **positive integer** that represents a year...

So, we'll need to make sure the user has input a positive integer into our program. We can do that using a simple **If-Else** statement:

```python
year = int(args[1])

if year <= 0:
  print("Error")
else:
  # more code here
```

In this case, we might be tempted to use an **If** statement instead. However, we need to make sure our program only calculates a result if the input is positive. If it is negative, we should just print an error. Since that means our program needs two distinct branches, we should use an **If-Else** statement here. 

## Calculating Output

Once we've read our input, we need to calculate our output. Let's handle the three rules one at a time.

### Divisible by {{< math >}}$ 4 ${{< /math >}}

For the first rule, we must check to see if the year is divisible by {{< math >}}$ 4 ${{< /math >}}. We can use the modulo operator to do this. Remember that the modulo operator performs a division and returns the remainder. So, if the remainder is {{< math >}}$ 0 ${{< /math >}}, then we know that the number is evenly divisible by the divisor.

In code, we could do the following:

```python
year = int(args[1])

if year <= 0:
  print("Error")
else:
  if year % 4 == 0:
    # divisible by 4
  else:
    # not divisible by 4
    print("{} is not a Leap Year".format(year))
```

In each of these **If-Else** statements, let's place a quick comment in the code to keep track of what we know within each branch. 

### Not Divisible by {{< math >}}$ 100 ${{< /math >}}

Next, we need to handle the rule that any year divisible by {{< math >}}$ 100 ${{< /math >}} is not a leap year, even if it is divisible by {{< math >}}$ 4 ${{< /math >}}. Of course, we can easily determine mathematically that all years divisible by {{< math >}}$ 100 ${{< /math >}} are also divisible by {{< math >}}$ 4 ${{< /math >}}, so we don't have to worry about the other case in this instance. So, we can add another **If-Else** to our program:

```python
year = int(args[1])

if year <= 0:
  print("Error")
else:
  if year % 4 == 0:
    # divisible by 4
    if year % 100 == 0:
      # divisible by 4 and 100
      print("{} is not a Leap Year".format(year))
    else:
      # divisible by 4 but not 100
      print("{} is not a Leap Year".format(year))
  else:
    # not divisible by 4
    print("{} is not a Leap Year".format(year))
```

In this case, we chose to next our **If-Else** statement inside of the previous statement. So, if the year is divisible by {{< math >}}$ 4 ${{< /math >}} and also divisible by {{< math >}}$ 100 ${{< /math >}}, we print `Not a Leap Year`. If it is divisible by {{< math >}}$ 4 ${{< /math >}} and not divisible by {{< math >}}$ 100 ${{< /math >}}, which is the `false` branch of the innermost **If-Else**, we know that it must be a leap year, so we can print `Leap Year`.

### Unless Divisible by {{< math >}}$ 400 ${{< /math >}}

There's one more rule we must add, which is the rule that a year divisible by {{< math >}}$ 400 ${{< /math >}} must be a leap year, even though it is also divisible by {{< math >}}$ 100 ${{< /math >}}. So, we must add one additional **If-Else** statement. But where?

If we think back through the rules, we know that this rule is only in effect when the year is both divisible by {{< math >}}$ 4 ${{< /math >}} and {{< math >}}$ 100 ${{< /math >}}. So, we'll need to add one more statement in the `True` branch of the innermost **If-Else**:

```python
year = int(args[1])

if year <= 0:
  print("Error")
else:
  if year % 4 == 0:
    # divisible by 4
    if year % 100 == 0:
      # divisible by 4 and 100
      if year % 400 == 0:
        # divisible by 4 and 100 and 400
        print(str(year) + " is a Leap Year")
      else:
        # divisible by 4 and 100 but not 400
        print(str(year) + " is not a Leap Year")
    else:
      # divisible by 4 but not 100
      print(str(year) + " is a Leap Year")
  else:
    # not divisible by 4
    print(str(year) + " is not a Leap Year")
```

Now we've created a program that should be able to tell us if a year is a leap year or not. 

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

## Other Solutions

Of course, there are many other ways this program could have been structured that would produce the same output. For example, instead of using nested **If-Else** statements, we could rearrange them a bit to make them inline **If-Else If-Else** statements, as in this example below:

```python

if year <= 0:
  print("Error")
elif year % 400 == 0:
  # divisible by 400
  print(str(year) + " is a Leap Year")
elif year % 100 == 0:
  # divisible by 100 but not 400
  print(str(year) + " is not a Leap Year")
elif year % 4 == 0:
  # divisible by 4 but not 100
  print(str(year) + " is a Leap Year")
else:
  # not divisible by 4
  print(str(year) + " is not a Leap Year")
```

In fact, with a bit of thinking, we could reduce most of this program to a single Boolean logic expression, as in this example

```python

if year <= 0:
  print("Error")
elif ((year % 4 == 0) and (year % 100 != 0)) or (year % 400 == 0):
  print(str(year) + " is a Leap Year")
else:
  print(str(year) + " is not a Leap Year")
```

Any of these solutions is just as correct as the one we built above. It really only depends on which solution makes the most sense to us and is the easiest for us to write and debug. 