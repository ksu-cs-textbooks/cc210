---
title: "Parameters"
pre: "2. "
weight: 20
---

{{< youtube O-vkFmelepU  >}}

[Video Materials]({{% relref "./video" %}})

Methods are a very useful way to divide our code into smaller chunks. However, many times we need to provide input to our methods. This allows us to reuse the same code, but with different values each time we call the method. So, let's review how to add _parameters_ to our methods in Java.

## Method Parameters

In Java, we can add parameters to a method declaration by placing them in the parentheses `()` at the end of the declaration. Each parameter is similar to a variable declaration, requiring both a type and an identifier. We can also define multiple parameters, separated by commas `,`. 

For example, let's extend our definition of `foo()` from the previous page by adding a String parameter named `message`:

```java
static void foo(String message){
    System.out.println("Message: " + message);
}
```

Then, when we call that method, we are required to provide an _argument_ of the correct type. That argument will be stored as the parameter's variable in `foo()`:

```java
foo("Hello World!");
```

## Another Example

Here's another example. In this case, we are writing two methods, `foo()` and `bar()`. They accept multiple parameters, and in `main()` we call each method using arguments for each parameter.

```java
public class Parameters{
    public static void main(String[] args){
        int x = 5;
        int y = 10;
        int z = 8;
        bar(x, y, z);
        foo(y, true);
    }
  
    static void foo(int output, boolean longMessage){
        if(longMessage){
            System.out.println("The value was " + output);
        }else{
            System.out.println("Val: " + output);
        }
    }
  
    static void bar(int a, int b, int c){
        System.out.println(a + ", " + b + ", " + c);
    }
}
```

First, let's look at `bar()`. When we call this method from `main()`, we are using `x`, `y`, and `z` as arguments. So, inside of `bar()`, the value stored in `x` will be stored in `a`, `y` will be stored in `b`, and `z` will be stored in `c`. The parameters and arguments are matched up based on the order they are provided to the method call. So, `bar()` will output `5, 10, 8` when it is called with those parameters.

The call to `foo()` is very similar. It only contains two parameters, but each one is a different type. So, when we call that method, we must make sure that the first parameter is an integer, and the second one is a Boolean value. 
