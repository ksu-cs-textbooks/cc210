---
title: "Multidimensional Arrays"
pre: "4. "
weight: 40
---

To create a multidimensional array in Java, simply provide additional square brackets `[]` as part of the array declaration. Similarly, when we initialize the array, we'll need to provide a length for each dimension of the array:

```java
//2d integer array
int[][] a = new int[5][5];

//3d boolean array
boolean[][][] b = new boolean[2][4][8];

//4d double array
double[][][][] c = new double[5][4][6][2];
```

We can also directly initialize the array elements, just as we did before. We'll need to include additional curly braces `{}` for each dimension:

```java
//2d integer array
int[][] a = {{1, 2}, {3, 4}, {5, 6}};
```

Typically, multidimensional arrays will only have 2 or 3 dimensions, but Java will allow up to 255 dimensions.

Each of the examples above will create a multidimensional array with each dimension consisting of arrays of the same length. However, it is possible to have arrays of different length within the same dimension, though it can be much more difficult to manage that scenario. We won't deal with that in this course, but it may be useful in some situations.

To get the size of each dimension, we can use the `length` property on an element at that dimension:

```java
//2d integer array
int[][] a = {{1, 2}, {3, 4}, {5, 6}};

System.out.println(a.length); // 3
System.out.println(a[0].length); // 2
```

Of course, we'll need to make sure that `a[0]` exists before trying to find its length. If not, it will cause an error.

To access or assign elements in a multidimensional array, add additional square brackets `[]` for each dimension:

```java
//2d integer array
int[][] a = {{1, 2}, {3, 4}, {5, 6}};

a[0][1] = 10;

System.out.println(a[0][1]); // 10
System.out.println(a[1][1]); // 4
System.out.println(a[2][0]); // 5
```

Again, remember that the indexes in each array dimension begin at 0. So, `a[1][1]` is actually accessing the second element in the first dimension of `a`, which is an array containing `{3, 4}`, and then the second element in that array, which is `4`.