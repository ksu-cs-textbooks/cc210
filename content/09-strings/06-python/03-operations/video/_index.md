---
title: "Python String Operations"
pre: "3.P. "
weight: 31
date: 2019-09-09T00:00:26-05:00
hidden: true
---

{{< youtube oUS1rxBfano >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

Let's take a look at a few of the more common operations we can perform on strings in our programs. First off, one of the most important operations we can perform on a string is to find the length, or number of characters, contained in the string. Consider the example shown on this slide. The first string, `"This"` is a pretty simple example. Let's color each character in an alternating shade, just to make it easier to count them. As we can easily see, the string `"This"` contains exactly 4 characters.

However, things are a bit different in the second string. Let's use our coloring trick once again. In this case, we have a few special characters contained in the string. Those special characters only count as one character in the string, even though they are displayed as two characters here. That is because the slashes are not actually included in the string itself; they are just there to tell us that the quotation marks should be included in the string. So, if we carefully count the characters, we see that this string contains 14.

We may also want to compare two strings to see if they contain the same characters. In this example, we have three different strings. Below, we see a couple of lines comparing each string using a double equals sign. Will that work?

It sure will! The Python programming language helpfully allows us to use the double equals sign to determine if two strings contain the same characters. So, it is really simple to find out that strings `s1` and `s2` are the same, while strings `s1` and `s3` are not.

Additionally, we may want to see if one string should come before or after another string lexicographically. This is similar to asking if a string comes before or after another alphabetically, but it also takes into account capitalization and punctuation as well. So, in this example, we are testing to see if `s1 < s2` in our **IF** statement. Will this work?

Once again, in Python, this comparison works exactly as expected. Since `s2` comes before `s1`, the **else** branch will be executed.

We can also concatenate strings together using the plus `+` symbol. In Python, the plus symbol has special rules: if one of the operands is a string, it will perform string concatenation on both operands. So, in the first line, we see that strings `s1` and `s2` are being concatenated, resulting in `ThisThat` as output.

In the second line, we see that we are concatenating an empty string with an integer. In this case, we'll need to manually convert any primitive data types to a string, or else we'll get a `TypeError`. If we do, the result will be `"42"` as a string. Unfortunately, Python will not automatically convert primitive data types to a string, so we'll have to remember to do that manually anytime we want to use them as part of a string.

Finally, the textbook demonstrates how to use several other methods for searching within a string, or even manipulating the characters in a string. We'll get plenty of experience working with many of these methods in the examples later in this chapter.
