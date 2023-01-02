---
title: "Driver Class"
pre: "5. "
weight: 50
---

The Driver class is much simpler.  It has one feature, a **class method** `public static void main(String[] args)`[^1]. Everything that needs to be done will be done in the main method.  A template might be:

[^1]: In Java, class methods have the modifier static

```java
public class Driver{
    
   public static void main(String[] args){

   }
    
}
```

{{% notice info "Class vs. Static Features" %}}

A class feature belongs to the class, no object is necessary to use it.  Examples include math methods we write 

```java
double five = Math.sqrt(25.); 
```
to access the class function `sqrt()`.  WE DO NOT FIRST CREATE A MATH OBJECT:

```java
Math mo = new Math();    // NO
double five = mo.sqrt(25.); //  NO
```

Java uses the keyword `static` as a function modifier to create class methods and attributes.  NOT ALL LANGUAGES USE `STATIC` THIS WAY.   Be caredul when using "static" to mean "class".  In Java they are virtually synonymous, in general they are not.

{{% /notice %}}

## Accessing the Instance Class

Lets add an instance `Ingredient` as `i1`.

```java
public static void main(String[] args){
    Ingredient i1 = new Ingredient();
}
```

{{% notice info "How Does the Compiler Handle User-Defined Classes?" %}}

When the java compiler (`javac`) sees an identifier it does not understand, it looks in
* the rest of the file being compiled
* the classes covered by the `import` statements
* the directory the `.java` file is in
* * If it finds a .java file it also compiles it
* * If it finds a `.class` file it uses it 

So when our `Driver.java` uses `Ingredient`, the java compiler (re)compiles `Ingredient.py`.

{{% /notice %}}

