---
title: "Variable Scope"
pre: "3. "
weight: 30
---

Now that we've learned how to create new code blocks in our programs using constructs such as the **If-Then** and **If-Then-Else** statements, we must take a minute to discuss one of the major limitations of those code blocks.

The _scope_ of a variable refers to the possible areas in a program's code where that variable can be accessed and used. This is very important to understand once we begin introducing additional code blocks in our programs, because variables declared inside of a code block cannot be accessed outside of that block.

## Local Variable Scope in Java

In general, Java follows these rules when determining if a local variable is accessible.

1. A local variable in Java **may not** be accessed before it is first declared. 
1. A local variable in Java **may not** be accessed outside of the code block in which it is declared.
1. A local variable in Java **may** be accessed inside of any code blocks placed inside of the code block in which is declared.
1. A local variable in Java **may not** have the same name as an existing variable contained in an enclosing code block.

Later on in this course we'll learn about class member variables, which have some different rules that govern their scope. For now, we'll only worry about local variables, which are variables declared within a method body. 

## Accessing Before Declaring

Let's look at a few examples for each rule. First, a variable may not be accessed before it is declared. So, we cannot do the following:

```java
public static void main(String[] args){
  x = 5;
  int x;
}
```

If we do, the compiler will output an error similar to the following:

```tex
error: cannot find symbol
    x = 5;
    ^
  symbol:   variable x
```

Instead, we must make sure the variable is declared before it is accessed, as in this correct example:

```java
public static void main(String[] args){
  int x;
  x = 5;
}
```

## Accessing Outside Code Block

Next, here's an example where the code is trying to access a variable outside of the code block where it is initially declared:

```java
public static void main(String[] args){
  int x = 5;
  if(x < 10){
    int y = x + 5;
  }
  System.out.println(y);
}
```

Once again, the compiler cannot find the variable, and we'll get an error similar to the following:

```tex
error: cannot find symbol
  System.out.println(y);
                     ^
  symbol:   variable y
```

If we think about this error, it actually makes sense. What if the value of `x` is greater than {{< math >}}$ 10 ${{< /math >}}? In that case, the program will never execute the line declaring the variable `y`, so it won't even exist. Therefore, if we'd like to solve this problem, we can try to declare our variable outside of the **If-Then** statement's code block, as in this second example:

```java
public static void main(String[] args){
  int x = 5;
  int y;
  if(x < 10){
    y = x + 5;
  }
  System.out.println(y);
}
```

However, this example will also cause the compiler to give us an error:

```tex
error: variable y might not have been initialized
  System.out.println(y);
                     ^
```

In this case, we've declared the variable `y`, but we have not initialized it to a value. Once again, if the value of `x` is greater than {{< math >}}$ 10 ${{< /math >}}, and the code block inside the **If** statement is not executed, we won't know what value should be stored in `y`. So, the compiler will detect that error and warn us that `y` may not have been initialized. To solve this error, we simply must assign a value to `y` before attempting to use it:

```java
public static void main(String[] args){
  int x = 5;
  int y = 0;
  if(x < 10){
    y = x + 5;
  }
  System.out.println(y);
}
```

That example will compile and run as expected.

Surprisingly, the Java compiler is advanced enough to determine if a variable would be initialized by all possible paths, as in this example:

```java
public static void main(String[] args){
  int x = 5;
  int y;
  if(x < 10){
    y = x + 5;
  }else{
    y = x - 5;
  }
  System.out.println(y);
}
```

This example will compile and run without any problems, since the variable `y` is initialized in both blocks of the **If-Else** statement. In short, there is no possible execution path that does not initialize `y`, so it is accepted by the compiler. 

## Accessing Inside a Code Block

We've already seen several examples of this already, but here's a clear example of accessing a variable from a code block within the block where the variable was declared:

```java
public static void main(String[] args){
  int x = -1;
  if(x < 0){
    x = -1 * x; 
  }
  System.out.println(x);
}
```

In this example, the variable `x` is declared inside of the `main` method's body. Then, it is accessed inside of the body of the **If** statement, which is itself within the body of the `main` method. Later in this chapter we'll see examples of chaining and nesting conditional constructs, which will give us more examples of how this works.

## Same Variable Names

Finally, Java does not allow us to use the same variable name twice in the same code block, or in any code blocks enclosed within that block. For example, we could try to do something like this:

```java
public static void main(String[] args){
  int x = 5;
  if(x < 10){
    int x = 15;
    System.out.println(x);
  }
}
```

If so, the compiler will detect that we've already declared variable `x` in the `main` method body, so it won't allow us to declare it again inside the **If-Then** statement's body. Instead, it will give us the following error message:

```tex
error: variable x is already defined in method main(String[])
    int x = 15;
        ^
```

We can resolve this error by simply renaming one of the variables:

```java
public static void main(String[] args){
  int x = 5;
  if(x < 10){
    int y = 15;
    System.out.println(y);
  }
}
```

We may also choose to use the same variable without declaring it again:

```java
public static void main(String[] args){
  int x = 5;
  if(x < 10){
    x = 15;
    System.out.println(x);
  }
}
```

However, we'll need to remember that it will change the value of the variable outside the block as well. 

Lastly, while we cannot use the same variable name as an existing variable, we can use that name later on in our program, as long as there is not already a variable declared with the same name that is accessible. Here's an example of that:

```java
public static void main(String[] args){
  int x = 5;
  if(x < 10){
    int y = 15;
    System.out.println(y);
  }
  int y = 12;
  System.out.println(y);
}
```

Surprisingly, this program will compile and run without any errors. In this case, we are allowed to declare a variable named `y` inside of the **If** statement's code block because we have not yet declared a variable with that name anywhere in our program. Later, we are allowed to declare another variable named `y`, this time directly within the `main` method's body. This is because we are outside of the **If** statement's code block, so the previously declared variable named `y` no longer exists. So, we can reuse the name here without causing any problems. 

However, this is _**widely**_ regarded as poor coding practice, as it may make our code very difficult to read and understand. So, it is always better to try and avoid reusing variable names whenever possible, just to make it clear in our code which to variable we are referring. 