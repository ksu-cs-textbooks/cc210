---
title: "Array Length"
pre: "3. "
weight: 30
---

Arrays in Java have a fixed length, which is set when they are initialized. 

To get the length of an existing array, use the built-in `length` property:

```java
int[] a = new int[5];
boolean[] b = {true, false, true, false};

System.out.println(a.length); // 5
System.out.println(b.length); // 4
```

While it may seem obvious what the size of each array is in this example, there are many instances where we'll be given an array with unknown size from another piece of code. Similarly, as we start working with loops and arrays, we'll find that it is very useful to be able to access the length of the array directly. 