---
title: "Formatted Strings"
pre: "5. "
weight: 50
---

We've already seen one way that we can create strings of output for our users. In nearly all of the programs we've written so far, we have simply placed variables into our print statements, along with strings inside of quotation marks, and then combined them together. However, most programming languages support a way to create _formatted_ output strings.

The syntax varies for each programming language, but in essence, we can create a string with _placeholders_ for variables, and we can also include information about how those variables should be formatted.

For these examples, I'll be using the most common syntax, which comes from the C programming language. Both Java and Python use a similar syntax, but each language works a bit differently, so we'll want to consult the documentation linked later in this chapter for our language of choice. 

Consider this string as an example:

```
Welcome %s! You have loaded this program %d days so far.
```

In that string, we have "%s" and "%d" as placeholders. The first one, "%s", specifies that it should be replaced by a string since it includes the letter "s", while the second one, "%d", should be replaced by an integer (also known as a decimal, hence the use of the letter "d")[^1]

[^1]: These particular formatting  codes originate in C ( s- string, d- decimal, x-hexadecimal, f-floating point), which probably borrowed the idea from Fortran.  In older versions of Fortran "D" is used for double precision floats.

In addition, we could also specify things such as the number of leading 0s or decimal places in these format strings as well. 

Here's another example:

```tex
Your balance is $%8.3f
```

In this example, the format string "%8.3f" specifies that we should create an output that is 8 characters wide, including 3 decimal places. Finally, the use of the character "f" tells us that it expects a floating point value. So, if we replaced that format string with the value `1.23`, the resulting string would be:

```tex
Your balance is $   1.230
```

Formatted output strings are a great way to make sure our output is formatted exactly the way we want. 