---
title: "Switch Statement"
pre: "5. "
weight: 50
---

Next, let's look at the **switch statement** in Java. As we learned earlier, this statement allows our programs to choose branches based on any number of possible values of a variable. Here's a flowchart showing what such a program might look like:

![Switch Statement](/images/04-cond/4.5.switch.png)

In Java, we could write that program in many ways. This is one possible solution:

```java
public static void main(String[] args) {
  int x = 2;
  switch (x) {
    case 1: System.out.println("A");
      break;
    case 2: System.out.println("B");
      break;
    case 3: System.out.println("C");
      break;
    default: System.out.println("Error!");
      break;
  }
}
```

In this program, the switch statement will evaluate the value of `x`, then look for the `case` keyword that exactly matches that value. In this example, `x == 2`, so it will choose the second case and output `B`. 

If we change the value of `x` to {{< math >}}$ 4 ${{< /math >}}, then we can see that none of the `case` keywords match. In that instance, the program will instead choose the `default` case and print `Error!`. 

## Fall Through

The switch statement above introduces a new keyword, `break`, which we'll cover in detail in a later chapter. The `break` keyword causes the program to stop executing code in the current statement, and the continue executing the code following that statement. So, when the program reaches a `break` statement in the example above, it stops executing any additional code in the **switch statement** and continues running the code following that statement.

It is possible to create a switch statement that does not include `break` keywords. In that statement, it will continue executing any cases below the chosen case until it reaches the end of the statement or the `default` keyword. 

For example, let's say we'd like to write a program that will print all the numbers from a given starting number up to 5. So, we could use a **switch statement** to do that as in this program:

```java
public static void main(String[] args){
  int x = 2;
  switch (x) {
    case 1: System.out.println("1");
    case 2: System.out.println("2");
    case 3: System.out.println("3");
    case 4: System.out.println("4");
    case 5: System.out.println("5");
      break;
    default: System.out.println("Error!");
      break;
  }
}
```

When we compile and run this program, we'll receive the following output:

```tex
2
3
4
5
```

The program will start at `case 2:`, since `x == 2`, and print `2`. Since there is not a `break` keyword in that case, it will continue to the next case, printing `3`, then `4`, then `5` before it finally reaches a `break` keyword. 

## Further Reading

**Switch Statements** are not used as often as other conditional constructs, but they can be a useful to a program in certain instances. There are many other unique ways they could be used. To learn more, refer to the official Java documentation on [The `switch` Statement](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/switch.html).  