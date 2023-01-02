---
title: "Return"
pre: "4. "
weight: 40
---

{{% youtube cL5GHtZ7VUw %}}

[Video Materials]({{<relref "./video">}})

Lastly, one of the most useful things we can do with methods in our code is _return_ a value from a method. This allows us to use a method to perform an action or calculation that results in a single value that we can use elsewhere in our code. We can even use these method calls just like we use variables in other arithmetic expressions. Let's take a look at how that works.

## Returning a Value

To return a value from a method in Java, we use the special keyword `return`, followed by an expression representing the value we'd like to return. We must also declare the type of that value in our method declaration, taking the place of the `void` keyword we've been using up to this point. 

Here's an example program showing how to use the `return` keyword and store that returned value in a variable. 

```java
public class Return{
  public static void main(String[] args){
    int returnValue = last(1, 3, 5, 7, 9);
    System.out.println(returnValue);  // 9
  }
  
  static int last(int ... items){
    if(items.length > 0){
      return items[items.length - 1];
    }
    return -1;
  }
}
```

Let's review this program carefully to see what parts of the program are important for returning a value:

1. First, instead of `void`, we use the keyword `int` in the declaration of our `last()` method, `static int last(int ... items)`. This is because the method must return a value with the type `int`. 
2. Inside of the method, we see two instances of the `return` keyword. Each instance is followed by a value or expression that results in an integer, which is then returned from the method. As soon as the method reaches a `return` keyword, it immediately stops executing and returns that value. So, if the `items` variable length parameter is empty, the method will return $-1$. Otherwise, it will return the last item in the `items` parameter. 
3. In the `main()` method, we see that we've included the method call to `last()` on the right-hand side of a variable assignment statement. So, once we reach that line of code, the program will call the `last()` method and store the returned value in the `returnValue` variable in `main()`

## Compiler Messages

The Java compiler is a very crucial part of making sure that each method we create returns a value correctly. When we compile our code, the compiler checks to make sure that each method that includes a return type other than `void` will return a value along all code paths. That means that if one branch of an **If-Else** statement returns a value, then either the other branch or code below it should also return a value. 

In addition, it will make sure that the type of the value returned matches the type that is expected by the method's declaration. 

Finally, just like every other variable assignment in Java, when we store the result of a method call in a variable, Java will also make sure that the variable storing the value has a type that is compatible with the type being returned from the method.

So, if we receive error messages from the Java compiler regarding invalid return types or values in our methods, we'll need to carefully check our code to make sure we aren't violating one of those rules.

## Try It!

Let's try one more example, just to get some more experience building methods that return a value.

For this exercise, let's write a program that contains the following methods:

1. A `main()` method, just like always. This method should accept a single command-line parameter, which will be a random string containing both uppercase and lowercase letters. It should then use the method below to determine the total number of vowels (a, e, i, o, and u) in the input, including both uppercase and lowercase letters. If the parameter is not provided, just print `No input` and exit the program. 
2. A method `countLetters()` that accepts a String and a single character (type `char`) as parameters. The method should then return an integer that gives the number of times that exact character appears in the string in a case-sensitive way. If the character provided is lowercase, it should only count the lowercase versions of that character. 

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}