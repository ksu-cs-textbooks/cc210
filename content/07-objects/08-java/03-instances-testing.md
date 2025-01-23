---
title: "Instances & Testing"
pre: "3. "
weight: 30
---

Your class should now look something like this, although your default values may be different:

```java
public class Ingredient{
    public String name;
    public double amount;
    public String units;

    public Ingredient(){
        this.name = "flour";
        this.amount = 2.0;
        this.units = "cup";
    }

    public Ingredient(String name, double amount, String units){
        this.name = name;
        this.amount = amount;
        this.units = units;
    }
}
```

As classes grow large you will want to test methods as you add them.  In CC 410 we will learn about test frameworks and will write formal tests in parallel with project development.  

For now we will follow the convention of a `main` method in each class which can be used for testing.  The basic flow would be:

1. Create class
1. Write the constructor, it may be blank
1. Create `main(args)`, instantiate an object and test (print out) the initialized value to test for correctness.
1. Compile and run the class as a program
1. Repeat until done:
   1. Create new method
   1. Update `main()`, usually involves instantiating and object and using it to call the new method
   1. Run and check output

## Instantiation

To _instantiate_, or create, an object in Java, we use the keyword `new` and call the class constructor. 

```java
Ingredient ingr1 = new Ingredient();
```

This will create a new `Ingredient` object, and then store it in a variable of type `Ingredient` named `ingr1`. While this may seem a bit confusing at first, it is very similar to how we've already been working with variables of types like `int` and `double`.

### Accessing Attributes

Once we've created a new object, we can access the instance _attributes_ as defined in the class from which it is created. 

For example, to access the `name` attribute in the object stored in `ingr1`, we could put the following code in `main()`[^2]

[^2]: Recall that java always looks for a `public static void main (String[] args)` method to run:

```java
Ingredient ingr1 = new Ingredient();
String n = ingr1.name; // n is assigned the current value of
                       // ingr1's name attribute
System.out.println(n == ingr1.name); // prints true they are equal
```

Java uses what is called _dot notation_ to access attributes and methods within instances of a class. So, we start with an object created from that class and stored in a variable, and then use a period or dot `.` directly after the variable name followed by the attribute or method we'd like to access. Therefore, we can easily access all of the attributes in an `Ingredient` object using this notation:

```java
Ingredient ingr1 = new Ingredient();
System.out.println(ingr1.name);
System.out.println(ingr1.amount);
System.out.println(ingr1.units);
```

We can then treat each of these attributes just like any normal variable, allowing us to use or change the value stored in it:

```java
Ingredient ingr1 = new Ingredient();
System.out.println(ingr1.name);
System.out.println(ingr1.amount);
System.out.println(ingr1.units);

n = ingr1.name;
String ingr1.name = "cardamom";
System.out.println (n == ingr1.name); // False they are not equal we changed ingr1.name
```

## How to Test

When testing it is important to avoid "feature creep" in the class.  We want to avoid adding add attributes or methods that are not called for by the UML class diagram.  In software development you will drive up test and maintenance cost[^3].  

In this class it is always acceptable to add a `private static void main()` method, even if it is not on the UML, to facilitate testing.  We will put all our test code <b>for instance classes</b> in `main()`. 

[^3]: Software <a href="https://galorath.com/software-maintenance-costs/#:~:text=SOFTWARE%20MAINTENANCE%20COST%20DEFINED&text=Software%20maintenance%20costs%20will%20typically,20%25%20of%20software%20maintenance%20costs)">maintenance</a> is estimated to be 60 - 75% of the total cost of ownership for a software project.


```java
public class Ingredient{
    public String name;
    public double amount;
    public String units;

    public Ingredient(){
        this.name = "flour";
        this.amount = 2.0;
        this.units = "cup";
    }

    public Ingredient(String name, double amount, String units){
        this.name = name;
        this.amount = amount;
        this.units = units;
    }

    private static void main(String[] args){
        Ingredient ingr1 = new Ingredient();
        System.out.println(ingr1.name);
        System.out.println(ingr1.amount);
        System.out.println(ingr1.units);    
    }
}
```

This is how one might test a constructor method, we check to see all object variables have the correct values.

Things to keep in mind for this course:
* YOU need to know what the answer (print out) should be
* Never use input (keyboard or file) in your test code
  * Hard code the values you want to test with
* Consider deleting `main()` from instance classes before submitting a Project
* Consider deleting this code after testing each method
  * You can continue to append to the end but it makes for a long program

{{% notice info "What if the Class Needs a Main Method?" %}}

Write `main()`'s actual functionality last, and possibly move your testing code to the `test()` method. Consider this structure:

```java
private static void test(){  put you test code here}
public static void main(String[] args){
    test(); // delete this line when you are done testing
            // and ready to start writing main
}
```

It encapsulates all the test code in `test` and keeps main pretty clean.  When you are satisfied that everything but `main()` works, delete the call and work on `main()`.

The only way to test `main()`'s functionality will be from the terminal.

{{% /notice %}}