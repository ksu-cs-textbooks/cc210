---
title: "A Worked Example"
pre: "6. "
weight: 60
---

{{< youtube S1tNf9TTwzo  >}}

[Video Materials]({{% relref "./video" %}})

Now that we've learned some of the different looping constructs in Python, let's work through a completed example to see how we can use loops to build more advanced programs.

## Problem Statement

For this example, we'd like to build a program that matches the following problem statement:

> Write a program that will accept a series of integers from the terminal, one per line. It will continue to accept integers from the user until the user inputs 0. If the user inputs a negative number, the program should print "Error! Positive Integers Only" and continue to receive input. Once the user inputs 0, the program should print the sum and average of the positive integers input by the user. 

Let's see if we can build a program that meets that specification.

## First "Sketch" out the Control Logic

It is often a mistake to start with coding.  Lets instead start by drawing a flow chart for this program. We know that we need to get keyboard input, convert it to an integer then take some actions based on its value. 

![Intial Flow Chart](/images/05-loop/example_1.png)

We also know we will have to repeat this an indeterminate number of times, and a **While-Loop** is the preferred construct to use for this. So lets add a **While** loop. While we are at it, make sure that if `0` is input for x, we do nothing and let the program flow back to the while loop check.  Something like this will work.

![Revised Flow Chart](/images/05-loop/example_2.png)

Note a few things:
1. We added a `x > 0` check, this is keeps us from adding `0` to our sum ... which won't effect the value of the sum but may impact put calculation of the average.
1. The `x < 0` and `x > 0` paths are mutually exclusive. We should probably consider using **If-Else-If** statements to communicate this intentional exclusivity when we write our code.
1. The flow chart is a "complete" in so much as it models the control flow of the program; but is skips many details.
    1. How can we check if `x != 0` that first time if we don't get a value for `x` until we are in the loop?
    1. How do we calculate the average?
    1. Where does the Scanner stuff go?


Keep in mind that a flow chart is an abstraction of the code you need to write; a model containing some important subset of the details.  This one is sufficient to ensure we use the right loop and if statements.

## Code the Boiler Plate

First, we'll need to build the boiler plate of our program. The part that handles input from a file or the key board.  Let's store this program in `Example.py`, which should be open to the left.
```python
# Load required modules
import sys

class Example:
    
    @staticmethod
    def main(args):
        reader = sys.stdin # this creates an alisas for stdin
        # more code here

# Main Guard
if __name__ == "__main__":
    Example.main(sys.argv)

```

For the rest of this example, we'll look at a smaller portion of the code. That code can be placed where the `MORE CODE GOES HERE` comment is in the code above. 

## Handling Input

Next, we want to build a program that can accept a series of integers from the user. Since we don't know how many we'll get, we'll probably want to use some sort of a **While** loop. So, let's add in a **While** loop and start building from there:

```py
while :
  # logic here
```

Inside of that loop, we know we need to read an integer from the user, so we can add the code for that as well:

```py
while :
  x = int(reader.readline())
```

Next, we need to determine when the loop should terminate. In this case, we can go back to the problem statement above, where we see the line:

> It will continue to accept integers from the user until the user inputs 0.

So, we might be tempted to do something like this:

```python
while x != 0:
  x = int(reader.readline())
```

However, that code has a very important error in it. We haven't initialized `x` outside of the **While** loop, so when we try to run this code we'll get an error. So, let's resolve that error:

```python
x = 0
while x != 0:
  x = int(reader.readline())
```

This looks a bit better, but it also has a problem. We need to initialize `x` to some value, so we quickly chose to initialize it to $0$. However, by doing so, we should hopefully see that it will never enter the loop, since `x != 0` will immediately be `False`. 

{{% notice info "Sentinel Values" %}}

In the above loop, "zero" may be referred to as a <a href="https://en.wikipedia.org/wiki/Sentinel_value">sentinel value</a>.  A value to watch for and alter the program's behavior when it occurs.  It is important to ensure you don't inadvertently initialize your variable to a sentinel value.

{{% /notice %}}

So, let's set `x = 1` instead for now:

```python
x = None
while x != 0:
  x = int(reader.readline())
```
`None` is a keyword in Python.  It is used to define a variable before its value can is known, as is the case here. It is also used in object oriented programming when there is a failure to create an object, more on that later in the course.  The preferred syntax for checking if a variable in `None` is ` x is None`, which returns true if the variable x is set to `None`.

When you run this fragment, you should see that it indeed keeps prompting you for input until you enter `0`.  Note that if you enter a non-integer the program will crash, and that is ok.

That's a good start! As we continue to work on this program, we'll revisit the structure of this code and see that there might be a better way to do it. For now, let's press on ahead.

## Invalid Inputs

Next, we can handle the error messages for any invalid inputs. From the problem statement:

> If the user inputs a negative number, the program should print "Error! Positive Integers Only" and continue to receive input.

This case is pretty simple. We want to check if the user has entered a number less than $0$. If so, we should just print out an error message, but continue to receive input. The word "continue" gives us an important clue toward how we can accomplish this task. Here's one way to build this test into our program:

```python
x = None
while x != 0:
  x = int(reader.readline())
  if x < 0:
    print("Error! Positive Integers Only")
    continue
  # logic here
```

In this code, if the user enters a negative number, we simply use an **If-Then** statement to find that error, print out the error message, and then the `continue` keyword will cause the program to loop back to the beginning and read another input. Of course, we can do this without the `continue` keyword as well, using an **If-Then-Else** statement instead:

```python
x = None
while x != 0:
  x = int(reader.readline())
  if x < 0:
    print("Error! Positive Integers Only")
  else:
    # logic here
```

Either approach works equally well. Some developers prefer to avoid the use of `continue` and `break` keywords because they make it more difficult to understand loops, while other developers prefer to avoid having the logic of the loop nested several layers deep in many **If-Then-Else** statements. It is really up to developer preference and the overall style guide that is in effect. 

For this example, we'll use the code with the `continue` keyword, just to get a better understanding of how it works.

## Program Logic

Once we've handled our user inputs, we can include our program's logic. In this case, we need to calculate both the sum and average of all of the numbers entered by the user. Calculating the sum is pretty simple! We can just include a `sum` variable and add each input to that variable:

```python
x = None
sum = 0
while x != 0:
  x = int(reader.readline())
  if x < 0:
    print("Error! Positive Integers Only")
    continue
  sum += x
print("Sum: " + str(sum))
```

To calculate the average of a set of numbers, we must remember the formula $\text{Average} = \frac{\text{Sum}}{\text{Count}}$. Since we already are tracking the sum, we can just add another variable to keep track of the count of inputs:

```python
x = None
sum = 0
count = 0
while x != 0:
  x = int(reader.readline())
  if x < 0:
    print("Error! Positive Integers Only")
    continue
  sum += x
  count += 1
print("Sum: " + str(sum))
print("Average: " + str(sum / count))
```

Now, let's see if this works.

{{% notice tip "Try It!" %}}

See if you can complete the program using the example code above in `Example.py`. Does it work correctly? 

There is a very important logic bug in the code above. See if you can figure out what it is before continuing. 

{{% /notice %}}

## Logic Bug

The code above contains a very important logic error. To find that error, let's run the program by entering the numbers `1` and `3`, followed by `0` to end the program. Here's the output we should receive:

![Logic Error Output](/images/05-loop/5.7.p.5.error.png)

Notice that the sum of `4` is correct, but the average is `1.333333` instead of `2`. Why is that?

If we look closely at our program above, we notice that the program will still increment `count` when we input `0` to stop the program. So, it believes that we've entered three numbers, when we actually only entered two. Therefore, we need to figure out some way to prevent the program from incrementing `count` when we input `0`.

There are several ways we can accomplish this. One way is to simply wrap the program logic in another **If** statement, as in this example:

```python
x = None
sum = 0
count = 0
while x != 0:
  x = int(reader.readline())
  if x < 0:
    print("Error! Positive Integers Only")
    continue
  if x != 0:
    sum += x
    count += 1
print("Sum: " + str(sum))
print("Average: " + str(sum / count))
```

In addition, we could rearrange the code just a bit to make the **While** loop's Boolean expression a bit clearer:

```python
sum = 0
count = 0
x = int(reader.readline())
while x != 0:
  if x < 0:
    print("Error! Positive Integers Only")
  else:
    sum += x
    count += 1
  x = int(reader.readline())
print("Sum: " + str(sum))
print("Average: " + str(sum / count))
```

In this example, we read an input from the user before entering the loop. So, if the user initially inputs `0`, it skips the loop entirely, which is fine. If the input is not `0`, then it will enter the loop and check to see if it is negative. If it is, it will print the error message, but if not, it will update the sum and count accordingly. Finally, at the end of the loop, it will read another input from the user, then immediately loop back to the beginning and make sure that the user has not input `0` before starting the next iteration. 

However, this code does include two lines that read input from the user. This violates one principle of writing good code, which is **DRY**, or _**Don't Repeat Yourself**_. If at all possible, we want to avoid writing two lines of code that perform the same action. So, while this code may be a bit simpler to read, it may also be a bit more difficult to update later. For example, what if a future developer needs to change this program to read floating point numbers instead of integers? If that developer does not update both lines that read input from the file, it could make the program unusable!

Finally, it may be best to simply include several **If-Else If-Else** statements to make everything clear in the code, as in this example:

```python
x = None
sum = 0
count = 0
while x != 0:
  x = int(reader.readline())
  if x < 0:
    print("Error! Positive Integers Only")
  elif x>0 :
    sum += x
    count += 1
  else:
    pass
print("Sum: " + str(sum))
print("Average: " + str(sum / count))
```

This code is probably one of the best ways to accomplish this task. We use a clear string of **If-Else If-Else** statements to show that there are two possible operations inside of the **While** loop. Either the input is negative, in which case we print an error message and restart the loop; or the input is greater than 0 and is accepted for our calculations. If it is `0`, execution follows the `else: pass` branch and flows to the Loop Condition.

Many programmers will omit the `else: pass` branch.  `pass` is a Python keyword meaning -"do nothing";  it is used when syntax REQUIRES there be a code-block or statement-body, but you do not actually want to do anything in that block.

{{% notice info "The Accumulator Pattern" %}}

This process of iterating or looping and then updating a variable each time is known as the accumulator-pattern and is used to solve a lot of different kinds of problems in computer science.  The keys are: 
1. Declare the accumulator outside the loop, so it is available after the loop terminates
1. Make sure the logic in the loop is correct so you only accumulate the values you want

{{% /notice %}}

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}



