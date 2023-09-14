---
title: "Instance Methods"
pre: "4. "
weight: 40
---

We can also add additional methods to our classes. These methods are used either to modify the attributes of the class or to perform actions based on the attributes stored in the class. Finally, we can even use those methods to perform actions on data provided as arguments.  In essence, the sky is the limit with methods in classes, so we'll be able to do just about anything we need to do in these methods. Let's see how we can add methods to our classes.

As with attributes, there are class and instance categories. Class methods are underlined on the UML diagram and will be discussed in a later module. 

## Adding Methods

To add a method to our class, we can simply add a method declaration inside of our class declaration. So, let's add the methods we need to our `Ingredient` class:

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

    public String toString(){
        return String.format("%.2f",amount) + " " + units + " of " + name;
    }
}
```

The `toString()` method is pretty straightforward. When that method is called, we simply return a string of `<amount> <units> of <name>`. `toString()` has a special meaning in Java, it is the method called whenever an object is coerced (automatically converted) to a String.  

So that we get consistent results, we used the format specifier`%.2f` in `String.format()`, to round the `amount` off to two decimal places.  Used in this manner:

```java
String.format("<format specifier>", <variable>)
```

[`String.format()`](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#format-java.lang.String-java.lang.Object...-) returns a string representation of **variable** formatted according to the format specifier.  See [geeks for geeks](https://www.geeksforgeeks.org/format-specifiers-in-java/) for a specifier list.

{{% notice info "Variable Scope" %}}

We've already discussed variable scope earlier in this course. Recall that two different functions may use the same local variable names without affecting each other because they are in different scopes. 

The same applies to classes. A class may have an attribute named `age`, but a method inside of the class may also use a local variable named `age`. Therefore, we must be careful to make sure that we access the correct variable,  using the `this` reference if we intend to access the object's attribute's value in the current instance. Here's a short example:

```java
public class Test{
  public int age;

  public Test(){
     this.age = 15;
  }
  
  public void foo(){
    int age = 12;
    System.out.println(age);     // 12
    System.out.println(this.age);// 15
  }

  public static void main(String[] a){
    Test temp = new Test();
    temp.foo();
 }
}
```

As we can see, in the method `foo()` we must be careful to use `this.age` to refer to the attribute, since there is another variable named `age` declared in that method.

{{% /notice %}}

For the `convert()` method, lets specify objects of type `Ingredient` must have units of "cups" or "ml" (milliliters).  As parameters, it accepts a reference to the current instance named `self`, and value for conversion units.  It must determine if a conversion is necessary.  If so, it must update the attributes `units` and `amount`.  There are 236.588 milliliters in a cup.  

```java
public void convert(String units){
    if (this.units.equals("cups") && units.equals("ml")){
        this.units = "ml";
        amount *= 236.588;
    }else if(this.units.equals("ml") && units.equals("cups")){
        this.units = "cups";
        amount /= 236.588;
    }
}
```

Let's go ahead and add the `scale()` method as well.  That method should accept a single `double` as a parameter It should: (1) create a new object, (2) copy its object attributes to the new object, (3) scale the new object's `amount` by the scaling factor.  

```java
public Ingredient scale(double factor){
    Ingredient output = new Ingredient();
    output.name = this.name;
    output.units = this.units;
    output.amount = this.amount * factor;
    return output;
}
```

![UML](/images/07-object/ingr2_UML_jv.png)

