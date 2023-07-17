---
title: "Variable Scope"
pre: "5. "
weight: 50
---

Another topic we must revisit is _variable scope_. Recall from an earlier chapter we learned how variables may only be referenced after they've been defined, and in many cases only within the method or block they are defined in. Now that we are dealing with multiple methods, we must once again discuss variable scope and how it applies to this situation.

## Method Scope

In general, all of the scope rules we've learned still apply. For example, a variable declared in a method can only be accessed within that method. In that way, different methods may use the same variable names to refer to different variables. In addition, as we've seen in the earlier examples, a method may define parameters using the same variable names as the variables that are used as arguments to that method. It may seem confusing to some, but to others it makes perfect sense.

## Class Scope

Most programming languages also allow us to create variables at the class level, inside a class but outside of any method. Those variables can then be referenced within any of the class's method, allowing us to share data between methods without using parameters and return values.

Here's a quick example in code:

```java
public class MathOperations {

    double PI = 3.1415926535;

    public static void main(String[] args){
        double r = 3.0;
        double area = calculateArea(r);
        System.out.println(area);
    }

    public static double calculateArea(double r){
        return r * r * PI;
    }

} 

```

In this example, we have created a class variable named `PI` to store the value of {{< math >}}$ \pi ${{< /math >}} for our entire program. Then, we can use that variable just like any other inside of the `calculateArea` method.

Of course, we can assign and edit class variables just like any other variable:

```java
public class Foo{
    static int people = 1;

    public static void main(String[] args){
        people = people + 1;
        foo();
        System.out.println(people);
    }

    public static void foo(){
        people = people * 3;
    }
}
```

In this example, the `main` method will print {{< math >}}$ 6 ${{< /math >}} as the value of `people`. Since that variable is declared in the _class scope_, it can be accessed and changed by any method. 

## Shadowing Variables-- Using the Same Variable Names

Sometimes we may want to have a variable inside of our methods use the same name as a class variable, this is a type of **shadowing**. Shadowing occurs whenever an inner scope name hides (in its shadow) an outer scope variable of the same name.  Here's a modified version of the code above showing that situation:


```java
public class Foo{
    static int people = 1;

    public static void main(String[] args){
        int people = 1;
        people = people + 1;
        foo();
        System.out.println(people);
    }

    public static void foo(){
        people = people * 3;
    }
}
```

In this example, the variable `people` is redeclared inside of the `main` function. So, it is an entirely different variable than the class variable named `people`. Because of this, whenever we use the variable `people` inside of `main`, we are referring to the _method scope_ or _local scope_ variable people. Therefore, the class-scope value is not updated by the `main` method, and `main` will simply print {{< math >}}$ 2 ${{< /math >}} instead of {{< math >}}$ 6 ${{< /math >}}. 

Shadowing is not necessarily bad, and may be unavoidable in large programs using multiple imported modules. It is something that a developer should always be aware of, since it can have unintended consequences. 
