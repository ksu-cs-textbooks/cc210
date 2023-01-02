---
title: "Parsing Strings"
pre: "2. "
weight: 20
---

{{% youtube 4O-eLkzD50s %}}

[Video Materials]({{<relref "./video">}})

In many programs, we'll be reading input from the user into a string variable, and then parsing that input into the various data types we need. So, we'll need to understand how to parse strings in Python. Thankfully, there are a couple of approaches we can use. 

## Keyboard Input Reminders

For the code 

```python
reader =  sys,stdin
s1 = readline()
```
If we type " The mind once enlightened cannot again become dark &crarr;". s1 is ` The mind once enlightened cannot again become dark\n`.  

```python
 s2 = s1.strip()
```
Using the `.strip()` method of the string class, s2 is `The mind once enlightened cannot again become dark`.  `strip()` removes all leading and trailing so called 'white space'^[spaces, tabs, returns ... or string characters that cause  the cursor position to shift but nothing to be printed ... leaving "white space" of the printed page].

If we just hit enter ("&crarr;"), the  s1 is `\n` and s2 is `''`, the empty string.


## Tokenization

As we've already seen, Python includes methods to convert an entire string into a particular data type. Each of those methods uses the name of the data type we'd like to convert to, as in this example:

```python
s1 = "123"
x = int(s1)  # 123

s2 = "1.23"
f = float(s2) # 1.23

s3 = "True";
b = bool(s3);  # True
```

As we can see here, we can easily convert an entire string to a different data type. 

However, when we try to convert a string that contains more than one item, or if the string cannot be converted to the data type specified, we will get an error. Consider these examples:

```python
s1 = "1.23"
x = int(s1)
```

When we run that code, we'll get the following error:

```tex
Traceback (most recent call last):
  File "7p-strings/Strings.py", line 16, in <module>
    x = int(s1)
ValueError: invalid literal for int() with base 10: '1.23'
```

In this case, a "ValueError" error tells us that the string we are trying to parse does not match the format expected for the data type we'd like to store it in. Again, we'll learn how to handle these errors in a later chapter, but for now we'll just have to trust our users to input correct data.

We'll receive a similar error when we run this code:

```python
s2 = "1.23 3.45"
f = float(s2)
```

In this case, the string `s2` contains more than one element, so it will also not match the format of a floating point number. So, we'll get an error.  

### Split

What we need to be able to do is make tokens, or smaller fragments, from the input string. 


For example, let's say we'd like to parse the following input from the user:

```tex
This 1
2.0 true
```

We'll assume that we've already created our `reader` variable using the skeleton code given above. So, to parse this input, we could use the following code

```python
line1 = reader.readline()
line1Parts = line1.split(" ")
s1 = line1Parts[0]
x = int(line1Parts[1])

line2 = reader.readline()
line2Parts = line2.split(" ")
f = float(line2Parts[0])
b = bool(line2Parts[1])
```

Let's go through this code and see how it works. First, we read a single line of input from the user using the `reader.readline()` method. Then, we split that line into individual parts using the `split()` method of the string variable `line1`. In the call to the split method, we need to give the string that we'd like to use as our _delimiter_. So, in this case, we'll just provide a string that contains a single space to use the space character as our delimiter. 

The invoking the string method `split()` on `line1` will create a list of strings which we assign to `line1Parts`.  This list will  will contain two elements. In this case, the first element will be "This" and the second element will be "1". 

So, we can store the first element into the string variable `s1` directly. However, we'll need to use the `int()` method to convert the string stored in the second element of `line1Parts` to an integer before we can store it in `x`. 

The next few lines of code will read another line of input, then split it, and then convert the two parts into a floating point number and a boolean value, respectively. 

{{% notice info "String.split() and Delimiters" %}}

The Python `split()` method can also split on a delimiter containing multiple characters, as in this example:

```python
s = "This<>is<>good"
parts = s.split("<>"); # {"This", "is", "good"}
```

However, if multiple delimiters are found consecutively in the string, Python will add an empty string to the list between each set of consecutive delimiters:

```python
s = "This,is,,good"
parts = s.split(","); # {"This", "is", "", "good"}
```

You can read more about how Python's `split()` method works here:

[Python 3 str.split()](https://docs.python.org/3/library/stdtypes.html#str.split)

{{% /notice %}}

## Reading an Indefinite Number of Lines from the Keyboard

When reading from the terminal, we'll never actually know when the input ends. So, it is a good practice to also check and see if the user provided an empty line as input, or tell the user some other way to mark the end of input. An "empty line" is one where just the enter key is input.

Here's a great way to handle this situation in Python:

```python
line = reader.readline().rstrip('\n')  
while len(line) != 0: 
    <body of loop>  # parse the input
    line = reader.readline().rstrip('n') # last line in loop, try to get next input

```

In this case, the program reads the first user input and enters the loop unless the user enters a blank line. If the user enters a blank line:
1. `reader.readline()` returns the string '\n'
2.  `.rstrip('\n')` strips the new-line character from the right^[see <a href="https://docs.python.org/3/library/stdtypes.html">Python Docs</a> for a better discussion of rstrip() ] leaving the empty string ("")^[This allows the user to have blank-lines by entering a space (" \n".rstrip('\n') returns a space (" "))]
3.  the len() of the empty string is 0

The last line of the loop body is reading the next user input.  This way, the program will continue read input from the user until the user enters an empty. The len() of the empty string is 0.


## Practice

Let's take a minute to get some practice parsing strings of input for our programs.

Complete 'StringParsing.py' to meet the following problem statement:

> Write a program that can find the sum of an undetermined number of inputs provided on two lines. The first line of input will contain one or more integers, separated by spaces. The second line of input will contain one or more floating point numbers, separated by commas. The program should output the sum of all inputs provided. 

So, for example, if our program receives the following input:

```tex
1 2 3 4 5
1.25,2.5,3.75
```

we should print out "22.5" as the result. 

Assuming we already have our skeleton code, we can quickly work through this problem statement. First, we'll need to read a line of input and split it using the space character as our delimiter:

```python
input = reader.readline()
splits = input.split(" ")
```

That's simple enough. Now, since we don't know how many inputs might have been provided, we'll have to use a **For** loop to iterate over the inputs:

```python
input = reader.readline()
splits = input.split(" ")

for s in splits:

```

Then, inside of the **For** loop, we can just parse each input as an integer and then add it to a sum variable. We'll set that variable to 0.0 initially:

```python
input = reader.readline()
splits = input.split(" ")

sum = 0.0

for s in splits:
  sum += int(s)
```

Next, we can read the next line of input from the user, and then split it using a comma as a delimiter. 

```python
input = reader.readline()
splits = input.split(" ")

sum = 0.0

for s in splits:
  sum += int(s)

input = reader.readline()
splits = input.split(",")
```

Notice that we are able to reuse the variables `input` and `splits` here. This is handy, so we only have to manage one set of variables as we parse multiple lines of input.

Finally, we can use another **For** loop to iterate across the second set of inputs, parse them into a floating point value, and then add them to the sum variable. Finally, at the end, we'll print out the value of the `sum` variable.

```python
input = reader.readline()
splits = input.split(" ")

sum = 0.0

for s in splits:
  sum += int(s)

input = reader.readline()
splits = input.split(",")

for s in splits:
  sum += float(s)

print(sum)
```

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

