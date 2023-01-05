---
title: "Dictionaries"
pre: "5. "
weight: 50
---

Next, let's explore another important collection, the **dictionary**. Some programming languages, such as Java, refer to this collection as a **map** as well. 

A map is a collection that associates, or _maps_, a **key** to a **value**. To store something in a dictionary, we must provide a unique **key** for each value. If we provide a key that is already in use, the value stored by that key is overwritten. Then, to retrieve a value, we simply provide the key that is associated with that value. 

This is very similar to how lists work, where each element in the list can be accessed using a list index. The biggest difference is that keys in a map can be _any_ value, not just an integer, and likewise the values can be _any_ type of value. 

{{% notice info "Not Everything Can Be a Key" %}}

Some types of objects cannot be used as keys.  Lists and Dictionaries cannot be used as keys. Pretty much any type where you can assign by index cannot be used as a key. If you can go `x[0] = ...` it is out.

{{% /notice %}}

In Python, dictionaries are another example of a collection that is included directly in the language.

Dictionaries are generally used when:
* the number of entries in the dictionary is not fixed 
* the programmer wants indexes which are not integers
* integer indexes may have gaps-- 1,2 and 7 all have values and 3-6 do not exists
* programmer does not care what order Python stores the elements .. i.e. don't care what order elements appear in a for-loop^[In Python they will appear in the order they are added to the dictionary in Python 3.6 & 3.7 but that is not guaranteed in later versions].


## Creating a Dictionary

To create a dictionary, we can simply declare it using curly brackets `{}`, either containing a set of keys and elements to be included or an empty set of brackets to create an empty dictionary:

```python
# empty dictionary
dict1 = {}

# dictionary with some items
dict2 = {"one" : 1, "two": 2, "three": 3}
```

That's all there is to it!

## Accessing Elements

Elements in a dictionary can be accessed and updated by providing the key in square brackets:

```python
# dictionary with some items
dict2 = {"one" : 1, "two": 2, "three": 3}

x = dict2["one"]
print(x) # 1

dict2["two"] = 5
print(dict2["two"]) # 5
```
## Dictionary Operations

The `dict` data type in Python defines several operations that it can perform. The full list can be found on the [Data Structures](https://docs.python.org/3/tutorial/datastructures.html) page of the Python documentation. Here are a few of the most important ones:

* `dict.get(k)`---return the value associated with the key `k` in the dictionary
* `len(dict)`---returns the number of key and value associations in the dictionary `dict`
* `k in dict`---returns `True` if the dictionary contains an associated value for the given key `k`
* `dict.pop(k)`---removes the key `k` and its associated value from the dictionary

## Iterating

What if we want to iterate through a dictionary? That is a bit tricky, but it can be done. To do this, we'll use a **for each** loop. The code for doing this is shown here:

```python
dict_iter = {"One":"Uno", "Two":"Dos", "Three":"Tres", "Four":"Quatro"}

for key in dict_iter:
  print("Key: {}".format(key))
  print("Value: {}".format(dict_iter[key]))
```

However, in most cases, it doesn't make much sense to iterate through a dictionary, since that isn't what it is designed for. Instead, we may want to consider using some sort of a list instead. 

## Example

To explore how to use a dictionary in a real program, let's look at a quick example program. Here's a short problem statement:

> Write a program that will read multiple lines of input from the terminal.  The program should terminate if a blank line is entered.

> The program will store a dictionary that associates lines of input with random integers.

> When a line of input is read, the program will check to see if that line has already been used as a key in the dictionary. If so, it will return the value associated with that key.

> If the dictionary does not contain an entry for that key, the program should generate a new random integer and store it in the dictionary, using the input line as the key. 

> The program should be implemented as two methods - a `main()` method that handles reading input, and a `getOutput()` method that accepts a string as a parameter and returns the associated number for that string. It should also use a global variable to store the dictionary. 

For example, let's say the program receives the following input:

```tex
cat
dog
horse
dog
cat
```

One possible output could be:

```
12334512345
239487234
234234
239487234
12334512345
```

Notice that the lines of output correspond with the lines of input, such that the program returns the same value each time it reads the word `cat`. 

### `main` Method

So, let's build the program. We can start with this simple skeleton:

```python
import sys
import random

class DictExample:

    dictionary = {}

    @staticmethod
    def main(args):
        reader = sys.stdin
        line = "test"
        while len(line.strip()) > 0: 
            line = reader.readline()
            if len(line.strip())>0:
                output = DictExample.get_output(line)
                print(output)

  def get_output(line):
    # MORE CODE GOES HERE
     
# main guard
if __name__ == "__main__":
  DictExample.main(sys.argv)
```

This program contains a simple `main()` method that will handle reading and parsing the input. When it reads a line of input, it will use the 
`get_output()` method to get the associated output for that input, and then print it to the terminal.

The program also includes a class attribute to store the dictionary. In that way, we can use the same object in both methods without having to pass it around as an argument. 

So, all we need to worry about implementing is the `get_output()` method.

### `get_output` Method

{{% youtube UAawcVBZgXc %}}

[Video Materials]({{<relref "./video">}})

<!-- TODO Update Video -->

<p style="color:red; padding:10"><b>Note:</b> video unnecessarily marks the method `get output` as static method.  We will follow the convention that only the start-up 'main' method shall be static.</p>

Let's dive into the `get_output()` method. First, we'll need to see if the dictionary contains a value for the string provided as input. If so, we can just return that value:

```python

def get_output(line):
  if line in DictExample.dictionary:
    return DictExample.dictionary[line]
```

However, if the dictionary does not contain a value for that key, we must generate a new one, store it in the dictionary, then return it:

```python

def get_output(line):
  if line in DictExample.dictionary:
    return DictExample.dictionary[line]
  else:
    new_number = random.randint(-1000000, 1000000)
    DictExample.dictionary[line] = new_number
    return new_number
```

That's all there is to it! See if you can complete the code in `DictExample.py` to the left, then use the two assessments below to check your program.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}
