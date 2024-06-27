---
title: "A Worked Example"
pre: "5. "
weight: 50
---

{{< youtube oeee8aLz91Q  >}}

[Video Materials]({{% relref "./video" %}})

<!-- TODO Update Video -->

Let's get some more practice creating our own methods by building another example program. This program will perform convert the volume-measurement "cups" into either fluid ounces, tablespoons or teaspoons.

## Problem Statement[^1]

[^1]: Idea adapted from Gaddis, Tony "Starting out with JAVA", 5th ed, Pearson: New York 2012

For this example, we'll need to build a program that matches this problem statement:

> Write a program[^2] that accepts terminal input, allowing the user to enter a number of cups, and then selecting the conversion output as: fluid ounces, tablespoons or teaspoons. The program will then calculate the correct value and display it with the correct units.

> The program should contain one class `Example`, and run from the command line with the command `python3 Example.py.`

> When printing, all decimal values should be rounded to the nearest tenth (one decimal place), use `{:.1f}` with the str format() method. The final output of the program should look similar to the following: 

[^2]: In the Computational Core, from CC 210 on out we assume that all programs are to be written in an object oriented style.

```tex
Please enter the number of cups to convert:
.5
Select 1 (ounces), 2 (tablespoons) or 3 (teaspoons):
3
24.0 teaspoons
```

That seems like a pretty straightforward problem statement. Lets see how we might structure the program.

## Methods

First, we could look at the problem statement and try to divide the program into a number of methods to perform each action. In this case, it looks like we have a few important actions that could be made into methods

1. Getting the user input
1. Performing the conversion
1. Printing the converted value and units

Lets structure the class so it has the following methods


> main(args)-- gets input and prints output, needed so program runs from the command line
> convert(cups, units) -- select proper conversion and returns string to print
> to_ounces(cups) -- returns right number of ounces
> to_tablespoons(cups) -- returns right number of tablespoons
> to_teaspoons(cups) -- returns right number of teaspoons

#### Program "flow"

`main` will get two keyboard entries and convert them to numbers.  `main` will call `convert`, printing the string `convert` supplies.

`convert` will get the correct value for the conversion by calling the proper `to_???` method based on the value it receives as a parameter.  It will use that value to build and return a string.

`to_???` takes the value it receives for its parameter, and returns the proper amount.

###  Building the Scaffolding

We can already put together the skeleton of the program

```python
import sys

class Example:
    
    @staticmethod
    def to_ounce(c: float) -> float:
        pass

    @staticmethod
    def to_tablespoon(c: float) -> float:
        pass
    
    @staticmethod
    def to_teaspoon(c: float) ->
        pass

    @staticmethod 
    def convert(cups: float, units: int) -> str: 
        pass
    
    @staticmethod
    def main(args: list):
        reader = sys.stdin   
    
# main guard
if __name__ == "__main__":
    Example.main(sys.argv)
```
Here we set up the class, the methods and the main guard.  We know that proper object oriented programs pass `sys.argv` to `main` and that we'll  need to read the keyboard, so we import `sys`.

For each method we establish its "signature"; its name and parameters.  I have include the optional commenting for expected parameter type (:float) and return type (-> float).  This is not necessary but can help clarify the design in longer more complex efforts.

For each method we also include a body; for most it is the keyword `pass` since we don't know what to do yet.  The Python interpreter <b>requires</b> all methods have bodies, so we include the "do nothing" command so this program will run without error.

Finally, we include a main guard that will run the program , passing the command line arguments to `main()`. 

{{% notice info "Order of Method Definitions" %}}

Inside a class, it does not matter what order the methods occur. By course convention, `main()` will be the last method in a class.

In non-object oriented programming, i.e. if using Python procedurally, definitions must occur before calls.  In this instance, order is important and Python will throw exceptions for calling undefined functions/methods.

{{% /notice %}}

### `to_` Methods

We know that 1 cup is 8 fluid ounces, or 16 tablespoons or 48 teaspoons.  So we can complete and test our `to_ounces` method as follows:

```python
    @staticmethod
    def to_ounce(cup: float) -> float:
        return cup * 8.0

    @classmethod
    def __TEST(cls):
        volume = 0.0  # 0 oz
        print("{:.1f} cups is: ".format(volume), end="")
        value = Example.to_ounce(volume)
        print("{:.1f} ounces".format(value))

        volume = 1. # 8.0 oz
        print("{:.1f} cups is: ".format(volume), end="")
        value = Example.to_ounce(volume)
        print("{:.1f} ounces".format(value))

        volume = 0.6 # 4.8 oz
        print("{:.1f} cups is: ".format(volume), end="")
        value = Example.to_ounce(volume)
        print("{:.1f} ounces".format(value))


    @staticmethod
    def main(args: list):
        Example.__TEST()
```

Note how we write one method then test one method.  One could use an input for the tests, `volume = float(reader.readline())`.  However in unit testing (which covers the testing of one method in isolation), it is standard to "hard code" the test values, that way you can be sure you have covered boundary conditions and can pre-calculate the answers.

{{% notice note "Test Method" %}}

We recommend defining your test method

```python
@classmethod
def __TEST(cls):
```

This will make it hard for other programs (classes) to access the `__TEST` method and provide it access to class features should there be any.  Both these topics will be expaned on in later modules.

{{% /notice %}}

We leave it to you to write and test the the other `to_` methods.

Be sure to remove the test code from `main()` when you are finished.

### Convert

`convert()` contains the logic for selecting the appropriate conversion function, calling it and then returning the string to be printed.  

Since the conversions are all mutually exclusive (you must pick exactly one conversion) we will use an IF-ELSE-IF construct.  Something like:

```python
    @staticmethod
    def convert(cup: float, units: int) -> str:
        if units == 1:
            value = Example.to_ounce(cup)
            rtrn = "{:.1f} fluid ounces".format(value)
        elif units == 2:
            value = Example.to_tablespoon(cup)
            rtrn = "{:.1f} tablespoons".format(value)
        elif units == 3:
            value = Example.to_teaspoon(cup)
            rtrn = "{:.1f} teaspoons".format(value)
        else:
            rtrn = ""
        return rtrn
    
    @classmethod
    def __TEST(cls):
        #  "test code"
        volume = 0.7  # 5.6 oz
        units = 1
        string1 = Example.convert(volume, units)
        print("{:.1f} cups is: ".format(volume), end="")
        print(string1)

        volume = 0.7  # 11.2 Tsp
        units = 2
        string1 = Example.convert(volume, units)
        print("{:.1f} cups is: ".format(volume), end="")
        print(string1)   
        
        volume = 0.7  # 33.6 tsp oz
        units = 3
        string1 = Example.convert(volume, units)
        print("{:.1f} cups is: ".format(volume), end="")
        print(string1)       

    @staticmethod
    def main(args):
        Example.__TEST()
```

In `convert()` we call the appropriate function and build then return the string. Observe how we include an `else:` that assigns the return variable^[I almost always use the identifier 'rtrn' for every method -- Bud LaVezzi] the value `None`.  Our spec does not tell us what to do if invalid inputs are given, so this is a good default. 

By default in Python, a method which does not explicitly return a value returns `None`.  However, by explicitly returning `None`, we communicate to other readers that the IF-ELSE should have been inclusive of all valid values.

Notice how the test code uses only one value for volume.  We are testing the logic that picks the right method and returns the correct string.  We should have already tested that each `to_` method works correctly for volume conversions; there is no reason to test with different volumes here. 


### `main()`

Finally, we should write `main()`.  It should prompt the user for the number of cups and the units in which to convert it (as ints 1-3).  It should then call convert and print the answer.  We leave `main()` for you to do write and test.

```python
    @staticmethod
    def main(args):
        reader = sys.stdin
        print ("Please enter the number of cups to convert:")
        cup = float(reader.readline())
        print("Select 1 (ounces), 2 (tablespoons) or 3 (teaspoons):")
        units = int (reader.readline())
        string1 = Example.convert(cup,units)
        print(string1)    
```


## Grading
When you are ready, use the two grading tests to make sure our program meets the expected specification. Specifically, the first grading test will check to make sure our program contains the following method definitions:

* `main(: list)`
* `to_ounce(: float)`
* `to_tablespoon(: float)`
* `to_teaspoon(: float)`
* `convert(: float, : int)`

The second test will check that each method performs the correct operation as shown above. 

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

