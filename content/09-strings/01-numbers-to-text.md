---
title: "From Numbers to Text"
pre: "1. "
weight: 10
---

Up to this point, we've learned how to store data in many different forms in our programs. We've used integers and floating point numbers to store various numerical values, and Booleans to store `true` and `false` in our programs. We have learned how to make arrays of those data types when we need to store several of them together. We can even create multidimensional arrays when we want to store data in a structured way, such as a grid for representing 2D data in a game. 

However, we haven't covered how to handle one of the the most important types of data that our programs can handle - text. Text is a fundamentally important type of data in the world today, because it is really what enables us to share broad ideas across the entire Internet. Therefore, our programs need to be able to work with that type of data clearly and effectively. 

As we've seen so far, computers are well suited to working with numerical data. In fact, all the data stored on a computer are just numbers, written in a binary format. So, how can we store text in our computer, using that binary format?

## ASCII and Unicode

![ASCII Table](/images/09-string/7.1.ascii.wikimedia.svg)[^1]

[^1]: File:ASCII-Table-wide.svg. (2019, January 19). Wikimedia Commons, the free media repository. Retrieved 23:04, February 21, 2019 from https://commons.wikimedia.org/w/index.php?title=File:ASCII-Table-wide.svg&oldid=335449197.

In the 1960s, the _American Standard Code for Information Interchange_, abbreviated as _ASCII_ and usually pronounced "az-skee", was developed as a way to represent text on a system that was designed to store numerical data. Each character in the English alphabet was assigned a value. So, on a computer, the decimal value $65$ represents the character `A`, while the decimal value $116$ represents `t`. In addition to the printed characters in English, several other characters were added to ASCII, representing items such as a tab character or newline in printed text. In that way, an entire document of printed text could be represented as a list of numbers using ASCII. 

However, ASCII can only handle simple characters in English, and wasn't a very good system for storing text in other languages. So, another encoding system, known as _Unicode_, was developed in the 1980s to handle text in a variety of writing systems. As the Internet grew, Unicode became much more prevalent, and by the late 2000s, a majority of websites on the Internet were using UTF-8, a version of Unicode, to store and represent their data.

UTF-8 was chosen as a global standard because it is also backwards compatible with ASCII. So, any text written in ASCII will automatically work in UTF-8 as well, bypassing any required conversion step.

In this book, we'll generally be using ASCII to refer to the encoding system used to handle text in our programs. However, behind the scenes, it is important to know that most of the text may actually be stored and represented in Unicode, specifically UTF-8, depending on how we are using it. 

