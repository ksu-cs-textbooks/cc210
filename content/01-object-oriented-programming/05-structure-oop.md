---
title: "Structure of an Object-Oriented Program"
pre: "5. "
weight: 50
---

An object oriented program contains lots of additional syntax that instructs the compiler or interpreter^[We are going to just use compiler for simplicity's sake] to impose certain conditions when creating the machine- or byte-code.  We will address the details of this syntax after you have learned the necessary background, until then we will just give you the code.

## Everything Is In a Class

Classes are the blueprints of objects.  In an object oriented program everything is inside a class definition.  In this class, every file will contain exactly class definition or class-body.

```tex
# Pseudo Code
CLASS <identifier>{
   class-body
}
```


```java
// Java
public class <identifier> {
    class-body
}
```


```python
# Python
class <identifier>:
    class-body
```

### Code Block Delimiters

The class-definition is a "code-block." Code-blocks signal a boundary to the compiler.  This helps the compiler manage identifier names, memory and other things.

Code-blocks are delimited, or set apart by various symbols.  In Java and pseudo code, this is done with brackets `{ code block }`.  Spacing is often also used to make the code more readable, everything a block lines up.

In Python each code block is indented to the right; in this class we will use 4-spaces.  When a line ends with a colon, Python expects the next line to be the start of a new code block (and therefore indented).

```tex
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

In the preceding examples, statement_one and statement_two are the code block for class-Foo's definition.

## Every Program Starts Somewhere

By tradition (and by rule in many languages)  object oriented programs start in a method called `main().`

```tex
# Pseudo Code
CLASS <class identifier>{
   FUCNTION main(){
       function-body
   }
}
```
```java
// Java
public class <class identifier> {
    publlic static void main(String[] args){
        method-body
    }
}
```
```python
# Python
class <class identifier>:
    @classmethod
    def main(args):
        method-body
```

For the first several modules, all of the code you need to write will be in the method-body for `main()`.  The area for you code will be clearly delimited.

```python
# Python
class Foo:
    @classmethod
    def main(args):
        ###  your code goes below this line

        ###  your code goes above this line
```
