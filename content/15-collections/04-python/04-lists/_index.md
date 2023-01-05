---
title: "List"
pre: "4. "
weight: 40
---

First, let's explore the simplest of these collections, the **list**. A list is defined as an ordered collection or sequence of elements, meaning that the order in which the elements were added to the list is preserved, but that order can be updated through the use of sorting algorithms. 

We've already worked with lists in this course, but in previous modules we included one important restriction: we would know the maximum size of the list ahead of time. This is because most other programming languages use statically sized arrays as the basic collection data type.

Thankfully, lists in Python do not require a static size, and can be resized to store as much data as needed. In addition, lists are much more flexible than arrays, so in this module we'll discuss some of the more useful features of lists. 

List are generally used when:
* the number of entries in the container is not fixed 
* the programmer wants indexes which are continuous integers
* integer indexes may will not have gaps-- if indexes 1,2 and 7 all have values then indexes 0, 3-6  exists but are assigned `None`
* programmer cares what order Python stores the elements ..  elements appear in a for-loop in index order


## Creating a List

To create a list, we can simply declare it using square brackets, either containing a list of elements to be included or an empty set of brackets to create an empty list:

```python
# empty list
list1 = []

# list containing 4 elements
list2 = [1, 2, 3, 4]
```

However, we can also create lists in Python using **list comprehensions**, which allow us to build lists from a range or another list. For example, if we want to build a list that contains the first 10 perfect squares, we could do the following:

```python
list3 = [x**2 for x in range(1, 11)]
```

We could even expand that with a filter that will only include even values:

```python
list4 = [x**2 for x in range(1, 11) if x % 2 == 0]
```

To learn more about list comprehensions, we can consult the [Python Tutorial](https://docs.python.org/3/tutorial/datastructures.html#list-comprehensions) for Data Structures.

## List Operations

The `list` data type in Python defines several operations that it can perform. The full list can be found on the [Data Structures](https://docs.python.org/3/tutorial/datastructures.html) page of the Python documentation. Here are a few of the most important ones:

* `append(e)`---adds element `e` to the end of the list
* `insert(index, e)`---adds element `e` to the specified `index` position in the list. All elements at that position and after are shifted toward the end of the list.
* `x in list`---returns true if the object `x` is contained in the list `list`
* `index(o)`---returns the first index that this object can be found in the list, or raises a `ValueError` not found
* `remove(o)`---removes the first occurrence of the given object from the list, if one exists. If not, a `ValueError` is raised
* `len(list)`---returns the number of elements in the list

## Slicing

Recall from an earlier module that we can also use **slicing** to get chunks of a list. For example, here are some different ways to slice a small list:

```python
a = [1, 2, 3, 4, 5]

b = a[:3]  # [1, 2, 3]
c = a[2:]  # [3, 4, 5]
d = a[:]   # [1, 2, 3, 4, 5]
e = a[:-2] # [1, 2, 3]
```

We can even assign to a slice of a list! For more information, we can consult [An Informal Introduction to Python: Lists](https://docs.python.org/3/tutorial/introduction.html#lists) or [Data Structures: More on Lists](https://docs.python.org/3/tutorial/datastructures.html#more-on-lists).

## Iterating

What if we want to iterate through a list? Thankfully, we can use a **for each** loop to do this, just as we've learned to do previously

```python
iter_list = [5, 3, 7, 2, 4]

for x in iter_list:
  print(x)
```

## Sorting

To sort a list in Python, we can use the `sort()` method on the list itself. This will sort the list in ascending order by default, but we can provide an optional parameter to sort in descending order as well:

```python
list5 = [5, 3, 7, 2, 4]

# sort in ascending order
list5.sort()

# sort in descending order
list5.sort(reverse=True)
```

## Example

To explore how to use a list in a real program, let's look at a quick example program. Here's a short problem statement:

> Write a program that will accept a single integer as input from the terminal. If there are any errors r parsing the input, simply print "Invalid Input!" and terminate the program. If the provided integer is less than 3, it should also print "Invalid Input!".

> Using the integer provided as input, the program should generate a list of numbers representing the [Fibonacci sequence](https://en.wikipedia.org/wiki/Fibonacci_number) containing that many entries. 

> Before printing the list, the program should perform two additional operations on the list. First, if the integer provided as input is contained in the list, it should be removed. Secondly, the list should be presented in descending order, with the largest value first. 

> The program should print the list to the terminal, with each entry separated by a space. 

> The program should be implemented as two Methods - a `main()` Method that handles reading input, and a `make_list()` Method that accepts a single integer as a parameter and returns the completed list of integers. 

{{% notice note "Fibonacci Sequence" %}}

The Fibonacci sequence is produced by adding the two previous numbers together to generate a new number. Traditionally, the first two Fibonacci numbers are `0` and `1`. So, the next number is `0 + 1 = 1`, and the number following that is `1 + 1 = 2`. The sequence continues indefinitely.

Formally, the Fibonacci sequence is defined as:

{{< math >}}
$$F_0 = 0$$
$$F_1 = 1$$
$$F_n = F_{n-1} + F_{n-2}$$
{{< /math >}}

You can find more information about the Fibonacci Sequence on [Wikipedia](https://en.wikipedia.org/wiki/Fibonacci_number).

{{% /notice %}}

For example, if the input provided is `8`, the program would begin by generating the first eight Fibonacci numbers, starting with `0` and `1`:

```tex
[0, 1, 1, 2, 3, 5, 8, 13]
```

Then, since `8` is contained in the list, it should be removed:

```tex
[0, 1, 1, 2, 3, 5, 13]
```

Finally, the list should be sorted in descending order, so the final list returned will be:

```tex
[13, 5, 3, 2, 1, 1, 0]
```

### `main` Method

So, let's build the program. We can start with this simple skeleton:

```python
import sys

class ListExample:

  @staticmethod
  def main(args):
    reader = sys.stdin
    try:
     count = int(reader.readline())
      if count < 3:
        print("Invalid Input!")
        return
      l1 = make_list(count)
      l1 = [str(l) for l in l1]
      print(" ".join(l1))
        
    except Exception as e:
      print("Invalid Input!")
      return

  def make_list(x):
    # MORE CODE GOES HERE
     
# main guard
if __name__ == "__main__":
  ListExample.main(sys.argv)
```

This program contains a simple `main()` method that will handle reading and parsing the input from either the terminal or a file provided as a command-line argument. It will also verify that the input is an integer, and it is a value that is at least `3` or greater. If will then call the `make_list()` Method using the input as a parameter to create the list. It uses list comprehension to reassign the variable `l1` to a list of strings.  Finally it will print the result using the `String.join()` method to place a space between each element of the list. Pretty nifty, right?

So, all we need to worry about implementing is the `make_list()` Method.

### `make_list` Method

{{% youtube CRJcdyUDneI %}}

[Video Materials]({{<relref "./video">}})

<!-- TODO Update Video -->

<p style="color:red; padding:10"><b>Note:</b> video unnecessarily marks the method `make list` as static method.  We will follow the convention that only the start-up 'main' method shall be static.</p>

Let's dive into the `make_list()` method. First, we'll need to create a list that contains the first two Fibonacci numbers. So, the code would be as follows:

```python

def make_list(x):
  l1 = [0, 1]
```

Following that, we'll use a simple **for** loop to generate the next few numbers. We can either have separate variables to represent the previous values, or we can just read them directly from the list using square brackets:

```python

def make_list(x):
  l1 = [0, 1]
  for i in range(2, x):
    new_number = list[i-1] + list[i-2]
    list.append(new_number)
```

Once we've generated our list, we need to make sure `x` is not in the list. If so, we can just remove it using the `remove()` method. We must be careful to only call the `remove()` method if we are sure it is in the list, otherwise it will raise a `ValueError`: 

```python

def make_list(x):
  l1 = [0, 1]
  for i in range(2, x):
    new_number = list[i-1] + list[i-2]
    list.append(new_number)
  if x in list:
    list.remove(x)
```

Finally, we can use the `sort()` method to sort the list. We'll need to remember to include the optional parameter to sort in descending order. Once we've sorted the list, we can return it.

```python

def make_list(x):
  l1 = [0, 1]
  for i in range(2, x):
    new_number = list[i-1] + list[i-2]
    list.append(new_number)
  if x in list:
    list.remove(x)
  list.sort(reverse=True)
  return list
```

That's all there is to it! See if you can complete the code in `ListExample.py` to the left, then use the two assessments below to check your program. 

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}
