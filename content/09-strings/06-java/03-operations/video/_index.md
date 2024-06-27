---
title: "Java String Operations"
pre: "3.J. "
weight: 30
date: 2019-09-09T00:00:26-05:00
hidden: true
---

{{< youtube k4-RnL5niK4 >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

Let's take a look at a few of the more common operations we can perform on strings in our programs. First off, one of the most important operations we can perform on a string is to find the length, or number of characters, contained in the string. Consider the example shown on this slide. The first string, `"This"` is a pretty simple example. Let's color each character in an alternating shade, just to make it easier to count them. As we can easily see, the string `"This"` contains exactly 4 characters.

However, things are a bit different in the second string. Let's use our coloring trick once again. In this case, we have a few special characters contained in the string. Those special characters only count as one character in the string, even though they are displayed as two characters here. That is because the slashes are not actually included in the string itself; they are just there to tell us that the quotation marks should be included in the string. So, if we carefully count the characters, we see that this string contains 14.

We may also want to compare two strings to see if they contain the same characters. In this example, we have three different strings. Below, we see a couple of lines comparing each string using a double equals sign. Will that work?

Unfortunately, in Java, we cannot use a double equals sign to determine if two strings contain the same characters. Instead, it will only check to see if two variables contain the exact same string object. The textbook has a good example of what that actually means.

So, instead of using a double equals sign, how can we check if two strings contain the same characters? We can use the `equals()` method! In this example, we are checking to see if the first string is equal to one of the other strings. In this case, the `equals()` method will return the correct answer, so we will find that `s1` and `s2` contain the same characters, but `s1` and `s3` do not.

Additionally, we may want to see if one string should come before or after another string lexicographically. This is similar to asking if a string comes before or after another alphabetically, but it also takes into account capitalization and punctuation as well. So, in this example, we are testing to see if `s1 < s2` in our **IF** statement. Will this work?

Once again, it doesn't work the way we think it should. Instead, we should use the `compareTo()` method. If we want to find out if `s1` comes before `s2`, we use the same less than sign, but check to see if the result of the method is less than 0. This is because the `compareTo()` method will return a value less than 0 if the first string comes first, or a value greater than 0 if the second string comes first. Finally, it will even return 0 if they are exactly the same.

We can also concatenate strings together using the plus `+` symbol. In Java, the plus symbol has special rules: if one of the operands is a string, it will perform string concatenation on both operands, and even convert primitive data types to a string if needed. So, in the first line, we see that strings `s1` and `s2` are being concatenated, resulting in `ThisThat` as output.

In the second line, we see that we are concatenating an empty string with an integer. In this case, the integer will automatically be converted to a string, and then the result will be `"42"` as a string. This is a neat shortcut to convert any primitive data type to a string, and even works with many other data types as well.

Finally, the textbook demonstrates how to use several other methods for searching within a string, or even manipulating the characters in a string. We'll get plenty of experience working with many of these methods in the examples later in this chapter.
