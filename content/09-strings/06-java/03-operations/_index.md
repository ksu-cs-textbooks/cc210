---
title: "String Operations"
pre: "3. "
weight: 30
---

{{% youtube k4-RnL5niK4 %}}

[Video Materials]({{<relref "./video">}})

The string data type includes many built-in operations that we can use to compare, manipulate, and search within strings. We'll cover several of them on this page, and we'll also include links at the bottom to additional resources where all of them are listed.

## Length

First and foremost is the `length()` method. It allows us to find the number of characters in a string. 

```java
String s = "This";
System.out.println(s.length()); // 4

String t = "This \"is\" that";
System.out.println(t.length()); // 14
```

Notice that the second string, stored in variable `t`, only contains 14 characters. That is because `\"` only counts as a single character in the output, so it is stored as a single character in the string. The same applies to any of the special characters we've seen so far in this chapter.

## Comparison

Next, we can use special methods in Java to compare two strings. First, we must use the `equals()` method to determine if two strings are equal (meaning they contain exactly the same characters in the same order), as in this example:

```java
String s1 = "This";
String s2 = "This";
String s3 = "this";

System.out.println(s1.equals(s2)); // true
System.out.println(s1.equals(s3)); // false
```

{{% notice warning "Don't Use == with Strings!" %}}

When comparing two strings in Java, we cannot use the equality `==` operator. This is because Java stores strings as an _object_, and not a primitive data type such as the integers and floating point numbers we've seen so far.

When using the equality operator, it will test to see if the two _objects_ are exactly the same, not the contents of the string. 

Here's an example:

```java
String s1 = "This";
String s2 = s1;
String s3 = new String("This");

System.out.println(s1 == s2); // true
System.out.println(s1 == s3); // false
```

In this case, even though all three strings contain the same data, they may not be the same objects in memory. So, we must always use the `equals()` method instead.

{{% /notice %}}

Similarly, we can use the `compareTo()` method to compare two strings and see which one should be placed first in lexicographic order. Consider this example:

```java
String s1 = "This";
String s2 = "That";

int x = s1.compareTo(s2);
```

In this example, `x` will be a negative number if s1 should come before s1, a positive number if s2 should come before s1, and exactly 0 if the two strings are the same. 

While this may seem a bit complex, there is actually a great way to remember how this works. Whenever we would normally want to say `s1 < s2`, we'll instead say `s1.compareTo(s2) < 0`. In effect, we replace the left side with `s1.compareTo(s2)`, and then replace the right side with 0, leaving the sign the same. This simple conversion works for all comparison operators:

* `s1 < s2` &rarr; `s1.compareTo(s2) < 0`
* `s1 <= s2` &rarr; `s1.compareTo(s2) <= 0`
* `s1 > s2` &rarr; `s1.compareTo(s2) > 0`
* `s1 >= s2` &rarr; `s1.compareTo(s2) >= 0`
* `s1 == s2` &rarr; `s1.compareTo(s2) == 0`

## Concatenation

Another common string operation is _concatenation_, or joining two strings together. This operation is actually very simple, and there are multiple ways to do it.

First, we can use the `+` operator to concatenate any two strings together. In addition, if at least one of the operands is a string, Java will automatically convert the other operand to a string, if possible. 

Here are a few examples:

```java
String s1 = "This";
String s2 = "That";
int x = 42;

String s3 = s1 + s2;
String s4 = "" + x;

System.out.println(s3); // ThisThat
System.out.println(s4); // 42
```

As we can see, one neat way to convert any primitive data type to a string is to simply concatenate it with an empty string literal, represented by empty double quotation marks in the code above.

Strings also include a method named `concat()` that will also perform concatenation. However, it does not modify the original string, so we'll have to remember to store the result in a string variable in order to use it.

```java
String s1 = "This";
String s2 = "That";

String s3 = s1.concat(s2); // we can store it in a new variable, and the original is unchanged!

System.out.println(s1); // This
System.out.println(s3); // ThisThat

s2 = s2.concat(s1); // we can store it in the same variable!

System.out.println(s2); // ThatThis
```

Either method works well for concatenating two strings together. 

## Searching Within Strings

Java also includes several methods that can be used to search within one string for another. We can even specify if we'd like to find the string at the beginning or the end of the string, and it includes methods to give us the location of the string we are searching for. Here's a great example of several of those methods in action:

```java
String s1 = "abc123abc123";

System.out.println(s1.contains("123")); // true
System.out.println(s1.contains("321")); // false

System.out.println(s1.indexOf("123")); // 3  (the index of the first character)
System.out.println(s1.indexOf("321")); // -1 (it returns -1 if it can't find it)

System.out.println(s1.lastIndexOf("123")); // 9  (it returns the beginning of the last instance)
System.out.println(s1.lastIndexOf("321")); // -1 (it returns -1 if it can't find it)

System.out.println(s1.startsWith("abc")); // true
System.out.println(s1.startsWith("123")); // false

System.out.println(s1.endsWith("abc")); // false
System.out.println(s1.endsWith("123")); // true
```

## Manipulating Strings

Finally, Java includes methods that can be used to manipulate strings in unique ways. It is important to remember that none of these methods modify the original string, so we'll need to store the result back in a string variable in order to use it. In these examples, we'll just print the output so we can see the result:

```java
String s1 = "abc123abc123";

// replace takes two characters as input, and replaces all 
// instances of the first character with the second
System.out.println(s1.replace('b', ' ')); // a c123a c123

// substring takes two integers as input, and returns
// all characters starting at the first index up to
// but not including the second index
System.out.println(s1.substring(3, 9)); // 123abc

String s2 = "UPPERlower";

System.out.println(s2.toLowerCase()); // upperlower
System.out.println(s2.toUpperCase()); // UPPERLOWER

String s3 = "  \t Some String  \n \n ";

// trim removes all whitespace characters from the beginning
// and end of the string, including special characters
// such as newlines and tabs. 
String s4 = s3.trim();
    
System.out.println(s4); // Some String
System.out.println(s4.length()); // 11
```

In Java, we can also get a single character from a string using the `charAt` method. This is similar to getting a substring of length 1, but in this case it returns a `char` data type:

```java
String s1 = "abc123";

char c1 = s1.charAt(0);
char c2 = s1.charAt(5);

System.out.println(c1); // a
System.out.println(c2); // 3
```

This is just a small list of the many operations that can be performed on strings in Java. For more information, consult the official Java documentation linked below.

### References

[Java String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)