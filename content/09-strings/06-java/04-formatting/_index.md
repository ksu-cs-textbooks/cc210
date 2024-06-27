---
title: "String Formatting"
pre: "4. "
weight: 40
---

{{< youtube _sxpOzam2mU  >}}

[Video Materials]({{% relref "./video" %}})

There are also a couple of different approaches we can take to formatting output strings in Java. Let's take a minute to review both of those and see how they work.

## Concatenation

We've already seen this approach in several programs in this course. In effect, we can simply build an output string by concatenating strings and the variables we'd like to include in those strings. 

For example, if we'd like to create an output string that gives both the sum and the average of a set of numbers, we could do something like this:

```java
int sum = 123;
double avg = 1.23;

System.out.println("The sum is " + sum + " and the average is " + avg + ".");
```

In this code, we are using the plus symbol `+` to concatenate strings and variables together into a single output string. In Java, the concatenate operator will automatically convert any primitive data type to a string for us, so we don't have to worry about that. In many cases, this is the quick and easiest way to present output to the user. 

## Formatted Strings

Java also includes a special string method, the `format()` method, which allows us to use _placeholders_ in our output string, and then replace those placeholders with the values stored in variables. 

Here's an example of how to use that method in Java:

```java
int sum = 123;
double avg = 1.23;
String name = "Student";

String output = "%s: Your score is %d with an average of %f.";

System.out.println(String.format(output, name, sum, avg));
```

When we run this program, the output will be:

```tex
Student: Your score is 123 with an average of 1.230000.
```

There are several unique parts to this code, so let's break it down and see how this works.

First, instead of using an existing string variable, we are actually using the `String` class when we use the `format()` method. This is because the `format()` method is a _static_ method. Static methods do not require an existing variable to use them, and can be used directly from the class where they are defined. We'll learn more about how classes and methods work in a later chapter. For now, just remember that we'll use `String.format()` whenever we want to use this method.

Inside of the method, the first input is the string that contains the placeholders. In this case, we are using three different placeholders:

* `%s` - This placeholder can be replaced by any string, or any variable which can be converted to a string. 
* `%d` - This placeholder can be replaced by any integer data type, including `int`, `short`, `byte`, or `long`. 
* `%f` - This placeholder can be replaced by any floating-point data type, including `double` and `float`. 

Following that, the rest of the inputs are the variables which should be placed in each placeholder, given in the order they appear in the format string. So, in this example, we want the first placeholder, `%s`, replaced by the second input, the `name` variable. 

In addition, many of the placeholders can also specify the _width_ and _precision_ of each output. Here's an updated example using these formatting options:

```java
int sum = 123;
double avg = 1.23;
String name = "Student";

String output = "%s: Your score is %5d with an average of %8.4f.";

System.out.println(String.format(output, name, sum, avg));
```

When we run this program, we'll see the output is now this:

```tex
Student: Your score is   123 with an average of   1.2300.
```

So, what happened? First, we updated the second placedholder to `%5d`. This means that we want the output of that variable to have a width of 5. Since the `sum` variable would only have 3 characters, the `format()` method adds two additional spaces in front of the number. 

Secondly, we updated the last placeholder to `%8.4f`. Once again, the number 8 is used to give the width of the output. In addition, we added a 4 after a decimal point to indicate how many characters we'd like to include after the decimal point in the output. So, the total output is `  1.2300`, which includes four characters after the decimal place, and an additional two spaces in the front. All told, the output is 8 characters in length, including the decimal point.

There are many more ways that a formatted string can be used to create output that meets our needs. We can find more information on using the placeholders and associated settings by reading the official Java documentation linked below.

### Reference

[Java Formatter Syntax](https://docs.oracle.com/javase/8/docs/api/java/util/Formatter.html#syntax)
