---
title: "Other Types"
pre: "3. "
weight: 30
---

Beyond numbers, there are a few other primitive data types in Java. Let's take a quick look at them and see how they can be used in our programs.

## Boolean

Java supports a primitive data type named `boolean` that can only store two values: `true` and `false`. As we might expect, we can use these boolean variables to store answers to questions in our program, such as "Is `x` greater than `y`?" At this point, we won't use boolean variables for much in our programs, but in a later module we'll cover the basics of boolean logic and learn how to use these variables to control how our program runs. 

## Character

Java also has a `char` data type, which can be used to store a single character of text. It uses the 16-bit Unicode format to store the data, which is the same as ASCII for simple characters and commands.

## Declaring & Assigning

To declare a variable using these data types, the format is the same as the numerical data types:

```java
boolean t;
char c;
```

We can also assign values to each variable. For example, to assign a value to a boolean variable, we could do this:

```java
boolean t;
t = true;
boolean f = false;
```

Notice that both `true` and `false` are _keywords_ in Java, which means that we won't have to put them in quotation marks to use them. These values can be used to directly represent the boolean values True and False, respectively. Some programming languages, most notably C, do not support boolean values in this way, but Java includes them as keywords.

For characters, the process is similar:

```java
char c;
c = 'a';
char d = 'B';
```

Notice that we use a single quotation mark `'` around character values in our code. This is very important to remember! In our Hello World example, we used double quotation marks `"` around _strings_, or sentences of text. For a single character, however, we only use a single quotation mark. 

{{% notice info "Characters & Strings" %}}

Thankfully, the Java compiler will catch this problem pretty quickly. For example, take a look at this code, and see if you can spot the errors:

```java
char c = "a";
System.out.println("c");
```

When we first try to compile the program, we should get the following error:

![Compilation Error](/images/02-data/image_4.png)

As we can see, the compiler will not allow us to assign the string `"a"` to the variable `c`, which is of type `char`. So, to fix this error, we'll need to modify our code to be the following:

```java
char c = 'a';
System.out.println("c");
```

However, there might be another error in this code. Can you spot it? What will be printed to the screen when we run this program? 

Let's find out:

![Program Output](/images/02-data/image_5.png)

You might have expected the program to output `a`, but instead it output `c`. This is because we have `"c"` inside of our `System.out.println` method. To print the value stored inside a variable, we shouldn't put it in quotation marks. Otherwise, it will interpret that as a string, and print the name of the variable (or whatever is in quotation marks) instead. 

{{% /notice %}}
