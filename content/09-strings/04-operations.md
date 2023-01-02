---
title: "String Operations"
pre: "4. "
weight: 40
---

We can also perform many different operations on strings in our programs. These operations allow us to search within strings, edit them, compare them, and more.

## Length

First, we can get the length of any string stored in our programs. From the example earlier:

![String Array](/images/09-string/7.2.stringarray.png)

This string has length 11, because it contains 11 characters. We must make sure we count the space as a character, as well as any punctuation or other symbols. Since the index of the last character is 10, we know that the length is 11, just as we saw when working with arrays.

## Comparison

We can also compare two strings to see if they are equal. Two equal strings would contain exactly the same characters in exactly the same order. So, we would say that "Hello" and "Hello" are equal, but "Hello" and "hello" are not. 

We can also use comparison operators to determine if one string comes before another _lexicographically_. This is similar to alphabetical order, but it also encompasses all of the other characters in either ASCII or Unicode and handles capitalization, sorting uppercase letters before lowercase letters

## Searching

There are also methods we can use to search within a string. For example, we could see if the string "Hello World" contains "lo" using a find method. We could even determine if a string starts with or ends with a particular sequence of characters. 

Finally, we can find the location of a character or sequence within a larger string. As an example, if we wanted to find the location of "lo" in "Hello World", our program would tell us that it begins at character 3. 

## "Modifying" Strings

In many programming languages, including Python and Java, strings are immutable--the values in the memory locations containing the string cannot be changed.  However there are many methods which provide new copies of old strings with modifications. These typically include methods to make a string entirely lowercase or uppercase, as well as a method to remove any extra whitespace from the beginning or end of a string. 

There are also methods to replace one character with another in a new string. So, we could replace all spaces in "Hello World" with commas, resulting in a new string "Hello,World". 

{{% notice info "Immutable Strings" %}}

Consider the scenario below:

![Immutable Strings](/images/09-string/immutable_strings.png)

1. On Line 2, calling the method `toUpperCase()` does not change the memory location holding `s`.  It provides a copy of the string, with all letters as capitals. But since this value is not captured in a variable, it never goes into the variable storage, and it is lost when the program moves to line 3.
1. Line 3 makes `t` an alias of `s`, they are two different variables referring to the same thing.
1. Line 4 reassigns `s` to the new string "HELLO"--but because strings are immutable, the memory space with "hello" **is not** reused (as it the case mutable data types).  Instead, a new memory location is used and s is redirected there.

{{% /notice %}}

## Substring

Finally, we can also get a substring from our original string. A substring is simply a consecutive portion of the original string. For example, if we want the substring from character 3 through character 7 of "Hello World", the result would be "lo Wo". So, we can get smaller parts of our original string using a method that creates a substring.

Later in this chapter we'll see how to use each of these methods in our chosen programming language. 



