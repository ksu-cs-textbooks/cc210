---
title: "Call by Reference vs. Value"
pre: "4. "
weight: 40
---

{{< youtube 5gyV1KqWaSU  >}}

[Video Materials]({{% relref "./video" %}})

As we start creating objects, one major concept is how objects are handled differently than "primitive" data types when used as arguments; i.e. when passed to functions. Typically, there are two scenarios: _call by value_ and _call by reference_. Let's discuss them both in detail to understand how they differ and the impact that may have on our code.

## Call by Value

When method parameters are handled in a _call by value_ way, that means that each time we call the method, that method gets a unique copy of the parameter. So, any changes made to that parameter won't be reflected in the code from which the method was called.

Let's look at an example:

```java
public static void main(String[] args){
  int x = 5;
  int y = addThree(x);
  System.out.println(x);
  System.out.println(y);
}

public static int addThree(int x){
  x = x + 3;
  return x;
}
```

In this code, we initialize the variable `x` to the value {{< math >}}$ 5 ${{< /math >}}. Then, we pass that value as an argument to the method `addThree`, where it is stored in the parameter named `x`. Inside of that method, we add {{< math >}}$ 3 ${{< /math >}} to that variable, then return its new value.

Back in the main method, when we print the value of `x`, it will still be {{< math >}}$ 5 ${{< /math >}}. Why? Since this method is using _call by value_, the method `addThree` gets a _copy_ of the value stored in `x`, which it stores in its own variable. So, when the method updates the value in `x` it is only changing the value in it's copy. The original value from the `main` method is unchanged. 

However, the value `y` in the main method stores the value returned by `addThree`, which is {{< math >}}$ 8 ${{< /math >}}. So, when we print that value, we'll get {{< math >}}$ 8 ${{< /math >}} as expected.

## Call by Reference

If a method handles parameters in a _call by reference_ way, the method simply gets a _reference_, sometimes called a _pointer_, to the value passed as an argument. In that way, when it changes the value of that argument, it is also changing the value of the original variable passed in as that argument. 

Here's another example:

```java
public static void main(String[] args){
  int[] x = {1, 2};
  changeLast(x);
  System.out.println(x[0]);
  System.out.println(x[1]);
}

public static void changeLast(int[] x){
  x[1] = 5;
}
```

In this example, we are creating an array named `x` in the `main` method, which stores two values, {{< math >}}$ 1 ${{< /math >}} and {{< math >}}$ 2 ${{< /math >}}. Then, we use the `changeLast` method to change the last element in the array to {{< math >}}$ 5 ${{< /math >}}. Notice that we are providing the array `x` as an argument to the `changeLast` method, but that method does not return a value.

When we print the first element of `x`, it is {{< math >}}$ 1 ${{< /math >}} as expected. However, when we print the second element of `x`, we see that it is now {{< math >}}$ 5 ${{< /math >}}, even in the `main` method. Why? This is because the method `changeLast` is using _call by reference_, so instead of getting a copy of the variable `x`, it actually gets a _reference_ to where that array is stored in the `main` method. Therefore, any changes made to `x` in `changeLast` also affect the value in `main`

### Reassignment

However, it is very important to know that we cannot reassign the value of a variable passed using _call by reference_ and expect it to work the way we want. Here's an example:

```java
public static void main(String[] args){
  int[] x = {1, 2};
  changeLast(x);
  System.out.println(x[0]);
  System.out.println(x[1]);
}

public static void changeLast(int[] x){
  x = {3, 4};
}
```

In this instance, we are _reassigning_ the variable `x` inside of `changeLast` to an entirely new array. By doing so, we are changing the _reference_ that it uses to point to the new array. The old array still exists, and the variable `x` in `main` still refers to that array. So, when we print the values of `x` in `main`, we'll get {{< math >}}$ 1 ${{< /math >}} and {{< math >}}$ 2 ${{< /math >}}, since they haven't changed.

In the example above that worked, we are simply changing a value inside of the array, not reassigning the array itself. 

## Different Scenarios

Unfortunately, it can be very difficult to tell on the surface which parameter handling method is being used by a particular piece of code, especially pseudocode. Each language handles this a bit differently, so we'll have to carefully read our language's documentation to know for sure. Later in this chapter we'll discuss the specifics for the language we are using. 

However, there are some general rules that we can follow that work in most cases:

1. Simple data types, such as ints, floats, booleans, etc., are typically passed using _call by value_. Any changes to their value will not be seen outside of the method.
2. Other data types, such as arrays, lists and objects are typically passed using _call by reference_. If the object can be modified, those changes will appear outside of the method. However, if the parameter is reassigned, it will not affect the outside reference

When in doubt, we can always write a simple test program in any language to check and see how parameters are handled. 