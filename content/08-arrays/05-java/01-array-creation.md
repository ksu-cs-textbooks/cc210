---
title: "Array Creation"
pre: "1. "
weight: 10
---

As with any variable in Java, we must declare an array variable before we can use it. 

## Array Declaration

To declare an array, we'll need to provide the _type_, a _variable name_, and _square brackets_ `[]` to denote that this variable is an array.

The preferred way of doing so is:
`<type>[] <variable_name>;`
as we can see in these examples:

```java
//integer array
int[] a;

//boolean array
boolean[] b;

//double array
double[] d;
```

We can create an array of an available type in Java, including all primitive data types and object types. We can even create our own classes and store objects created from those classes in an array.

One easy way to remember this syntax is to say "I'm creating an _int array_ named _a_ (`int[] a`)." Try saying it with the examples above!

There is an alternative syntax as well:

`<type> <variable_name>[];`

though it is rarely used in practice. It makes less sense to say "I'm creating an _int_ named _x array_," doesn't it?

## Array Initialization

Once we have declared an array, we can initialize it just like any other variable. In Java, use the `new` keyword to create an array. We'll also need to provide it with a _size_, which _must be a positive, whole integer_. 

The standard format for this is:

`<variable_name> = new <type>[<size>];`

as we can see in these examples:

```java
//integer array
int[] a;
a = new int[5];

//boolean array
boolean[] b;
b = new boolean[10];

//double array
double[] d;
d = new double[15];
```

Of course, we can combine both the declaration and initialization into a single statement:

```java
//integer array
int[] a = new int[5];

//boolean array
boolean[] b = new boolean[10];

//double array
double[] d = new double[15];
```

If we know the values we'd like to store in the array when we initialize it, we can use the shortcut syntax to build the array directly:

`<type>[] <variable_name> = {<item1>, <item2>, <item3>, ... , <itemN>}`

as we can see in these examples:

```java
//integer array
int[] a = {1, 2, 3, 4, 5};

//boolean array
boolean[] b = {true, false, true, false};

//double array
double[] d = {1.2, 2.3, 3.4};
```

Otherwise, we can store items individually in the array, as we'll see in the next page. 

## `new` Keyword

The keyword <b>new</b> is used to create a object.  Objects are a collection of data and the methods used to access and manipulate that data. 

When you <b>instantiate</b> (the technical term for create) an object, a memory cubby hole, is created and given that name.  You may then use various methods to assign, manipulate and change the data it holds.  In general you must use **new** to get a distinct object in memory.

1. In the figure below we first instantiate the int-array "a". 
1. On line 2 we assign the int-array "b" the value of "a". Note that we did not use **new**, so no new array was set up.  Instead "b" simply points to "a", "b" has become an _alias_ for "a".
1. On line 3, since "a" and "b" are the same object, assigning "0" to b[0] is the same as assigning 0 to a[0].
1. On line 4 we instantiate a new array for "b".

![Object creation flow chart](/images/08-array/arrays_obj_memory.png)


{{% notice info "Why Don't Arrays Use the New Keyword?" %}}

Arrays as data types pre-date object oriented languages by several decades, they are one of the oldest aggregate data types.  So when Java appears on the scene in the 1990s, they adopted the "C-style" array definition syntax `int[] a = {...}` in addition to the more conventional `int[] a = new int[]`.  Most object oriented languages will have some type of "syntactic sugar", or short-hand syntax, for array and list creation.

{{% /notice %}}






