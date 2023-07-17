---
title: "DRY: Don't Repeat Yourself"
pre: "6. "
weight: 60
---

One major mantra among programmers is **Don't Repeat Yourself (DRY)**, and it's a very important concept to keep in mind when writing programs that can use methods. In essence, anytime we find ourselves writing the same or similar code multiple times in our program, we may want to ask ourselves if it would be better to make that piece of code a method. That way, we only have to write it once, and if there are any problems with that code, we only have to remember to change it in one place instead of everywhere we've used it. 

## DRY Example

To really understand how DRY can improve our code, let's look at a quick example:

```java
import java.lang.Math;

public class Dry{

    public static void main(String[] args){
        int a = 1;
        int b = 0;
        int c = -4;
        double rootOne = (-b - Math.sqrt(b * b - 4 * a * c)) / (2 * a);
        double rootTwo = (-b + Math.sqrt(b * b - 4 * a * c)) / (2 * a);
        System.out.println(rootOne);
        System.out.println(rootTwo);

        a = 2;
        b = 7;
        c = 3;
        rootOne = (-b - Math.sqrt(b * b - 4 * a * c)) / (2 * a);
        rootTwo = (-b + Math.sqrt(b * b - 4 * a * c)) / (2 * a);
        System.out.println(rootOne);
        System.out.println(rootTwo);
    }
}
```

Of course, this is a very simple example calculating the roots of a quadratic equation. 

{{< math >}}
$$ax^2 + bx + c$$
{{< /math >}}

However, we see that this program repeats many lines of code to perform the same basic calculation with different values. We can easily move that calculation to a new method, and then use parameters to set the values. So, let's apply the DRY principle to simplify this program:

```java
import java.lang.Math;

public class Dry{

    public static void main(String[] args){
        quadratic(1, 0, -4);
        quadratic(2, 7, 3);
    }

    public static void quadratic(int a, int b, int c){
        rootOne = (-b - Math.sqrt(b * b - 4 * a * c)) / (2 * a);
        rootTwo = (-b + Math.sqrt(b * b - 4 * a * c)) / (2 * a);
        System.out.println(rootOne);
        System.out.println(rootTwo);
    }
}
```

There! We've moved all of the code for calculating the roots for the quadratic equation, printing each root at the end. Then, we can simplify the code in `main` by simply calling that method anytime we want to calculate the roots .

This could be further reduced by "pre calculating" the discriminant since it is used twice in the `quadratic` function. 

```java
import java.lang.Math;

public class Dry{

    public static void main(String[] args){
        quadratic(1, 0, -4);
        quadratic(2, 7, 3);
    }

    public static void quadratic(int a, int b, int c){
        d = discriminant(a, b, c);
        rootOne = (-b - Math.sqrt(d)) / (2 * a);
        rootTwo = (-b + Math.sqrt(d)) / (2 * a);
        System.out.println(rootOne);
        System.out.println(rootTwo);
    }

    public static int discriminant(int a, int b, int c){
        return b * b - 4 * a * c;
    }
}
```

We can also extend this code to make use of the fact that the value of the discriminant tells us how many different roots a quadratic equation will have. By moving code to functions, we can quickly find additional ways to expand upon and improve our programs.

Properly following the DRY principle when writing code will make our programs simpler, easier to maintain, and hopefully easier to debug. In effect, it is definitely a good idea to add a new method to our code anytime we find ourselves typing something twice, or copy and pasting code. 