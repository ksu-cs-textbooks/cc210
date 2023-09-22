---
title: "Accessing Array Elements"
pre: "2. "
weight: 20
---

Once we've created our array, we can access individual array elements by placing the _index_ of that element inside of the square brackets `[]` following the variable name.

Array indexes in Java start at 0. So, to access the first element of an array named `x`, we would use `x[0]`.

Similarly, the last array index is one less than the total size of the array. If the array named `x` has a size of 5, then the last element would be `x[4]`.

Let's take a look at an example in the code below. It will create an array of 5 integers, assign those integers a value, then sum them up and print the result. 

```java  
public static void main(String[] args){
  //create an integer array
  int[] a = new int[5];

  //assign array elements
  a[0] = 5;
  a[1] = 10;
  a[2] = 15;
  a[3] = 20;
  a[4] = 25;

  //create a sum variable
  int sum = 0;

  //add up all the elements in the array
  sum = sum + a[0];
  sum = sum + a[1];
  sum = sum + a[2];
  sum = sum + a[3];
  sum = sum + a[4];

  //print the sum (it should be 75)
  System.out.println(sum);
}
```

Feel free to copy this code to a file named `Array.java` and modify the code to try other operations with arrays.

