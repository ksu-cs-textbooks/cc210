---
title: "String Operations"
pre: "3. "
weight: 30
---


{{% youtube oUS1rxBfano %}}

[Video Materials]({{<relref "./video">}})

The string data type includes many built-in operations that we can use to compare, manipulate, and search within strings. We'll cover several of them on this page, and we'll also include links at the bottom to additional resources where all of them are listed.

## Length

First and foremost is the `len()` built in function. It allows us to find the number of characters in a string. `len()` can actually be used to find the number of elements in any iterable aggregate data type.

```python
s = "This"
print(len(s)) # 4

t = "This \"is\" that"
print(len(t)) # 14
```

Notice that the second string, stored in variable `t`, only contains 14 characters. That is because `\"` only counts as a single character in the output, so it is stored as a single character in the string. The same applies to any of the special characters we've seen so far in this chapter.

## Comparison

Next, we can use the standard comparison operators in Python to compare two strings. First, we could use the `==` operator to determine if two strings are equal (meaning they contain exactly the same characters in the same order), as in this example:

```python
s1 = "This"
s2 = "This"
s3 = "this"

print(s1 == s2) # True
print(s1 == s3) # False
```

Similarly, we can use operators such as `<` and `>` to compare two strings and see which one should be placed first in lexicographic order. Consider this example:

```python
s1 = "This"
s2 = "That"

print(s1 < s2) # False
```

In this example, since "This" should come after "That" in the dictionary, the comparison `s1 < s2` will return `False`. These operators are very helpful when sorting strings, which we'll learn about in a later chapter.  Note that lowercase letters are "greater than" uppercase letters due to their ascii values.

## Concatenation

Another common string operation is _concatenation_, or joining two strings together. This operation is actually very simple!

In Python, we can use the `+` operator to concatenate any two strings together. However, if one of the operands is not a string, we must convert it using the `str()` conversion method. 

Here are a few examples:

```python
s1 = "This"
s2 = "That"
x = 42

s3 = s1 + s2
s4 = "" + str(x)

print(s3) # ThisThat
print(s4) # 42
```

## Searching Within Strings

Python also includes several methods that can be used to search within one string for another. We can even specify if we'd like to find the string at the beginning or the end of the string, and it includes methods to give us the location of the string we are searching for. Here's a great example of several of those methods in action:

```python
s1 = "abc123abc123"

print("123" in s1) # True
print("321" in s1) # False

print("123" not in s1) # False
print("321" not in s1) # True

print(s1.find("123")) # 3  (the index of the first character)
print(s1.find("321")) # -1 (it returns -1 if it can't find it)

print(s1.rfind("123")) # 9  (it returns the beginning of the last instance)
print(s1.rfind("321")) # -1 (it returns -1 if it can't find it)

print(s1.startswith("abc")) # True
print(s1.startswith("123")) # False

print(s1.endswith("abc")); # False
print(s1.endswith("123")); # True
```

## Manipulating Strings

Finally, Python includes methods that can be used to manipulate strings in unique ways. It is important to remember that none of these methods modify the original string, so we'll need to store the result back in a string variable in order to use it. In these examples, we'll just print the output so we can see the result:

```python
s1 = "abc123abc123"

# replace takes two strings as input, and replaces all 
# instances of the first string with the second
print(s1.replace("b", " ")) # a c123a c123

# Strings in Python can also be spliced just like lists
# It will return all characters starting at the first index up to
# but not including the second index
print(s1[3:9]) # 123abc

s2 = "UPPERlower"

print(s2.lower()) # upperlower
print(s2.upper()) # UPPERLOWER

s3 = "  \t Some String  \n \n "

# strip removes all whitespace characters from the beginning
# and end of the string, including special characters
# such as newlines and tabs. 
s4 = s3.strip()
    
print(s4) # Some String
print(len(s4)) # 11
```

In Python, we can also get a single character from a string using the same syntax we used for lists. This is similar to getting a substring of length 1 using the slice operator:

```python
s1 = "abc123"

c1 = s1[0]
c2 = s1[5]

print(c1) # a
print(c2) # 3
```

This is just a small list of the many operations that can be performed on strings in Python. For more information, consult the official Python documentation linked below.

### References

[Python Built-In Types: str](https://docs.python.org/3/library/stdtypes.html#text-sequence-type-str)
[Python Common String Operations](https://docs.python.org/3/library/string.html)