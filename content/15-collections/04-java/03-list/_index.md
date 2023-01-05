---
title: "List"
pre: "3. "
weight: 30
---

First, let's explore the simplest of these collections, the **list**. A list is defined as an ordered collection or sequence of elements, meaning that the order in which the elements were added to the list is preserved, but that order can be updated through the use of sorting algorithms. 

Lists are similar to arrays in many ways. The biggest difference in Java is that arrays must be declared with a static size that cannot be changed, whereas a list can hold any number of elements, even without knowing the number of elements it will contain ahead of time. 

In Java, the collections framework provides an abstract class `List<E>` that defines the operations a list should be able to perform. So, as we saw in an earlier module, we can store our lists in the datatype `List`, but we cannot instantiate that class directly because it is abstract.

There are many classes in the Java collections framework that extend the `List` abstract class. The two most important are the `ArrayList` and `LinkedList` classes. Thankfully, since they both inherit from the `List` class, we can use them interchangeably.

{{% notice info "Why Multiple List Implementations?" %}}

Java provides multiple versions of the list classes for one important reason: performance. Each version of the list class can perform the same operations and provide the same results, but because each one handles the underlying storage of data differently, the time it takes to perform those operations can vary widely.

To truly understand the difference requires a much deeper understanding of computer science than we are going to gain in this course alone. However, even novice programmers can **empirically** explore the difference to see which data structure is best for their program.

The key is to build a simple program that uses one of the list classes, performing the operations our actual program might perform. After doing a large number of those operations (say, over one million of them), we can record the amount of time that program took to complete. Then, we can repeat that same process for each different list class. The version that ran the quickest is probably the best choice for our needs. 

{{% /notice %}}

## Creating a List

To use lists in our program, we'll need to start by importing the appropriate libraries at the top of our file:

```java
import java.util.List;
import java.util.LinkedList;
import java.util.ArrayList;
```

To create a list, we can simply instantiate it just like any other object. However, since the Java lists use generics, we must also provide the type of data we'd like to store in the list inside of angle brackets `<>` as well.

For example, to create an `ArrayList` that stores whole numbers, or `int` values, we would do the following:

```java
List<Integer> intList = new ArrayList<Integer>();
```

Notice that we have to use the `Integer` type instead of `int`, because these lists can only store objects, not primitive data types. 

Similarly, to create a `LinkedList` that stores `String` objects, we could do this:

```java
List<String> stringList = new LinkedList<String>();
```

That's all there is to it!

## List Operations

The `List` class in Java defines several operations that each list class must be able to perform. The full list can be found on the [List](https://docs.oracle.com/javase/8/docs/api/java/util/List.html) page of the Java API documentation. Here are a few of the most important ones:

* `add(e)`---adds element `e` to the end of the list
* `add(index, e)`---adds element `e` to the specified `index` position in the list. All elements at that position and after are shifted toward the end of the list. 
* `contains(o)`---returns true if the object is contained in the list
* `get(index)`---gets the element in the list at the specified `index` position
* `indexOf(o)`---returns the first index that this object can be found in the list, or -1 if it is not found
* `isEmpty()`---returns true if the list contains 0 elements
* `remove(index)`---removes the element at the specified `index` position in the list
* `remove(o)`---removes the first occurrence of the given object from the list, if one exists.
* `set(index, element)`---replaces the element at `index` position in the list with the given `element`. 
* `size()`---returns the number of elements in the list
* `toArray()`---returns an array containing all elements in this list in order

## Iterating

What if we want to iterate through a list? Thankfully, we can use an **enhanced for** loop to do this, in the same way that we can iterate through an array:

```java
List<Integer> intList = new ArrayList<Integer>();
intList.add(5);
intList.add(3);
intList.add(7);
intList.add(2);
intList.add(4);

for(int x: intList){
  System.out.println(x);
}
```

## Sorting

To sort a list in Java, we can use the `Collections.sort()` method on the list itself. First, we'll need to import the Collections class at the top of the file:

```java
import java.util.Collections;
```

Then, we can use the `sort()` method in our code. This will sort the list in ascending order by default, but we can provide an optional parameter to sort in descending order as well:

```java
List<Integer> intList = new ArrayList<Integer>();
intList.add(5);
intList.add(3);
intList.add(7);
intList.add(2);
intList.add(4);

// sort in ascending order
Collections.sort(intList);

// sort in descending order
Collections.sort(intList, Collections.reverseOrder());
```

{{% notice note "List or an Array?" %}}

Consider a list when:
* the number of elements cannot be known at instantiation
* you want to access the elements using **integer** indexes, and you want the indexes to run contiguously from 0
* you want to be able to control the **order** of the elements (by sorting etc)
* the size of the collection can vary over the life of the program

Select an array when:
* the number of elements can be known at instantiation, or an upper limit used 
* you want to be able to have "empty" elements in the collection
* the size of the collection **cannot** vary over the life of the program

{{% /notice %}}

## Example

To explore how to use a list in a real program, let's look at a quick example program. Here's a short problem statement:

> Write a program that will accept a single integer as input, either from the terminal or by reading a file provided as the first command-line argument. If no command-line argument is provided, assume that input should be read from the terminal. If there are any errors opening a file provided as an argument or parsing the input, simply print "Invalid Input!" and terminate the program. If the provided integer is less than 3, it should also print "Invalid Input!".

> Using the integer provided as input, the program should generate a list of numbers representing the [Fibonacci sequence](https://en.wikipedia.org/wiki/Fibonacci_number) containing that many entries. 

> Before printing the list, the program should perform two additional operations on the list. First, if the integer provided as input is contained in the list, it should be removed. Secondly, the list should be presented in descending order, with the largest value first. 

> The program should print the list to the terminal, with each entry separated by a space. 

> The program should be implemented as two functions - a `main()` function that handles reading input, and a `makeList()` function that accepts a single integer as a parameter and returns the completed list of integers. 

{{% notice note "Fibonacci Sequence" %}}

The Fibonacci sequence is produced by adding the two previous numbers together to generate a new number. Traditionally, the first two Fibonacci numbers are `0` and `1`. So, the next number is `0 + 1 = 1`, and the number following that is `1 + 1 = 2`. The sequence continues indefinitely.

Formally, the Fibonacci sequence is defined as:

{{< math >}}
$$F_0 = 0$$
$$F_1 = 1$$
$$F_n = F_{n-1} + F_{n-2}$$
{{< /math >}}

You can find more information about the Fibonacci Sequence on [Wikipedia](https://en.wikipedia.org/wiki/Fibonacci_number).

{{% /notice %}}

For example, if the input provided is `8`, the program would begin by generating the first eight Fibonacci numbers, starting with `0` and `1`:

```tex
[0, 1, 1, 2, 3, 5, 8, 13]
```

Then, since `8` is contained in the list, it should be removed:

```tex
[0, 1, 1, 2, 3, 5, 13]
```

Finally, the list should be sorted in descending order, so the final list returned will be:

```tex
[13, 5, 3, 2, 1, 1, 0]
```

### `main` Function

So, let's build the program. We can start with this simple skeleton:

```java
import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;
import java.lang.ArrayIndexOutOfBoundsException;
import java.util.List;
import java.util.ArrayList;
import java.util.LinkedList;
import java.util.Collections;

public class ListExample{
  
  public static void main(String[] args){
    Scanner scanner;
    try{
      scanner = new Scanner(new File(args[0]));
    }catch(FileNotFoundException e){
      System.out.println("Invalid Input!");
      return;
    }catch(ArrayIndexOutOfBoundsException e){
      //no argument provided, read from terminal
      scanner = new Scanner(System.in);
    }
    
    try(
      Scanner reader = scanner
    ){
    
      int count = Integer.parseInt(reader.nextLine());
      if(count < 3){
        System.out.println("Invalid Input!");
        return;
      }
      
      List<Integer> list = makeList(count);
      
      for(int x : list){
        System.out.print(x + " ");
      }
      System.out.println();
      
    }catch(Exception e){
      System.out.println("Invalid Input!");
      return;
    }
  }
  
  public static List<Integer> makeList(int x){

    // MORE CODE GOES HERE
  
  }
}
```

This program contains a simple `main()` method that will handle reading and parsing the input from either the terminal or a file provided as a command-line argument. It will also verify that the input is an integer, and it is a value that is at least `3` or greater. If will then call the `makeList()` function using the input as a parameter to create the list. Finally, it will print the result using a simple **enhanced for** loop to iterate through the list and print each element followed by a space. We also must remember to print a newline at the end. Pretty nifty, right?

So, all we need to worry about implementing is the `makeList()` function.

### `makeList` Function

{{% youtube 8SXbDr0nZtQ %}}

[Video Materials]({{<relref "./video">}})

Let's dive into the `makeList()` function. First, we'll need to create a list. However, as we saw earlier, there are two different types of list we can use. For this example, let's just use an `ArrayList` of `Integers`, but we could just as easily use a `LinkedList` as well. So, the code would be as follows:

```java
public static List<Integer> makeList(int x){
  List<Integer> list = new ArrayList<Integer>();

}
```

Then, we'll need to add the first two items to the list, representing the first two Fibonacci numbers:

```java
public static List<Integer> makeList(int x){
  List<Integer> list = new ArrayList<Integer>();
  list.add(0);
  list.add(1);
}
```

Following that, we'll use a simple **for** loop to generate the next few numbers. We can either have separate variables to represent the previous values, or we can just read them directly from the list using the `get()` method:

```java
public static List<Integer> makeList(int x){
  List<Integer> list = new ArrayList<Integer>();
  list.add(0);
  list.add(1);
  for(int i = 2; i < x; i++){
    int newNumber = list.get(i-1) + list.get(i-2);
    list.add(newNumber);
  }
}
```

Once we've generated our list, we need to make sure `x` is not in the list. If so, we can just remove it. However, remember that there are two methods for removing an item from the list. If we just provide an `int` as an argument, it will call the version that removes the element at that _index_ in the list. Instead, we'll need to cast that `int` as an `Integer` so that it removes the _element_ with the value equal to `x`. Thankfully, if we use the `remove()` method on an item that isn't in the list, it won't do anything. 

```java
public static List<Integer> makeList(int x){
  List<Integer> list = new ArrayList<Integer>();
  list.add(0);
  list.add(1);
  for(int i = 2; i < x; i++){
    int newNumber = list.get(i-1) + list.get(i-2);
    list.add(newNumber);
  }
  list.remove((Integer)x);
}
```

Finally, we can use the `Collections.sort()` method to sort the list. We'll need to remember to include the optional parameter to sort in descending order. Once we've sorted the list, we can return it.

```java
public static List<Integer> makeList(int x){
  List<Integer> list = new ArrayList<Integer>();
  list.add(0);
  list.add(1);
  for(int i = 2; i < x; i++){
    int newNumber = list.get(i-1) + list.get(i-2);
    list.add(newNumber);
  }
  list.remove((Integer)x);
  Collections.sort(list, Collections.reverseOrder());
  return list;
}
```

That's all there is to it! See if you can complete the code in `ListExample.java` to the left, then use the two assessments below to check your program. 

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}