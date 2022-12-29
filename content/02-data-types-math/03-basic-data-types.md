---
title: "Basic Data Types"
pre: "3. "
weight: 30
---

In a computer, all data, even the instructions, is stored in a _binary_ format. Binary data consist entirely of 1s and 0s, or, in the case of a computer, it could be represented as "on" and "off" for current in a circuit, or "positive" and "negative" charges stored on a magnetic storage device. It could even be "open" and "closed" for physical memory gates. There are many different ways to represent it, but it all boils down to just 1s and 0s.

Of course, we need a way to convert between the binary 1s and 0s that a computer understands and the actual data we'd like to represent. On this page, we'll cover some of the common types of data and how they are handled by most computer programming languages.

{{% notice note "Binary" %}}

Working with binary data can be a complex topic. In this program, we won't deal directly with binary data very often. If you'd like to learn more about the binary numerical system and how it works, check out the Wikipedia article on [Binary Numbers](https://en.wikipedia.org/wiki/Binary_number).

You may also want to review the [List of Types of Numbers](https://en.wikipedia.org/wiki/List_of_types_of_numbers) article as well, since we'll refer to several of those types. 

Binary literals are  often prepended with `0b`  thus `10` represents the decimal number 10, whereas `0b10` represents the binary number 10 and the decimal number 2. Recall that a literal represents the actual typed value.

{{% /notice %}}

## Common Numerical data

Numbers, and thus numerical literals, are used everywhere in computer programs.  This goes beyond obvious arithmetic and accounting applications.  Modern graphics, artificial intelligence and simulation programs use numerical representations of data to quickly perform their operations.  Thus, it is unsurprising that there are many ways to write and store numeric data.  

### Integers

The first type of data we'll deal with in our computer program is _whole numbers_. These are numbers such as 1, 0, -1, 25, -186, 12852, and more. In both mathematics and programming, we refer to these numbers as _integers_. An _integer_ is any whole number, or a real number without a fraction or decimal component. We sometimes refer to these numbers as _counting numbers_. 

To store these numbers in our computer program, we typically use a _signed integer_ data type. This data type allows us to store both positive and negative numbers in binary in our computer's memory. We won't go too far into the details of how that works in this course, but there is more information on how that works on [Wikipedia](https://en.wikipedia.org/wiki/Two%27s_complement)

### Floating Point

Next, we'll also need to handle numbers that include a fraction or decimal component. These include _rational numbers_ such as 1.5, -2.98, 3 1/3, and even _irrational numbers_ such as {{< math >}}$ e ${{< /math >}} and {{< math >}}$ \pi ${{< /math >}}. 

Our computer uses a special representation known as _floating point_ to store these numbers. Floating point is very similar to _scientific notation_, where a number such as 1,230,000 is represented as {{< math >}}$ 1.23 * 10^{6} ${{< /math >}}. In this example, 1.23 is the _significand_ and 6 is the _exponent_ of the number. It is known as floating point because the decimal point "floats around" the number based on the exponent. We could represent the same number as {{< math >}}$ 12.3 * 10^{5} ${{< /math >}} or {{< math >}}$ 0.123 * 10^{7} ${{< /math >}} just by adjusting the exponent, causing the decimal point to move within the significand.

Modern computers use the [IEEE 754](https://en.wikipedia.org/wiki/IEEE_754) standard for encoding floating-point numbers into binary. Again, we won't go into the specifics here, but the graphic below gives us a good idea of how a floating point number can be broken up and stored in binary.

![Double Precision Floating Point](/images/02-data/2.3.double.wikimedia.svg)[^1]

[^1]: File:IEEE 754 Double Floating Point Format.svg. (2015, January 21). Wikimedia Commons, the free media repository. Retrieved 20:50, December 18, 2018 from https://commons.wikimedia.org/w/index.php?title=File:IEEE_754_Double_Floating_Point_Format.svg&oldid=147276375.

Here we can see that a 64 bit space in memory is divided into three parts, one for the sign (to denote either a positive or negative number), another for the exponent, and a third for the fraction or significand of the number.

{{% notice warning "Floating Points are Approximations" %}}

Just like there are rational numbers (such as 1/3) which cannot be exactly represented in the base 10 decimal number system, there are numbers which cannot be exactly exactly represented in base 2 (the underlying binary system used by you computer).  In fact, there are many more rational numbers that cannot be exactly represented by binary numbers (hence floats) than there are in a base 10 system.

In addition to this, because floats have a finite (set) number of bits, there is a limit to the number of significant bits you can count on (typically 16 for a 64-bit float).  This is generally only a concern in scientific computing (where you deal with either very big or very small numbers).  However, many programs use common graphic processing units, which use only 32-bits (7 significant digits) to speed up calculations.  This much lower accuracy can cause problems with statistical simulations.

{{% /notice %}}

## Boolean

_Boolean_ values, named for [George Boole](https://en.wikipedia.org/wiki/George_Boole) represent `true` and `false` in a computer program. While it may be as simple as storing a single bit, with 0 and 1 representing `true` and `false`, most programming languages provide a special way to deal with these values as they are very important in our computer programs. We'll spend most of the next several chapters discussing how to work with Boolean values, but for now they are just another type of data our program could store.

## Text as Data

### Character

Many high-level programming languages have a character data type. A _character_ represents a single letter in a written language such as English. Most programming languages use a special code called [ASCII](https://en.wikipedia.org/wiki/ASCII), or the American Standard Code for Information Interchange. It defines a numerical value for each character in the English language, as well as several special characters such as the newline or `\n` character we've already seen. Below is a table showing the entire ASCII code.

![ASCII Table](/images/02-data/2.3.ascii.wikimedia.svg)[^2]

[^2]: File:ASCII-Table-wide.svg. (2018, March 6). Wikimedia Commons, the free media repository. Retrieved 21:51, December 18, 2018 from https://commons.wikimedia.org/w/index.php?title=File:ASCII-Table-wide.svg&oldid=291044172.

So, to store the character `c`, our computer would store the number 99 in binary. We should also notice that the capital and lowercase letters are separate, so `C` is 67. 

Modern computer programming languages also support the use of Unicode characters. We won't cover that in this course, but it is important to remember later on when working with languages other than English. 

### String

Sometimes we want to store entire sentences in our computer programs. A sentence is just a _String_ of characters, object-oriented languages use a string class for this purpose and we'll cover everything we need to know about strings in a later chapter. 

