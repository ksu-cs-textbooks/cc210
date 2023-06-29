---
title: "Program Structure"
pre: "5. "
weight: 50
---

When writing code in an object-oriented language, many times we must use some additional syntax and structures in our programs that are required by the language, even though they aren't strictly required for the program we are trying to develop.

In this section, we'll briefly discuss some of those limitations. Later on in this course, we'll come back to these concepts and explain them more fully, but for now we'll provide some of this structure as starter code for the first few modules. 

## Everything Is In a Class

Classes are the blueprints of objects.  In an object-oriented program, everything is inside a class definition.  In this class, every file will contain exactly class definition or class-body.

```java
// Java
public class ClassName {
    class-body
}
```

```python
# Python
class ClassName:
    class-body
```

### Code Block Delimiters

The class-definition is a "code-block." Code-blocks signal a boundary to the compiler.  This helps the compiler manage identifier names, memory and other things.

Code-blocks are delimited, or set apart, by various symbols.  In Java, this is done with brackets `{ code block }`.  Spacing is often also used to make the code more readable, so that everything in a block lines up.

In Python, each code block is indented to the right. In this class we will use 4 spaces. When a line ends with a colon, Python expects the next line to be the start of a new code block (and therefore indented).

```java
public class Foo{
    statement one
    statement two
}

public class Bar{
    statement_three
}
```

```python
class Foo:
    statement_one
    statement_two

class Bar:
    statement_three
```

In the preceding examples, `statement_one` and `statement_two` are the code block for the class named `Foo`, and `statement_three` is part of the code block for the class named `Bar`.

## Every Program Starts Somewhere

By tradition (and by rule in many languages), object-oriented programs start in a method called `main().`

```java
// Java
public class ClassName {
    public static void main(String[] args){
        // method-body
    }
}
```

```python
# Python
class ClassName:

    @classmethod
    def main(args):
        # method-body
```

For the first several modules, all of the code we need to write will be in the method body for the `main()` method. This area will be clearly marked in the starter code using a comment similar to `WRITE YOUR CODE HERE`. 

