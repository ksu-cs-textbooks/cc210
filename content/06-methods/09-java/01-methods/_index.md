---
title: "Methods"
pre: "1. "
weight: 10
---

{{% youtube F6YsCehtfS0 %}}

[Video Materials]({{<relref "./video">}})

Now that we've covered the basic ideas of adding methods to our programs, let's see how we can do that using the Java programming language.

## Declaring Methods

We've already seen how to create methods in our programs, since each program in Java already includes a method named `main`. In general, a method declaration in Java needs a few elements. Let's start at the simplest case:

```java
public static void foo(){
    System.out.println("Foo");
    return;
}
```

Let's break this example method declaration down to see how it works:

1. First, we use the keyword `static` at the beginning of this method declaration. That keyword allows us to use this method without creating an object first. We'll cover how to create and work with objects in a later module. For now, each method we create will need the `static` keyword in front of it, just like the `main()` method. 
1. Then, the second keyword, `void`, determines the type of data returned by the method. We use a special keyword `void` when the method does not return a value. We've already seen this keyword used in our declaration of the `main` method.
1. Next, we have the name of the method, `foo`. We can name a method using any valid identifier in Java. In general, method names in Java always start with a lowercase letter. 
1. Following the method name, we see a set of parentheses `()` that list the parameters for this method. Since there is nothing included in this example, the method `foo` does not require any parameters.
1. Finally, we see a set of curly braces `{}` that surround the code of the method itself. In this case, the method will simply print `Foo` to the terminal.
1. The method ends with the `return` keyword. Since we aren't returning a value, we aren't required to include a `return` keyword in the method. However, it is helpful to know that we may use that keyword to exit the method at any time. 

We'll cover how to handle method parameters and return values later in this module. For now, we'll just look at creating simple methods that neither require parameters nor return values. 

## Calling Methods

Once we've created a method in our code, we can _call_, or _execute_, the method from anywhere in our code using the following syntax:

```java
foo();
```

We simply use the name of the method, followed by parentheses, wherever we'd like to call that method. Again, we'll see how to pass arguments to the method and store the return value later in this module. 

## Example

Let's look at a complete sample program to see how this all fits together.

```java
public class Methods{
    public static void main(String[] args){
        System.out.println("Main 1");
        foo();
        System.out.println("Main 2");
        foo();
        System.out.println("Main 3");
        return;
    }
  
    public static void foo(){
        System.out.println("Foo 1");
        return;
    }
}
```

When we run this program, we should see the following output:

```tex
Main 1
Foo 1
Main 2
Foo 1
Main 3
```

We can also look at a flowchart diagram of this program to help understand how it works:

![Method Call Flowchart](/images/06-method/10.10.x.1.functioncall.png)

As we can see in this diagram, the program starts in the `main()` method. Inside, it prints `Main 1`, then calls the method `foo()`. So, we can follow the dashed line over to `foo()`, where it will print `Foo 1` and return back to main along the same dashed line. Then, we'll print `Main 2` in `main()`, before calling `foo()` once again. This time, we'll follow the dotted line to `foo()`, where we'll once again print `Foo 1` before returning back to `main()` and printing `Main 3`. 

{{% notice info "Method Signature" %}}

The line `public static void main(String[] args)` is often referred to as a **method signature**.  It contains all the vital information necessary to use the method: its name, what it returns, and what type of parameters it requires.  Even `public  static` inform the programmer on where and how to invoke the method, but we'll cover these key words when we cover classes.

{{% /notice %}}
