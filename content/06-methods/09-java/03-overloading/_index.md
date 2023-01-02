---
title: "Overloading"
pre: "3. "
weight: 30
---

{{% youtube bEVjtEc4IZM %}}

[Video Materials]({{<relref "./video">}})

There are several other things we can do with parameters in our methods, allowing us to use them in new and more flexible ways.

## Method Overloading

Java allows us to create multiple methods using the same name, or identifier in the same scope, as long as they have different parameter lists. This could include a different number of parameters, different data types for each parameter, or a different ordering of types. The names of the parameters, however, does _not_ matter here. This is called _method overloading_. 

For example, we could create a method named `max()` that could take either two or three parameters:

```java
public class Overloading{
  public static void main(String[] args){
    max(2, 3);
    max(3, 4, 5);
  }
  
  static void max(int x, int y){
    if(x >= y){
      System.out.println(x);
    }else{
      System.out.println(y);
    }
  }
  
  static void max(int x, int y, int z){
    if(x >= y){
      if(x >= z){
        System.out.println(x);
      }else{
        System.out.println(z);
      }
    }else{
      if(y >= z){
        System.out.println(y);
      }else{
        System.out.println(z);
      }
    }
  }
}
```

In this example, we have two methods named `max()`, one that requires two parameters, and another that requires three. When Java sees a method call to `max()` elsewhere in the code, it will look at the number and types of arguments provided, and use that information to determine which version of `max()` it should use.


Of course, we could just use the three argument version of `max()` in both cases:

```java
public class Overloading{
  public static void main(String[] args){
    max(2, 3);
    max(3, 4, 5);
  }
  
  static void max(int x, int y){
    max(x, y, y);
  }
  
  static void max(int x, int y, int z){
    if(x >= y){
      if(x >= z){
        System.out.println(x);
      }else{
        System.out.println(z);
      }
    }else{
      if(y >= z){
        System.out.println(y);
      }else{
        System.out.println(z);
      }
    }
  }
}
```

In this case, we are calling the three parameter version of `max()` from within the two parameter version. In effect, this allows us to define _default parameters_ for methods such as this. If we only provide two arguments, the code will automatically call the three parameter version, filling in the third argument for us. 


## Variable Length Parameters

Finally, Java allows us to define a single parameter that is a _variable length parameter_. In essence, it will allow us to accept anywhere from 0 to many arguments for that single parameter, which will then be stored in an array. Let's look at an example:

```java
public class Overloading{
  public static void main(String[] args){
    max(2, 3);
    max(3, 4, 5);
    max(5, 6, 7, 8);
    max(10, 11, 12, 13, 14, 15, 16);
  }
  
  static void max(int ... values){
    if(values.length > 0){
      int max = values[0];
      for(int i : values){
        if(i > max){
          max = i;
        }
      }
      System.out.println(max);
    }
  }
}
```

Here, we have defined a method named `max()` that accepts a single variable length parameter. To show a parameter is variable length we use three periods `...` between the type and the variable name. We must respect three rules when creating a variable length parameter:

1. Each method may only have one variable length parameter
2. It must be the last parameter declared in the method declaration
3. Each argument provided to the variable length parameter must be the same type

So, when we run this program, we see that we can call the `max()` method with any number of integer arguments, and it will be able to determine the maximum of those values. Inside of the method itself, `values` can be treated just like an array of integers. 

## Try It!

Let's see if we can use this knowledge to build a program that uses both method overloading and variable length arguments. Here are the methods we'll need:

1. First, we'll create a method `printRepeat` that accepts two parameters. The first parameter is an integer, and the second is a string. The method will print the string as many times as specified in the integer parameter, one per line.
1. We'll also create another method named `printRepeat` that accepts three parameters, an integer and two strings. This method will repeatedly print the first string, followed by the second string, each on separate lines, as many times as indicated by the integer parameter. 
1. Then, we'll create one more method, `printVar` that accepts an integer as the first parameter, and then a variable length parameter of strings at the end. Then, it will repeatedly print each of the strings provided in the variable length parameter, one per line, repeating as many times as indicated by the integer parameter.
1. Finally, we'll need a `main()` method. It should use the methods defined above to print the word "Hello" 4 times, and then the lines "Good Morning" and "Good Afternoon" alternating one after the other, a total of 3 times each. Finally, it should print the lines "One", "Two" and "Three" 2 times. 

In each case, if the integer is $0$ or less than $0$, the method shouldn't print anything.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}