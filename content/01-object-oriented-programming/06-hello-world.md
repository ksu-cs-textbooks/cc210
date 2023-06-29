---
title: "Hello World"
pre: "6. "
weight: 60
---

Tradition dictates that the first program in any introduction course is _Hello World_. _Hello World_ simply prints the text "Hello World" to the screen.

Below is an example of an object-oriented version of this program in both Java and Python:

```java
// Java
public class HelloWorld{
    public static void main(String[] args){
        System.out.println("Hello World");
    }
}
```

```python
# Python
class HelloWorld:
    @classmethod
    def main():
        print("Hello World")


HelloWorld.main()
```

In each program, the actual work is done by the line containing the word `print`. In the rest of this module, we'll explain the details behind the structure of this program.


