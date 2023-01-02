---
title: "Making Strings"
pre: "1. "
weight: 10
---

String variables in Python can be created just like any other variable type we've seen so far. To initialize a string variable, we can use the following syntax:

```python
s = "This is a string!"
```

The text itself should be placed in double quotation marks as seen in this example. This allows the Python interpreter determine what part of the source code file should be treated as text instead of code. 

{{% notice info "Special Characters" %}}

Python supports several special characters that can use in our strings to represent specific symbols. For example, we know that strings must be surrounded by double quotation marks. So, what if we want to include quotation marks in our string? 

We can use `\"` as a special character to represent a double quote in our string. Here's an example:

```python
s = "This is \"a quote\""
print(s)
```

This code segment would produce the following output:

```tex
This is "a quote"
```

There are several special characters we can include in our strings. Here are a few of the more common ones:
* `\'` - Single Quotation Mark (required if the string is within single quotation marks)
* `\"` - Double Quotation Mark (required if the string is within double quotation marks)
* `\n` - New Line
* `\t` - Tab
* `\\` - The backslash

Recall that a Python string can be delimited by either `''` or `""`.  We recommend use use `""` because the single quote is also used in English for possessive and contractions.

{{% /notice %}}

Python does not include a separate data type for characters. Instead, "characters" in Python are really just strings with a length of 1:

```python
c = "a";
```

Behind the scenes, Python refers to the string data type as `str`. We've already seen the use of the `str()` method to convert other data types into strings. 


### Reference

[Python Strings](https://docs.python.org/3/library/stdtypes.html#text-sequence-type-str)