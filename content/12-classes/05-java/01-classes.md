---
title: "Classes"
pre: "1. "
weight: 10
---

## Creating a Class

We've already been creating and using classes in our Java programs up to this point. This is because Java is a truly object-oriented language, meaning that all code in Java must be contained as part of a class.

Java requires that each class be stored in a file with the same name, followed by the `.java` file extension. By convention, class names in Java are written in CamelCase, meaning that each word is capitalized and there are no spaces between the words. We'll follow these rules in our code. 

So, to create a class named `Student`, we would place the following code in a file named `Student.java`:

```java
public class Student{
  
}
```

As we've already learned, each class declaration in Java includes these parts:
1. `public` - this keyword is used to identify that the item after it should be publicly accessible to all other parts of the program. Later in this chapter, we'll discuss other keywords that could be used here.
1. `class` - this keyword says that we are declaring a new class.
1. `Student` - this is an identifier that gives us the name of the class we are declaring.

Following the declaration, we see a set of curly braces `{}`, inside of which will be all of the _fields_ and _methods_ stored in this class.

To the left, we should see three Java files open: `Student.java`, `Teacher.java`, and `Main.java`. Let's go ahead and add the class declaration code to each file. Once we've completed that, we can use the button below to check our code and confirm that it is working before moving ahead.




