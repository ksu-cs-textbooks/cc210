---
title: "Python Parsing"
pre: "2.P. "
weight: 21
date: 2019-09-09T00:00:26-05:00
hidden: true
---

{{< youtube 4O-eLkzD50s >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

Let's look at a couple of different ways we can read input strings in Python, cut them up into individual parts or "tokens", and then convert and store those "tokens" in the correct data types.

First, for all of these examples, we're going to start with the same skeleton code for reading input that we've been using thus far in this book. We'll create a reader, and it will read input either from a file provided as a command-line argument, or directly from the terminal if no input file is given.

The first process we'll explore for handling string input is using the built-in methods of the reader to read individual lines of input, and then convert them to the proper data types. Here's a next example. Let's assume that our program is going to read the text given in the first box: `"1 This 2.0 is true"` using the code given in the second box. How would that work?

First, we need to read an integer. So, the first line uses the `readline()` method of the reader to read the next line from the input. Then, it will convert it to an integer using the built-in `int()` method, and store it in the variable `x`.

Next, we'll be reading the string `"This"` from input. Since it is just a string, we can use the `readline()` method of the reader to get the next line as a string, without any conversion. So, once again, we'll read the next token, and then store it in the variable `s1`.

After that, our program will need to read a floating-point value from input. So, we'll use the `readline()` method of the reader to read the next line of input, and then use the `float()` method to convert that string to a floating-point value. It reads the string `"2.0"`, then stores the value 2.0 in the variable `d`.

Next, we'll read another string. So, we'll use the `next()` method once again to read the string `"is"` from input and store it in `s2`.

Finally, we'll need to read another string. This string contains multiple tokens, but they are both on the same line of input. So, using the `readline()` method of the reader will read the entire line, storing the string `"is true"` in the variable `s2`.

What if we try to provide input that doesn't fit our expected format? Let's back up a couple of steps in our code, and consider the input `"1 This is 2.0"`. In this case, we'll be reading the line `"is"` using the `readline()` method. Obviously, the text `"is"` does not correspond to a valid floating-point value. So, when we try to convert that value, our Python program will throw a `ValueError` and stop executing. Therefore, we'll need to be very careful and make sure our code and the input match up. Otherwise, we'll get errors like this. In a later chapter, we'll learn how to handle these exceptions so they don't crash our program. But, for now, we'll just have to trust our users to provide the correct inputs.

Let's look at another way we can handle string inputs in our program. This time we'll use the `split()` method in the string data type to split a string into separate tokens. Then, we'll use the various methods to parse a string into each data type before storing those values. For this example, we'll use a two-line input, with `"This 1"` on the first line, and `"2.0 true"` on the second line.

In the code, we see the first line is using the `readline()` method of the reader to read an entire line of input and store it in to a string variable. So, after that line executes, the variable `line1` stores the string `"This 1"`.

Next, we can use the `split()` method to split the string stored in `line1` into a list of strings, each one being a token from the original string. Notice that we have provided a single space `" "` as input to the `split()` method, which tells the method that we want to use the space character as the delimiter between each token. In the text, we describe how this works in more detail, since we can provide more complex input as a delimiter, too. So, after this line, we have a new variable `line1parts` that contains a list of two strings, `"This"` and `"1"`.

Finally, we can store those list elements in separate variables if we so choose. On the third line, we are storing the first element into its own string variable `s1`. However, in the fourth line, we want to store the second list element as an integer. To do that, we must use the `int()` method to convert a string representing a number into an integer. Inside of that method, notice that we are providing the second list element as input. So, the input to that function is actually the second token of our original input, which is the string `"1"`. Therefore, the variable `x` stores the value 1 once it has been converted to an integer.

The second four lines of code work in a similar way. The first two lines will read the next line of input, and then split it into a list of strings, with each element in the list containing a token from the original input.

Once again, the third line of input will read the first element in the list and store it into a variable with the double data type. So, we must use the `float()` method, just like we used the `int()` method earlier. We provide the list element as input, and then the method converts that string to a double value, storing 2.0 in the variable `d`.

Finally, we can do the same with the Boolean value stored in the second list element, using the `bool()` method.

Each of these methods of reading, converting, and storing string input works in a very similar way. Depending on the structure of the input being provided, sometimes one method is a bit simpler than the other, but each one works in pretty much any case.
