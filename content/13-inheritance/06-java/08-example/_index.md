---
title: "A Worked Example"
pre: "8. "
weight: 80
---

Now that we've seen how to build classes that can inherit attributes and methods from other classes, let's work through a simple example program together to see how it all works in practice. The code in this program will be very simple, because the purpose is to explore how we can use the structure of inheritance in our programs. 

## Problem Statement

First, let's start with a problem statement. In this problem, we are going to build a program that will help us find an object in a toolbox based on several criteria provided from the user. To represent the objects in the toolbox, we'll use a structure of class inheritance as shown in the UML diagram below:

![Tool Example UML Diagram](/images/13-inherit/12.7.j.8.uml.png)

_Right-click image and choose "Open image in new tab" or similar to view larger version_

The completed program should be able to perform the following steps:

1) When the program is executed, a single command-line argument should be provided. That argument will be the path to a file containing descriptions for each tool in the toolbox. If the argument is not provided, or the input file cannot be successfully read or parsed, the program should print "Invalid Input" and terminate. 
2) The input file will contain at least two lines of input. The first line will give the number of tools included in the input file as an integer. Each subsequent line will identify a particular tool using the name of the class representing the tool, followed by values for each attribute of the tool. The values will be separated by spaces, and listed in the same order as those attributes are accepted in the tool's constructor. 
3) Once the input is read, the program will then accept a query as input via the terminal. That input should consist of multiple parts on a single line, separated by a space. The first part will be the name of an action that needs to be performed, and then following that will be one or more values to be provided to that action as arguments, separated by spaces. 
4) The program will review its list of available tools, finding any tool that supports that action. It will then call the method in that tool that corresponds with the action (the method and action names will be the same), providing the specified values as arguments. If the tool responds with `true` to that method call, then that tool is able to perform that action. The program should print the description of the appropriate tool to the terminal and terminate. In this example, each query will only result in one matching tool, if any. 
5) If a matching tool cannot be found, or there are any errors reading the input from the terminal, the program should print "Invalid Tool" and terminate. 

For example, here's a sample input file that could be provided to this program:

```tex
3
AdjustableWrench 170 10 25
CombinationWrench 135 8
CrossCutSaw 350 wood:drywall
```

Then, if the user inputs the following query:

```tex
tighten 150 8
```

The program will respond with the following output:

```tex
CombinationWrench Length: 135 Size: 8
```

Let's walk through this program step by step and see how we need to build it.

## `Tool` Class

{{% youtube bjnVaGbjDZw %}}

[Video Materials]({{<relref "./video">}})

First, we can start with the `Tool` class. Looking at the UML diagram, we see that the `describe()` method is in italics, meaning it should be an abstract method. Likewise, we see that the constructor is protected, so the class cannot be instantiated directly. Both of those help us realize that the entire `Tool` class should be abstract. So, we can easily create it and define the constructor and the `describe()` method in code:

```java
public abstract class Tool{

  protected Tool(){
    // do nothing
  }
  
  public abstract String describe();
  
}
```

That's really it! In many cases, the base class includes very little, if any, content or code. Instead, it simply gives us a shared starting point for the other classes in this program, and defines a single method, `describe()`, that each child class must implement.

## `Wrench` and `Saw` Classes

Next, we can go down a level and implement the `Wrench` and `Saw` classes. Each of these classes contains a single attribute with a getter method. They also each contain a protected constructor, and an abstract method defining what each type of tool can do. Since neither of these classes implements the `describe()` method, even though they inherit from `Tool`, they will also be abstract. So, the code for these classes will be very similar to what we already created for the `Tool` class:

```java
public abstract class Wrench extends Tool{

  private int length;
  
  protected Wrench(int length){
    this.length = length;
  }
  
  public int getLength(){ return this.length; }
  
  public abstract boolean tighten(int clearance, int size); 
  
}
```

```java
public abstract class Saw extends Tool{

  private int length;
  
  protected Saw(int length){
    this.length = length;
  }
  
  public int getLength(){ return this.length; }
  
  public abstract boolean cut(int length, String material); 
  
}
```

As we can see in the code above, these classes are nearly identical, differing only in the name of the class and the method signatures of the different abstract methods. 

At this point, we can quickly check our program structure to make sure everything is built correctly so far. Use the assessment below to confirm that your program structure is correct before continuing. 

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

## `AdjustableWrench` Class

{{% youtube 2FCtZ0ZeJHY %}}

[Video Materials]({{<relref "./video">}})

Next, let's look at one of the child classes of `Wrench`. As we can see in the UML diagram above, this class has both a `min_size` and a `max_size` attribute that are set through the constructor, as well as getter methods for each one. So, most of the code for this class is already pretty straight forward, just based on the structure of the class alone.

```java
public class AdjustableWrench extends Wrench{

  private int min_size;
  private int max_size;
  
  public AdjustableWrench(int length, int min_size, int max_size){
    super(length);
    this.min_size = min_size;
    this.max_size = max_size;
  }
  
  public int getMinSize(){ return this.min_size; }
  public int getMaxSize(){ return this.max_size; }
  
  // other methods go here

}
```

So, that just leaves the `describe()` and `tighten()` methods. Let's tackle `describe()` first. In the example above, we see that the `describe()` method seems to just print the name of the class, followed by each attribute's name and value. So, we can pretty easily implement that method in code:

```java
public String describe(){
  return String.format("AdjustableWrench: Length: %d MinSize: %d MaxSize: %d", this.length, this.min_size, this.max_size);
}
```

However, if we try to compile this code, we'll get an error message:

```tex
AdjustableWrench.java:16: error: length has private access in Wrench
    return String.format("AdjustableWrench: Length: %d MinSize: %d MaxSize: %d", this.length, this.min_size, this.max_size);
                                                                                     ^
2 errors
```

You can see for yourself by trying to compile your code at this point. You should get a similar message (you'll probably see another stating that we haven't implemented `tighten()` yet, which is expected).

Looking at the UML diagram above, we see that the `length` attribute in the parent `Wrench` class is indeed private instead of protected. So, we'll need to use the getter method `getLength()` to get that value instead:

```java
public String describe(){
  return String.format("AdjustableWrench: Length: %d MinSize: %d MaxSize: %d", this.getLength(), this.min_size, this.max_size);
}
```

That should fix the error! You can try it with the button above after making the change. We'll still get an error about not implementing `tighten()`, which is the last step in building this class.

The `tighten()` method should determine whether this wrench is able to tighten the item described. To really understand what we are dealing with, we must understand what an adjustable wrench looks like. Here's a picture of one from the real world:

![Adjustable Wrench](/images/13-inherit/12.7.x.8.adjustable_wiki.png)[^2]

[^2]: https://en.wikipedia.org/wiki/File:AdjustableWrenchWhiteBackground.jpg

The function accepts two parameters: a clearance value, which shows how much room between the item and the surrounding equipment there is, and the size of the item to be tightened itself. So, we know that if our wrench is shorter than the clearance, and supports an item of the given size, we'll be able to tighten it. 

An adjustable wrench has a head that can be adjusted to multiple sizes, so as long as the size given is between the minimum and maximum size our wrench is able to tighten, we can return true. So, to put that into code:

```java
public boolean tighten(int clearance, int size){
  return clearance >= this.getLength() && size >= this.min_size && size <= this.max_size;
}
```

As you may recall from an earlier module, we can directly return the result of a Boolean logic expression, so that makes this method even simpler. 

## `CombinationWrench` and `OpenEndWrench` Classes

Now that we've written the code for the `AdjustableWrench` class, it should be pretty simple to write the code for the other two types of wrenches.

First, a `CombinationWrench`, which typically only supports one size of bolt or nut. It typically looks like this.

![Combination Wrench](/images/13-inherit/12.7.x.8.combination_wiki.jpg)[^3]

[^3]: https://en.wikipedia.org/wiki/File:Kluc_ockoplochy.jpg

So, the `tighten()` method must simply check the clearance and the size of the item provided against the size of the wrench. Here's the code for that class:

```java
public class CombinationWrench extends Wrench{
  
  private int size;
  
  public CombinationWrench(int length, int size){
    super(length);
    this.size = size;
  }
  
  public int getSize(){ return this.size; }
  
  public String describe(){
    return String.format("CombinationWrench Length: %d Size: %d", this.getLength(), this.size);
  }
  
  public boolean tighten(int clearance, int size){
    return clearance >= this.getLength() && size == this.size;
  }
}
```

The other type of wrench, an `OpenEndWrench`, typically has two heads of different size on either end:

![Open End Wrench](/images/13-inherit/12.7.x.8.openend_wiki.jpg)[^4]

[^4]: https://en.wikipedia.org/wiki/File:Cl%C3%A9_plate.jpg

So, it can tighten bolts or nuts of two different sizes. Therefore, the `tighten()` method must determine if either size is applicable to the bolt or nut to be tightened. The code for that class is as follows:

```java
public class OpenEndWrench extends Wrench{
  
  private int size_one;
  private int size_two;
  
  public OpenEndWrench(int length, int size_one, int size_two){
    super(length);
    this.size_one = size_one;
    this.size_two = size_two;
  }
  
  public int getSizeOne(){ return this.size_one; }
  public int getSizeTwo(){ return this.size_two; }
  
  public String describe(){
    return String.format("OpenEndWrench Length: %d SizeOne: %d SizeTwo: %d", this.getLength(), this.size_one, this.size_two);
  }
  
  public boolean tighten(int clearance, int size){
    return clearance >= this.getLength() && (size == this.size_one || size == this.size_two);
  }
}
```

That's really it! As we can see, while there is quite a bit of code in this program, much of the code is very similar between classes. We're simply implementing the important bits and pieces of each class, with a slightly different implementation of the `describe()` and `tighten()` methods in each one. 

At this point, we can check our code to confirm that the structure is correct. Use the assessment below to check your program's structure before continuing.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

## `CrossCutSaw` Class

{{% youtube G5-c_uJTh0w %}}

[Video Materials]({{<relref "./video">}})

The `CrossCutSaw` class is very similar to the classes we created for the different type of wrenches above. The only difference is that it uses a `cut()` method to determine if the saw is able to cut the material described when we call that method. 

First, let's look at the rest of the code for that class. In the constructor, we are given a string that contains a list of materials that can be cut by the saw, separated by colons. So, we'll need to use the [`String.split()` method](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#split-java.lang.String-) to split that string into an array of strings to be stored in the class's `materials` attribute.

Likewise, since the `getMaterials()` method should return a simple string, we can use the [`String.join()` method](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#join-java.lang.CharSequence-java.lang.Iterable-) to make a string out of the array, with each element separated by a comma followed by a space. Finally, we can use that to help populate the `describe()` method.

```java
public class CrossCutSaw extends Saw{
  
  private String[] materials;
  
  public CrossCutSaw(int length, String materials){
    super(length);
    this.materials = materials.split(":");
  }
  
  public String getMaterials(){ return String.join(", ", this.materials); }
  
  public String describe(){
    return String.format("CrossCutSaw Length: %d Materials: %s", this.getLength(), this.getMaterials());
  }
  
  // additional methods here
}
```

{{% notice info "Why Not Just Return an Array?" %}}

# Why Not Just Return an Array?

It might be tempting to have the `CrossCutSaw` class simply accept an array of materials in the constructor, and then return that array in the `getMaterials()` method. However, recall that arrays are complex data type that are handled using call by reference. So, that leaves this class vulnerable to manipulation from an external code source.

For example, if the `Main` class gives an array of materials to `CrossCutSaw` via the constructor, we could simply store the reference to that array in our `materials` attribute. However, if `Main` proceeds to change some of the elements in the array, it would also update the array referenced by this class. Likewise, any code that calls the `getMaterials()` method would also get a reference to the same array. 

By creating our own array in the constructor, and then only returning a newly formed string each time a class calls the `getMaterials()` method, we can protect our data from malicious changes. 

An alternative method would be to create a _deep copy_ of the array and store that copy in this class. We haven't discussed how to do that in this course, but a future course on data structures will cover that process in depth.

{{% /notice %}}

The `CrossCutSaw` has two more methods that we'll need to implement: `cut()` and `findMaterial()`. The `findMaterial()` method is a private method that allows us to search the array of materials that can be cut by this `CrossCutSaw` object, and simply return a boolean value if the provided material is in the list. So, let's address that method first.

```java
private boolean findMaterial(String material){
  for(String m : this.materials){
    if(m.equals(material)){
      return true;
    }
  }
  return false;
}
```

This method simply iterates through each material in the `materials` array, and returns true if it finds a material that exactly matches the material provided as a parameter. If it can't find a match and reaches the end of the list, then the method will return `false`. 

We can then use this method in our `cut()` method to determine whether the given material can be cut by this saw:

```java
public boolean cut(int length, String material){
  return length < this.getLength() && this.findMaterial(material);
}
```

This method will simply return `true` if the length of the item to be cut is shorter than the saw and the material of the item is contained in the list of materials that can be cut by this saw. That covers the `CrossCutSaw` class. 

## `HackSaw` Class

The `HackSaw` class is very similar to the `CrossCutSaw` class. However, instead of having a list of materials that it can cut, a `HackSaw` can only cut a single material: metal. So, we can just hard-code that material into the saw's class, as shown in the code below:

```java
public class HackSaw extends Saw{
  
  public HackSaw(int length){
    super(length);
  }
  
  public String describe(){
    return String.format("HackSaw Length: %d Material: metal", this.getLength());
  }
  
  public boolean cut(int length, String material){
    return length < this.getLength() && material.equals("metal");
  }
}
```

That's all there is to it! At this point, we can check our code to confirm that the structure is correct. Use the assessment below to check your program's structure before continuing.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

## `Main` Class

{{% youtube 49PT8-SrZxs %}}

[Video Materials]({{<relref "./video">}})

Finally, we need to create a few methods in the `Main` class to build the actual logic for our program. Before we build the `main()` method, let's look at the other two methods.

First, the `readInput()` method should receive the name of a file as a string, and then return an array of tools that represents the tools specified in the given file. Also, looking at the UML diagram above, that method should be static, since it is underlined. In fact, all of the methods in the `Main` class are static, so we can call them directly without instantiating an object using the `Main` class. 

```java
import java.util.Scanner;
import java.nio.file.Paths;
import java.lang.Exception;

public class Main{
 
  // other methods go here
  
  public static Tool[] readInput(String filename){
    try(
      Scanner scanner = new Scanner(Paths.get(filename))
    ){
      int num_tools = Integer.parseInt(scanner.nextLine());
      Tool[] tools = new Tool[num_tools];
      for(int i = 0; i < num_tools; i++){
        String[] line = scanner.nextLine().split(" ");
        int length = Integer.parseInt(line[1]);
        if(line[0].equals("AdjustableWrench")){
          int min_size = Integer.parseInt(line[2]);
          int max_size = Integer.parseInt(line[3]);
          tools[i] = new AdjustableWrench(length, min_size, max_size);
        }else if(line[0].equals("OpenEndWrench")){
          int size_one = Integer.parseInt(line[2]);
          int size_two = Integer.parseInt(line[3]);
          tools[i] = new OpenEndWrench(length, size_one, size_two);
        }else if(line[0].equals("CombinationWrench")){
          int size = Integer.parseInt(line[2]);
          tools[i] = new CombinationWrench(length, size);
        }else if(line[0].equals("CrossCutSaw")){
          tools[i] = new CrossCutSaw(length, line[2]);
        }else if(line[0].equals("HackSaw")){
          tools[i] = new HackSaw(length);
        }else{
          throw new Exception("Unknown Tool: " + line[0]);
        }
      }
      return tools;
    }catch(Exception e){
      System.out.println("Invalid Input");
      return new Tool[0];
    }
  }
}
```

The `readInput()` method looks quite complex, but it is actually really simple. First, it tries to open the file provided using a **Try with Resources** statement. Then, inside of that statement, it will read the first line of input and use that as an integer to create the array of tools. Then, using a **For** loop, it will read each line of input. Those lines can immediately be split into an array of tokens using the `String.split()` method. Then, we simply use a bunch of **If-Then-Else** statements to determine which type of tool must be created based on the first token in the input. Then, we can use subsequent tokens as input to the constructors for each class, converting inputs to integers as needed.

If we can't find a matching tool, we can simply throw a new exception with a helpful error message.

Finally, since we simply need to catch _any_ possible exception, we'll just add a catch statement for the generic exception and print the "Invalid Input" message before returning an empty array of tools. 

Once we have an array of tools, we can also write the `findTool()` method that will search the list of tools for a tool that can do the job. We could do so using this code:

```java
public static Tool findTool(Tool[] tools, String query){
  String[] query_parts = query.split(" ");
  if(query_parts[0].equals("tighten")){
    int clearance = Integer.parseInt(query_parts[1]);
    int size = Integer.parseInt(query_parts[2]);
    for(Tool t : tools){
      if(t instanceof Wrench){
        Wrench w = (Wrench)t;
        if(w.tighten(clearance, size)){
          return t;
        }
      }
    }
    return ??;
  }else if(query_parts[0].equals("cut")){
    int length = Integer.parseInt(query_parts[1]);
    for(Tool t : tools){
      if(t instanceof Saw){
        Saw s = (Saw)t;
        if(s.cut(length; query_parts[2]))){
          return s;
        }
      }
    }
    return ??;
  }else{
    return ??;
  }
}
```

This method is also a bit complex, but upon closer inspection it should be pretty straightforward. We simply parse the query into individual tokens. Then, we use the first token to determine if we are looking for a wrench or a saw. Next, we iterate through the entire list of tools, and inside of the **Enhanced For** loop, we check to see if the current tool is either a wrench or a saw, whichever type we are looking for. If it is, we cast it to that type, and then call the appropriate method. If that method returns `true`, we know that the tool can perform the requested task, so we can just return it right there!

What if we get to the end and can't find a tool that matches? This method still needs to return an object of the `Tool` type. For arrays, we've been returning an empty array to show that the method was unsuccessful. Is there such as thing as an "empty object"? 

It turns out there is! Java uses a special keyword called `null` to represent an empty object. So, we can just return `null` anywhere we aren't sure what to return, and we'll use that value in our `main()` method to determine whether we found a tool or not.

```java
public static Tool findTool(Tool[] tools, String query){
  String[] query_parts = query.split(" ");
  if(query_parts[0].equals("tighten")){
    int clearance = Integer.parseInt(query_parts[1]);
    int size = Integer.parseInt(query_parts[2]);
    for(Tool t : tools){
      if(t instanceof Wrench){
        Wrench w = (Wrench)t;
        if(w.tighten(clearance, size)){
          return t;
        }
      }
    }
    return null;
  }else if(query_parts[0].equals("cut")){
    int length = Integer.parseInt(query_parts[1]);
    for(Tool t : tools){
      if(t instanceof Saw){
        Saw s = (Saw)t;
        if(s.cut(length, query_parts[2])){
          return s;
        }
      }
    }
    return null;
  }else{
    return null;
  }
}
```

Finally, we can simply write the `main()` method:

```java
public static void main(String[] args){
  if(args.length != 1){
    System.out.println("Invalid Input");
    return;
  }
  
  Tool[] tools = readInput(args[0]);
  
  if(tools.length == 0){
    return;
  }
  
  Scanner scanner = new Scanner(System.in);
  String query = scanner.nextLine();
  Tool t = findTool(tools, query);
    if(t != null){
      System.out.println(t.describe());
    }else{
      System.out.println("Invalid Tool");
    }

}
```

In the `main()` method, we check to make sure that we've received exactly one command-line argument. If so, we pass that argument to the `readInput()` method to read from the input file and produce an array of tools. If that array is empty, we know that we failed to read the input file correctly, so we should simply return.

If the array is populated, then we must read input from the terminal. So, we'll read a user's query, and then pass that query to the `findTool()` method along with the array of tools. As a reminder, **try with resources** should **NEVER** be used when reading from `System.in`.

If the `findTool()` method returns anything other than `null`, we know that we found a tool and should print the tool's description to the terminal. Otherwise, we can do nothing since we are at the end of the program.
 

There we go! This is a very simple program, but it helps demonstrate the power of using inheritance in our programs to represent real-world objects that are closely related to each other. 

We can use the first assessment below to check the structure of our entire program, making sure it matches the UML diagram given above. Once our program passes that assessment, we can use the second assessment to check the functionality of our program. For simplicity, the functionality tests will not use the `main()` method itself, but it will check the other two methods defined in the `Main` class as well as several other methods of the various classes. 

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

