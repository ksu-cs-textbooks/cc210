---
title: "Loops with Lists"
pre: "8. "
weight: 80
---

One of the most powerful ways to use lists is to combine them with loops. Loops provide an easy way to perform operations on all elements in a list, no matter what the size of the list is.

Let's go back to the flowchart seen earlier in this chapter, and see if we can implement that program in Python.

![Array Iteration Flowchart](/images/08-array/6.3.iteratearray.png)

The program first gets a value for the total number of elements in the array (list).  It then gets the value for each element, and finally sums them element values up.  We will implement this as a "driver-class"^[Driver classes have only one feature, a @classmethod `main()` method].

We'll need to start with our standard program skeleton which reads from the keyboard.  Place this code in `ArrayLoops.py`, which should be open to the left:

```python
import sys

class ArrayLoops:
    
    @classmethod
    def main (cls, args):
        reader = sys.stdin
        pass


if __name__ == "__main__":
    ArrayLoops.main(sys.argv)

```

For the rest of this example, we'll look at a smaller portion of the code. That code goes in the body of the `main()` method.


## Creating the List

Looking at the flowchart above, we must first accept one input from the user, an integer `x` that gives the size of the list. Then, we want to create a list named `a` which is able to store those elements. 

```python


x = int(reader.readline())
a = []
```

In the code, we use our reader to read an integer from the user and store it in `x`. Then, we can initialize a list named `a`.

## Filling the List

Next, we'll enter a for loop that reads input from the user, and then places that input into the list we created. Here's what that might look like in Python:

```python
x = int(reader.readline())
a = []

for i in range(0, x):
  y = int(reader.readline())
  a.append(y)
```

Here, we are using a **For** loop to iterate `x` times to fill the list. Inside of the loop, we simply read another input from the user, then append that input to the end of the list.  Note use of the `float`. For `x` it makes sense to assume it is an integer, after all how would one take a fractional (or negative) number of inputs.  However, summing real numbers, numbers with non-zero decimal places is also very reasonable.



## Finding the Sum

Finally, once we've filled the list, we must iterate over each element to find the sum and then print that to the terminal:

```python
x = int(reader.readline())
a = []

for i in range(0, x):
  y = float(reader.readline())
  a.append(y)
  
sum = 0
for j in a:
  sum += j
  
print("{:.2f}".format(sum))
```

Here, we are **For** loop to iterate over each element stored in the list `a`. Once inside of the loop, we can use `j` to refer to the current element in `a` that we are looking at. Notice that it is not the _index_ of that element, but the actual value of the _element_ itself. 

So, we can simply add the value of `j` to the `sum` variable. Once the loop has terminated, we can just print the `sum` variable to the terminal. Also we use the `"{:.2f}".format(sum)` to format the output to two decimal places.


{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

{{% notice warning "For Each Loops are Read Only!" %}}

When using a For loop in Python to iterate over a list, the list itself cannot be changed from within the loop. If that happens, the Python program will throw an error and stop. 

So, we must make sure we don't try to edit the list from within an Forloop. Instead, we can use a range and iterate over that

```python
a = [1, 2, 3, 4]

# use a range
for num in range(len(a)): #len(a) only gets evaluated at the start
  a.append(a[num])
```

{{% /notice %}}

**Reference:** [for Statements](https://docs.python.org/3/tutorial/controlflow.html#for-statements)
