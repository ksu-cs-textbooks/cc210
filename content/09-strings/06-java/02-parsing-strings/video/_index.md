---
title: "Java Parsing"
pre: "2.J. "
weight: 20
date: 2019-09-09T00:00:26-05:00
hidden: true
---

{{< youtube kBbqnMUddKs >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

Let's look at a couple of different ways we can read input strings in Java, cut them up into individual parts or "tokens", and then convert and store those "tokens" in the correct data types.

First, for all of these examples, we're going to start with the same skeleton code for reading input that we've been using thus far in this book. We'll create a Scanner object, and it will read input either from a file provided as a command-line argument, or directly from the terminal if no input file is given.

The first process we'll explore for handling string input is using the built-in methods of the Scanner object to read and convert the individual parts of our input. Here's a next example. Let's assume that our program is going to read the text given in the first box: `"1 This 2.0 is true"` using the code given in the second box. How would that work?

First, we need to read an integer. So, the first line uses the `nextInt()` method of the Scanner object to read the next token from the input and convert it to a integer. The Scanner object assumes that each token is separated by one or more whitespace characters, so any number or combinations of spaces, tabs, and newlines can be used to "delimit" or separate the tokens of input. In this example, that means that the first line of code will read the "1" from input. Then, it will convert it to an integer, and store it in the variable `x`.

Next, we'll be reading the string `"This"` from input. Since it is just a string, we can use the `next()` method of the Scanner object to get the next token as a string, without any conversion. So, once again, we'll read the next token, and then store it in the variable `s1`.

After that, our program will need to read a floating-point value from input. So, we'll use the `nextDouble()` method of the Scanner object to read and convert the next token to a double. It reads the string `"2.0"`, then stores the value 2.0 in the variable `d`.

Next, we'll read another string. So, we'll use the `next()` method once again to read the string `"is"` from input and store it in `s2`.

Finally, we'll need to read a Boolean value. For this, we'll use the `nextBoolean()` method in the Scanner object. It will read the string `"true"` from input and then convert it to the Boolean value `true` before storing it in the variable `b`. So, as we can see, it is easy to use the built-in methods of the Scanner object to read and convert tokens of input, provided we know what the format of the input will be.

What if we try to provide input that doesn't fit our expected format? Let's back up a step in our code, and consider the input `"1 This 2.0 is not true"`. In this case, we'll be reading the token `"not"` using the `nextBoolean()` method. Obviously, the text `"not"` does not correspond to either of the valid Boolean values. So, when we try to convert that value, our Java program will throw an `InputMismatchException` and stop executing. Therefore, we'll need to be very careful and make sure our code and the input match up. Otherwise, we'll get errors like this. In a later chapter, we'll learn how to handle these exceptions so they don't crash our program. But, for now, we'll just have to trust our users to provide the correct inputs.

Let's look at another way we can handle string inputs in our program. This time we'll use the `split()` method in the String data type to split a string into separate tokens. Then, we'll use the various methods to parse a string into each data type before storing those values. For this example, we'll use a two-line input, with `"This 1"` on the first line, and `"2.0 true"` on the second line.

In the code, we see the first line is using the `nextLine()` method of the Scanner object to read an entire line of input and store it in to a string variable. So, after that line executes, the variable `line1` stores the string `"This 1"`.

Next, we can use the `split()` method to split the string stored in `line1` into an array of strings, each one being a token from the original string. Notice that we have provided a single space `" "` as input to the `split()` method, which tells the method that we want to use the space character as the delimiter between each token. In the text, we describe how this works in more detail, since it is actually a regular expression and not just a simple list of delimiters. So, after this line, we have a new variable `line1parts` that contains an array of two strings, `"This"` and `"1"`.

Finally, we can store those array elements in separate variables if we so choose. On the third line, we are storing the first element into its own string variable `s1`. However, in the fourth line, we want to store the second array element as an integer. To do that, we must use the `Integer.parseInt()` method to convert a string representing a number into an integer. Inside of that method, notice that we are providing the second array element as input. So, the input to that function is actually the second token of our original input, which is the string `"1"`. Therefore, the variable `x` stores the value 1 once it has been converted to an integer.

The second four lines of code work in a similar way. The first two lines will read the next line of input, and then split it into an array of strings, with each element in the array containing a token from the original input.

Once again, the third line of input will read the first element in the array and store it into a variable with the double data type. So, we must use the `Double.parseDouble()` method, just like we used the `Integer.parseInt()` method earlier. We provide the array element as input, and then the method converts that string to a double value, storing 2.0 in the variable `d`.

Finally, we can do the same with the Boolean value stored in the second array element, using the `Boolean.parseBoolean()` method.

Each of these methods of reading, converting, and storing string input works in a very similar way. Depending on the structure of the input being provided, sometimes one method is a bit simpler than the other, but each one works in pretty much any case.
