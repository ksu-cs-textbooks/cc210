---
title: "Maps"
pre: "4. "
weight: 40
---

Next, let's explore another important collection, the **map**. Some programming languages, such as Python, refer to this collection as a **dictionary** as well. 

A map is a collection that associates, or _maps_, a **key** to a **value**. To store something in a map, we must provide a unique **key** for each value. If we provide a key that is already in use, the value stored by that key is overwritten. Then, to retrieve a value, we simply provide the key that is associated with that value.

This is very similar to how arrays work, where each element in the array can be accessed using an array index. The biggest difference is that keys in a map can be _any_ value, not just an integer, and likewise the values can be _any_ type of value. 

In Java, the collections framework provides an abstract class `Map<K, V>` that defines the operations a list should be able to perform. So, as we saw in an earlier module, we can store our maps in the datatype `Map`, but we cannot instantiate that class directly because it is abstract.

There are many classes in the Java collections framework that extend the `Map` abstract class. The most commonly used version is the `HashMap` and `LinkedList` class. 

## Creating a Map

To use a map in our program, we'll need to start by importing the appropriate libraries at the top of our file:

```java
import java.util.Map;
import java.util.HashMap;
```

To create a map, we can simply instantiate it just like any other object. However, since the Java maps use generics, we must also provide the data types for both the keys and values inside of angle brackets `<>` as well.

For example, to create a `HashMap` that associates `String` keys with `Double` values, we would do the following:

```java
Map<String, Double> aMap = new HashMap<String, Double>();
```

Notice that we have to use the `Double` type instead of `double`, because these maps can only store objects, not primitive data types, just like `Lists`. 

That's all there is to it!

## Map Operations

The `Map` class in Java defines several operations that each map class must be able to perform. The full list can be found on the [Map](https://docs.oracle.com/javase/8/docs/api/java/util/Map.html) page of the Java API documentation. Here are a few of the most important ones:

* `put(k, v)`---associate the value `v` with the key `k` in the map
* `get(k)`---return the value associated with the key `k` in the map
* `size()`---returns the number of key and value associations in the map
* `containsKey(k)`---returns `true` if the map contains an associated value for the given key `k`
* `containsValue(v)`---returns `true` if one or more keys in the map are associated with the given value `v`

## Iterating

What if we want to iterate through a map? That is a bit tricky, but it can be done. To do this, we'll use an **enhanced for** loop, which will use the special `Map.Entry` class to represent each entry. The code for doing this is shown here:

```java
Map<String, String> mapIter = new HashMap<String, String>();
mapIter.put("One", "Uno");
mapIter.put("Two", "Dos");
mapIter.put("Three", "Tres");
mapIter.put("Four", "Quatro");

for(Map.Entry<String, String> entry : mapIter.entrySet()){
  System.out.println("Key: " + entry.getKey());
  System.out.prinltn("Value: " + entry.getValue());
}
```

However, in most cases, it doesn't make much sense to iterate through a map, since that isn't what it is designed for. Instead, we may want to consider using some sort of a list instead. 


{{% notice info "Map or List?" %}}

Consider a map when:
* you want to use something other and integers as the index (key) 
* you don't care about the order the elements are yielded (provided) by iteration

{{% /notice %}}

## Example

To explore how to use a map in a real program, let's look at a quick example program. Here's a short problem statement:

> Write a program that will read multiple lines of input, either from the terminal or by reading a file provided as the first command-line argument. If no command-line argument is provided, assume that input should be read from the terminal. If there are any errors opening a file provided as an argument or parsing the input, simply print "Invalid Input!" and terminate the program. 

> The program will store a map that associates lines of input with random integers.

> When a line of input is read, the program will check to see if that line has already been used as a key in the map. If so, it will return the value associated with that key.

> If the map does not contain an entry for that key, the program should generate a new random integer and store it in the map, using the input line as the key. 

> The program should be implemented as two functions - a `main()` function that handles reading input, and a `getOutput()` function that accepts a string as a parameter and returns the associated number for that string. It should also use a global variable to store the map. 

For example, let's say the program receives the following input:

```tex
cat
dog
horse
dog
cat
```

One possible output could be:

```
12334512345
239487234
234234
239487234
12334512345
```

Notice that the lines of output correspond with the lines of input, such that the program returns the same value each time it reads the word `cat`. 

### `main` Function

So, let's build the program. We can start with this simple skeleton:

```java
import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;
import java.lang.ArrayIndexOutOfBoundsException;
import java.util.Map;
import java.util.HashMap;
import java.util.Random;

public class MapExample{
  
  public static Map<String, Integer> map;
  public static Random random;
  
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
    
      while(reader.hasNext()){
        String inp = reader.nextLine();
        int output = getOutput(inp);
        System.out.println(output);
      }
      
    }catch(Exception e){
      System.out.println("Invalid Input!");
      return;
    }
  }
  
  public static int getOutput(String inp){

    // MORE CODE GOES HERE
  
  }
}
```

This program contains a simple `main()` function that will handle reading and parsing the input from either the terminal or a file provided as a command-line argument. When it reads a line of input, it will use the `getOutput()` function to get the associated output for that input, and then print it to the terminal.

The program also includes a global static field to store the map. We also do the same for a `Random` object to generate random numbers. In that way, we can use the same objects in both functions without having to pass them around as arguments. 

So, all we need to worry about implementing is the `getOutput()` function.

### `getOutput` Function

{{< youtube cprt3TVt_7c  >}}

[Video Materials]({{% relref "./video" %}})

Let's dive into the `getOutput()` function. First, we'll need to see if the `map` and `random` objects have been initialized. We can do that by checking to see if they are equal to `null`. If so, we'll initialize them:

```java
public static int getOutput(String inp){
  if(map == null){
    map = new HashMap<String, Integer>();
  }
  if(random == null){
    random = new Random();
  }
}
```

Then, we'll need to see if the map contains a value for the string provided as input. If so, we can just return that value:

```java
public static int getOutput(String inp){
  if(map == null){
    map = new HashMap<String, Integer>();
  }
  if(random == null){
    random = new Random();
  }
  if(map.containsKey(inp)){
    return map.get(inp);
  }
}
```

However, if the map does not contain a value for that key, we must generate a new one, store it in the map, then return it:

```java
public static int getOutput(String inp){
  if(map == null){
    map = new HashMap<String, Integer>();
  }
  if(random == null){
    random = new Random();
  }
  if(map.containsKey(inp)){
    return map.get(inp);
  }else{
    int newNumber = random.nextInt();
    map.put(inp, newNumber);
    return newNumber;
  }
}
```

That's all there is to it! See if you can complete the code in `MapExample.java` to the left, then use the two assessments below to check your program. 
