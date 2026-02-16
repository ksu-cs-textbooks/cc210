---
title: "Returning a Value"
pre: "4. "
weight: 40
---

Finally, we may also want to get a result back from our methods, especially if it is performing a calculation or some other task for us. So, we can use a special keyword known as `return` to provide a value as output from our method.  In general, if you call a method that returns a value, you want to catch that value in a variable.

Let's look at an example:

```java
public static void main(String[] args){
    output = max(5, 42, 3);
    System.out.println(output);
}

public static int max(int a, int b, int c){
    if (a >= b && a >= c){
        return a;
    } else if (b >= a && b >= c){
        return b;
    } else {
        return c;
    }
}
```

In this example, we have defined a method named `max` which will _return_ the largest value of its three parameters, `a`, `b`, and `c`. So, in our `main` method, we are calling `max` with arguments `5`, `42`, and `3`, which will be stored as `a`, `b`, and `c`, respectively. 

Then, in the `max` method, we use an **If-Else** statements to determine which one is larger than the other two, and then return that value. So, if we look closely at the code, we should be able to see that it will return `42` as the largest value. 

As we can see, our code can contain multiple `return` statements. However, the method will stop executing as soon as it reaches the first `return` statement, and will therefore only return a single value. This is really handy if we know the answer we need to output; we can just use the `return` keyword to stop what we are doing and provide the output.

So, once our `max` method is complete, the value `42` will be returned. In our `main` method, that value will be stored in the `output` variable. So, values returned from a method can be used in an assignment statement, just like any other value. In fact, we can treat a method call just like a variable! As soon as our program reaches a method call, it will stop what it is doing, execute the method, and replace the method call with the returned value. It's a really handy way to organize our code.

That covers the basics of how a method is created in our code. On the next few pages, we'll discuss some related topics that will help us understand how these methods work and how we can structure our code to take advantage of methods. 

