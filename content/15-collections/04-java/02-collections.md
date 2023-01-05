---
title: "Collections"
pre: "2. "
weight: 20
---

The Java API contains several different classes specifically designed to store data. All together, we usually refer to these classes as the **collections framework** since they are used to store a "collection" of data.

The Java collections framework contains implementations for several different **data structures**, which are classes used to store and manipulate data in specific ways. We'll learn more about how each of these implementations works and differs in a later course, but in this course, we'll quickly describe a few of the most common ones. Specifically, we'll discuss these two data structures:

* Lists
* Maps

We'll also learn how to build our own `Tuple` objects in Java, since Java doesn't include tuples in the language or the Java API library directly, but they are very useful objects to have in our programs.

## Generics

As we've already learned, the Java programming language requires us to declare the type of each variable we are using before we can even compile the code. However, this can make it very difficult to enforce type-safety when working with collections, since each collection could only guarantee that an item was a subclass of `Object`, the base class for all classes in Java. 

Java 5 added support for **generics**, a method of programming that allows us to be a bit more flexible in the way we handle types. In short, when developing a collection, we can specify that each item in the collection must be an object compatible with a given, but unknown type. Then, when we use that collection in our code, we can specify the specific type we intend to store in the collection, and the Java compiler will be able to automatically enforce those type rules as if we originally wrote the collection class to only store items of that type.

For example, Java uses a class `List<E>` to represent a list that stores elements of some class `E`. We don't know what that class is at first, but we can still write our `List` class as if it is a specific type.

Then, when we instantiate a `List` object in our code, we can provide a type of item we'd like to store, such as `String`. So, we'd now have a class `List<String>` which represents a list of strings. This allows the Java compiler to make sure that we are only storing strings in the list. In addition, it allows us to automatically treat each item retrieved from the list as a string, without any additional conversion required. 

We'll see how to do this in code on the next page. 

To learn more about how Java handles Generics, check out [Lesson: Generics](https://docs.oracle.com/javase/tutorial/java/generics/index.html) in the Java Tutorials from Oracle.

## Primitives vs. Objects

One last thing that we must discuss related to Java and collections is the difference between primitive data types and objects. As we've already learned in this course, Java contains several primitive data types, such as `int`, `double`, `boolean`, and more. However, if we wish to store items of these primitive types in our collections, we'll quickly run into a problem. This is because the primitive data types aren't actually objects, and because of that, they don't follow the rules needed to allows generics to work.

Thankfully, Java has a quick and easy workaround. Java includes classes `Integer`, `Double`, and `Boolean` to represent objects that store a single value of the corresponding primitive data type. In addition, Java will automatically convert data between the two in some situations, using a process called **autoboxing** and **unboxing**. You can find more on the [Autoboxing and Unboxing](https://docs.oracle.com/javase/tutorial/java/data/autoboxing.html) Java Tutorial from Oracle. We'll see how this works on the next page as well