---
title: "Instance Classes"
pre: "1. "
weight: 10
---

Now that we understand the basics of what classes and objects are in object-oriented programming, let's look at how to create these items in Java.

## Creating an Instance Class

Creating a class in Java is very similar to creating a method. The syntax is `<access modifier> class <ClassName> {<body>}`.  We will use `public` for all our class-access modifiers.   The class definition (body), like all Java code-bodies, is enclosed in `{}`. 

Java requires just a single public-class in each file, with the filename matching the name of the class, followed by the `.java` file extension. By convention, class names in Java should be nouns, in mixed case (Pascal-case) with the first letter of each internal word capitalized[^1].

[^1]: https://www.oracle.com/java/technologies/javase/codeconventions-namingconventions.html]

So, to create an empty class named `Ingredient`, we would place the following code in a file named `Ingredient.java`:

```java
public class Ingredient {}
```

As we've already learned, each class declaration in Python includes these parts:
1. `public` - an access modifier enabling other parts of the code to "see" the class
1. `class` - this keyword says that we are declaring a new class.
1. `Ingredient` - this is an identifier that gives us the name of the class we are declaring.
1. `{}`- an empty body that does nothing.  

Following the declaration, we see a colon `{` marking the start of a new block, inside of which will be all of the _fields_ and _methods_ stored in this class. We'll need to indent all items inside of this class, just like we do with other blocks in Java.

In order for Java to allow this code to compile, we must have a body.  The `{  }` can be empty but cannot be missing.

To the left, we should see a tab for `Ingredient.java`. Let's go ahead and add the class declaration to it. Once we've completed that, we can use the button below to check our code and confirm that it is working before moving ahead.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

