---
title: "Call by Reference"
pre: "8. "
weight: 80
---

Finally, it is important to remember that any instantiated objects used as arguments to a method are passed in a _call-by-reference_ manner. So, any modifications to those objects made inside of a method will also be reflected in the code that called the method.

Here's a quick example:

```java
public class Reference{
  public int x;
}
```

```java
public class Main{
  public static void main(String[] args){
    Reference someRef = new Reference();
    someRef.x = 10;
    modify(someRef);
    System.out.println(someRef.x); // 15
  }

  public static void modify(Reference aRef){
    aRef.x = 15;
  }
}
```

As we can see, when we call the `modify()` function and pass a `Reference` object as an argument, we can modify the attributes inside of that object and see those changes back in the `main()` method after `modify()` is called. 

Of course, if we reassign the argument's variable to a new instance of `Reference` inside of the `modify()` function, then we won't see those changes in `main()` because we are dealing with a newly created object. 

So, we'll need to keep this in mind as we use objects as parameters and returned values in any methods we create in our programs.
