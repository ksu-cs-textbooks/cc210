---
title: "Parsing Strings"
pre: "3. "
weight: 30
---

One of the most common things our programs will do with strings is use them to collect data from the user. When we do, we'll need to _parse_ the data in the string into a format our computer can recognize.

Parsing typically involves two steps: tokenization and conversion.

## Tokenizing Strings

The first step in parsing a string is to _tokenize_ the string, or separate it into its individual elements. For example, let's say we want our user to be able to input two numbers, representing the coordinates of a square in Tic-Tac-Toe. So, we could prompt the user to input those two numbers on the same line, separated by a single space, like this:

```tex
2 1
```

When we read that line of input from the user, we'll create a string variable that stores `"2 1"`. So, we want to be able to separate that string into two parts, representing each number.

Most programming languages include a method to _split_ a string into parts, using a specific character as a _delimiter_, marking where one part ends and another begins. In many cases, we'll use the space character as the delimiter, but sometimes we'll use other characters such as the comma or semicolon as well.

So, once we split the string, we'll have an array of strings that stores `{"2", "1"}`, with each element representing a part of the string. That's the first step.

## Converting Strings

Once we've split our string into parts, we may need to convert the strings to another data type, such as integers or floating point values. Thankfully, each programming language includes a variety of methods we can use to convert to and from strings and other data types. We'll see how to do that in our chosen programming language later in this chapter. 

