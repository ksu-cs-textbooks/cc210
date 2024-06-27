---
title: "Characters and Strings"
pre: "1. "
weight: 10
date: 2019-09-09T00:00:26-05:00
hidden: true
---

{{< youtube ur4m3QjbBHE >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

To understand how a computer handles text, we have to take a step back and recall how our computer stores data. As we saw in an earlier chapter, all data in a computer is stored in a binary format. Here we have the number 1 0 0 0   0 0 0 1. Our computer can store that binary value as data, and then we can use the data type of that value in our programs to tell the computer how to interpret that binary number.

For example, if the data type of the variable storing that value is an integer, the computer would know that the binary value represents the decimal number 65.

To convert a binary value to text, our computer uses a system called the American Standard Code for Information Interchange, or ASCII (pronounced az-skee). This table gives a list of all of the characters available in ASCII, as well as the corresponding decimal value. So, on this table, we see that the decimal value 65 corresponds to the character `'A'`. Therefore, the binary value 1000 0001 can also represent the letter `'A'` in our programs, depending on the data type of the variable storing the value.

Of course, this only allows us to store one letter at a time. What if we want to store a whole word, or even a sentence, in our programs? To do that, we can use what we learned about arrays in the previous chapter. For example, assume we have an array containing 4 numbers - 65, 66, 67, and 68. As integers, our computer programs would interpret that array as these numbers. However, if we treat the same array as text, we can look up each number in the ASCII table and find the corresponding character. So, we end up with an array storing the letters `'A'`, `'B'`, `'C'`, and `'D'`.

Finally, there is a special data type we can use, called a string, that allows us to interpret these arrays of characters as a single word or sentence. So, that same binary data, when stored in a variable using the string data type, would represent the sentence `"ABCD"` in our program.

As we can see, our computer can interpret binary data as text quite easily, using the simple ASCII code to convert numerical data into individual letters or characters. From there, we can use arrays of those characters to represent longer pieces of text, including words, strings, and entire documents. In this chapter, we'll learn all about how to use strings of text in our programs.
