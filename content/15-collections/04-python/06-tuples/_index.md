---
title: "Tuples"
pre: "6. "
weight: 60
---

The last data structure we will explore is the **tuple**. A _tuple_ in mathematics is defined as a "finite ordered list" of items. So, it is a list of items that is not infinite, and the ordering of the items in that list matters. 

Thankfully, Python includes support for immutable tuples directly in the language, so we can use them in our programs quickly and easily.

Tuples are generally used when:
* the number of entries in the container is fixed 
* the values in the tuple will never change (tuples like strings are immutable)
* the programmer wants indexes which are continuous integers
* integer indexes may will not have gaps-- if indexes 1,2 and 7 all have values then indexes 0, 3-6  exists but are assigned `None`
* programmer cares what order Python stores the elements ..  elements appear in a for-loop in index order

## Creating a Tuple


To create a tuple in Python, we can simply assign multiple values to a variable, separated by commas:

```python
tuple_one = 123, 456, 789
```

In Python, assigning values to a tuple in this way is referred to as _packing_. As with lists and dictionaries, we can even store different types of data in the same tuple, as seen below:

```python
tuple_two = 876, "Hello", True
```

Tuples can be nested, using parentheses to enclose any inner tuples for clarity:

```python
tuple_three = 123, ("Hello", True)
```

To create a tuple containing fewer than two elements, we must use some special syntax:

```python
# empty tuple uses empty parentheses
tuple_empty = ()

# single item tuple uses a comma after the item
tuple_single = "Hello",  # alterante t_single = ("Hello")
```

## Using a Tuple

To access individual elements of a tuple, we can use the same square bracket notation `[]` we've learned with arrays:

```python
tuple_access = 123, 456, "Hello"

print(tuple_access[0])  # 123
print(tuple_access[1])  # 456
print(tuple_access[2])  # Hello
```

We can also _unpack_ values in a tuple, storing them in individual variables:

```python
tuple_unpack = 123, 456, "Hello"

x, y, message = tuple_unpack

print(x)       # 123
print(y)       # 456
print(message) # "Hello"
```

We can even do the same for a method that returns a tuple:

```python
x, y = get_coordinates();
```

As we can see, tuples appear to be very similar to lists in Python. However, tuples have one important property that sets them apart from lists---they are _immutable_. This means that once a tuple is created, the items it contains cannot be changed or updated:

```python
tuple_modify = 123, 456, "Hello"

tuple_modify[0] = 789  # raises TypeError
```

So, we should always remember that items in a tuple cannot be modified, whereas a list can be modified. Because of that, we typically use tuples when returning data from a function or method, or when storing associated data in a list. 

## Example

To really explore how we could use a tuple in our code, let's build a simple program. Here's a problem statement:

> Write a program that will read lines of input from the terminal. Valid input is a single line with two space separated integers between 0-9.

> The program should implement a simple search game. Players will guess coordinates on a 10x10 grid, trying to find a hidden item. So, input will take the form of two integers, separated by a space. If the program is unable to parse an input for any reason, it should print "Invalid Input!" and terminate the program.

> When a player makes a guess, the program should respond with one of the four cardinal directions: "North", "South", "East", "West", indicating the direction of the hidden item from the guess. For simplicity, the program will only respond "North" or "South" if the player's guess is not on the same row, or `x` coordinate, as the location, and "East" or "West" only if the player's guess is on the same row as the location. If the player guesses correctly, simply print "Found!" and terminate the program. If the player repeats a guess, the program should print "Repeat!" instead of a cardinal direction. 

> The hidden location should be randomly generated and stored in a tuple as a global variable, and the program should maintain a global list of tuples representing the locations already guessed.

> The program should be implemented as two functions: `main()` that handles reading input and printing output, and a `make_guess()` function that accepts two integers, `x` and `y` as parameters, and responds with a string representing the result of that guess. 

Let's see if we can build this program using tuples. 

## `main` Method

First, let's look at the main function. Once again, we'll start with skeleton code that is very similar to the other examples in this chapter:

```python
import sys
import random

class TupleExample:
  
  guesses = []
  location = None

  @staticmethod
  def main(args):
    reader = sys.stdin
    lines = "0 0"
    while len(lines.strip()) > 0:
        lines = reader.readline()
        if len(lines.strip()) > 0:
            try:
              val = lines.split(" ")
              x = int(val[0])
              y = int(val[1])
              output = TupleExample.make_guess(x, y)
              print(output)
              if output == "Found!":
                return
      
            except Exception as e:
              print("Invalid Input!")
              return

  def make_guess(x, y):
    # MORE CODE GOES HERE
     
# main guard
if __name__ == "__main__":
  TupleExample.main(sys.argv)
```

At the top of the class, we have included two fields to store our list of previous guesses and the location that should be guessed. For now, we'll set that value to `None` until we initialize it in our `make_guess()` function.

In this code, we are simply reading a line of input, splitting it into two tokens, and then parsing each token to an integer to get the `x` and `y` values of the guess. After that, we can call the `make_guess()` function with those values, and print the result. Finally, we must check to see if the result is `"Found!"`. If so, we can terminate the program using the `return` keyword.

## `make_guess` Function

{{% youtube 1ErzWJlvl0M %}}

[Video Materials]({{<relref "./video">}})

<p style="color:red; padding:10"><b>Note:</b> video unnecessarily marks the method `make guess` as a static method.  We will follow the convention that only the start-up 'main' method shall be static.</p>

Now that we have our `main()` Method written, let's work on the `make_guess()` function. For starters, we must make sure our random location has been established. So, we'll do that in the code shown below:

```python
def make_guess(x, y):
  if TupleExample.location is None:
    TupleExample.location = random.randint(0, 9), random.randint(0, 9)
```

Here, we are using the `randint()` method of the `random` library to generate a number between `0` and `9`, inclusive.

Now we must handle producing the output. First, we need to create a new tuple for the guess, and then check and see if the guess is correct, or if it has already been guessed:

```python
def make_guess(x, y):
  if TupleExample.location is None:
    TupleExample.location = random.randint(0, 9), random.randint(0, 9)
  guess = x, y
  if guess == TupleExample.location:
    return "Found!"
  if guess in TupleExample.guesses:
    return "Repeat!"
```

Here, we are taking advantage of the fact that Python can automatically handle checking for equality between tuples as easily as any other value. As long as both tuples contain the same values in the same order, they are considered equal.

If we find out that the guess is not the hidden location, then we should store it in our list of guesses:

```python
def make_guess(x, y):
  if TupleExample.location is None:
    TupleExample.location = random.randint(0, 9), random.randint(0, 9)
  guess = x, y
  if guess == TupleExample.location:
    return "Found!"
  if guess in TupleExample.guesses:
    return "Repeat!"
  TupleExample.guesses.append(guess)
```

Finally, we can handle printing the hints for cases where the guess is not on the same row:

```python
def make_guess(x, y):
  if TupleExample.location is None:
    TupleExample.location = random.randint(0, 9), random.randint(0, 9)
  guess = x, y
  if guess == TupleExample.location:
    return "Found!"
  if guess in TupleExample.guesses:
    return "Repeat!"
  TupleExample.guesses.append(guess)
  if guess[0] > TupleExample.location[0]:
    return "North"
  if guess[0] < TupleExample.location[0]:
    return "South"
```

Below that, we can assume that the guess is on the same row, so we'll have to handle the cases where the guess is east or west of the location:

```python
def make_guess(x, y):
  if TupleExample.location is None:
    TupleExample.location = random.randint(0, 9), random.randint(0, 9)
  guess = x, y
  if guess == TupleExample.location:
    return "Found!"
  if guess in TupleExample.guesses:
    return "Repeat!"
  TupleExample.guesses.append(guess)
  if guess[0] > TupleExample.location[0]:
    return "North"
  if guess[0] < TupleExample.location[0]:
    return "South"
  if guess[1] > TupleExample.location[1]:
    return "West"
  else:
    return "East"
```

{{% notice note "Use a Tuple or New Class?" %}}

Tuples are useful, but limited.  Conventional Python style is to use tuple when returning multiple values.  However, using a tuple signals the grouping is only transitory.  If a tuple represents a data aggregation that should be persistent, it is generally recommended that you make a class with properties and return an instance of t class instead.  Classes can be better documented and extended.

```python
def fie():
    ...
    return a,b

def fee():
    ...
    t1= fee()
    foe(t1)
    z = t1[0].operation()
    ...
    
def foe(x):
    ...
```

In this instance, it looks like the data returned by `fie` is persistent, and maybe there should be a class for it.  This is particularly true when a tuple contains lots of elements or it the tuple's elements themselves are complex objects.

{{% /notice %}}

There we go! That method will handle producing the output for any guess provided by the user. See if you can complete the code in `TupleExample.py` to the left, then use the two assessments below to check your program. 

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}