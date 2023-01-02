---
title: "Range & For Loops"
pre: "2. "
weight: 20
---

## Range

The Python built in type `range` produces a list-like object of integers.  We build a range object using the built in function `range()`.  `range()` can be used in three ways.

1. `range(<stop>)` - By providing a single input, it will produce a list of numbers starting at `0` and counting up by `1`, which contains the given number of elements. So, `range(3)` will produce a list containing `0`, `1`, and `2`. Or, another way to think about it, it includes all the numbers from `0` up to, but not including, `<stop>`.
1. `range(<start>, <stop>)` - With two inputs provided, it will produce a list of numbers starting at `<start>` and ending before `<stop>`. So, `range(1, 4)` will produce a list containing `1`, `2`, and `3`. As before, `<stop>` is not included in the list, but `<start>` is.
1. `range(<start>, <stop>, <step>)` - The third input gives the size of the step between numbers. For example, `range(1, 10, 3)` will produce a list that contains `1`, `4`, `7`. As before, it will not include `10` since that is not strictly less than the value of the second input, `<stop>`. 

## For

Ranges are typically used in conjunction with Python's *Enhanced For Loop* keyword **for**.  Python does not have a standard **For** loop, instead it uses the keyword `for` for an **enhanced for** loop.  Python calls their version of the enhanced for loop, the "For Loop"--which can cause both confusion and aggravation.

For-loops have a pretty straight-forward syntax:

```python
for <variable> in <iterable>:
  <loop code block>
```

{{% notice info "Python Iterable" %}}

In Python, instances of classes which implement the special Python method `__iter__()` method are called "iterable".  In this course you will use the built in iterable classes:

* list
* range
* str

300-level Computational Core courses will teach how to properly implement the `__iter()__` method in classes you design.

{{% /notice %}}


Let's break this syntax down into each individual part to understand how it works.

1. For right now, the `<iterable>` is any list, string or range.
1. The `<variable>` names the variable that will be used as an _element_ of the`<iterable>` in the loop.
1. The `<loop code block>` is the same as in the while loop.

So the program

```python
for i in ['cat', 'dog', 'fish']:
    print(i)
```

prints

```tex
cat
dog 
fish
```

<b>Note:</b> The `<iterable>` must be aggregate data.  `for i in 2:` will crash with the error `int is not iterable`.  `for i in [2]:` does work, `[2]` is the list containing `2`.

<b>Note:</b> the Enhanced For Loop has no loop condition --loop conditions only exist in WHILE and standard FOR loops.  In an Enhanced-For, you are going to see every element of the `<iterable>`.

## Sequences 

Lists, ranges and str are all members of Python's built-in sequence class, and as a result all have a few common traits that makes them good candidates to be  "for loop `<iterable>`s".

```python
a_list = ['cat', 'dog', 'fish']
b_str ="Wildcat"
c_range= range(4) # yields integer values of 0,1,2,3
```

1. They are indexed starting at 0 and have no gaps: 
    1. a_list[0] == 'cat', 
    2. c_range[2] == 2, 
    3. b_srt[7] == error there are only 7 letters in "Wildcat" so the last index is 6.
2. In a `for` loop, they always provide elements (yield elements) in index order, starting at 0.
3. They can all be used with the built in function `len()` to determine how many elements they have: len (b_str) == 7.
4. str and ranges are immutable--you cannot change their elements; this enhances program stability in a certain situations.

Thus in Python, a standard way to sum the numbers from 1 to 10 using the accumulator pattern in Python is:

```python
sum = 0
for i in range(1,11):  # yields numbers from 1 to 10
    sum += i
print(sum)
```

{{% notice info "Built-in Function ist()" %}}

In a fashion analogous to how `int(2.3)` converts  the float `2.3` into the int `2`.  `list()` converts other types of iterables into lists.  Thus:

```python
a = range(5)  # a is range object with values 0, 1, 2, 3, 4
b=list(a)     # b is a list object equal to [0, 1, 2, 3, 4]

```

{{% /notice %}}
