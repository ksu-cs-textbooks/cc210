---
title: "Printing Text & Numbers"
pre: "8. "
weight: 80
---

## Printing Text with Variables

Now that we've learned how to run our program and provide it some input, we must also learn how to provide output that includes our variables as well as text all on the same line. There are a few ways to accomplish this.

First, we can use `System.out.print()` to print text without a newline character at the end, so that the next output will begin on the same line. So, we could use that to print text and variables on the same line. Here's an example:

```java
int x = 1;
int y = 2;
System.out.print("Variable x: ");
System.out.print(x);
System.out.print(", Variable y: ");
System.out.println(y);
```

will produce this output:

```tex
Variable x: 1, Variable y: 2
```

In Java, we can also concatenate multiple outputs together using the `+` symbol. So, we could produce similar output using this example:

```java
int x = 1;
int y = 2;
System.out.println("Variable x: " + x + " , Variable y: " + y);
```

which should output:

```tex
Variable x: 1 , Variable y: 2
```

Notice that we needed to include an extra space after `1` in the output. This is because Java does not add a space between strings when concatenating them, so we must be careful to add the spaces ourselves where needed.

There are many ways that we can use Java to output text and variables as desired. We'll use some of these methods to complete this project. 