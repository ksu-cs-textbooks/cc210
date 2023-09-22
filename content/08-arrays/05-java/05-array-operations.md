---
title: "Array Operations"
pre: "5. "
weight: 50
---

We've already covered one of the operations we can perform on an array, `length`. Let's look at one more.

### Copying Arrays

Java has a built-in method to copy sequential elements from one array to another: 

```java
System.arraycopy(source, sourcePosition, destination, destinationPosition, length)
```

Just like the method we use to print to the terminal, `System.out.println`, this is just another method that is available in `System` that we can use in our code. 

That method accepts 5 inputs:
* **source** - The array containing the elements to be copied
* **sourcePosition** - An integer giving the starting position of elements to be copied from the source array
* **destination** - An array to copy elements into
* **destinationPosition** - An integer giving the starting position for elements to be copied to the destination array
* **length** - The number of elements to be copied

The source and destination arrays must store compatible data types. Likewise, if we give a length which tries to copy too many elements from the source array, or if it goes past the end of the destination array, an error will occur. 

Here is an example of how it can be used to copy elements from one array to another:

```java
int[] a = {1, 2, 3, 4, 5, 6, 7};
int[] b = new int[3];

System.arraycopy(a, 1, b, 0, 3);

System.out.println(b[0]); // 2
System.out.println(b[1]); // 3
System.out.println(b[2]); // 4
```

To learn more about this method and how to use it, consult the official Java documentation linked below. 

**Reference:** [System.arraycopy](https://docs.oracle.com/javase/8/docs/api/java/lang/System.html#arraycopy-java.lang.Object-int-java.lang.Object-int-int-)