---
title: "Methods"
pre: "5. "
weight: 50
---

{{% youtube t5Ehg2bjwlI %}}

[Video Materials]({{<relref "./video">}})

We can also add methods to our classes. These methods are used either to modify the attributes of the class or to perform actions based on the attributes stored in the class. Finally, we can even use those methods to perform actions on data provided as arguments. In essence, the sky is the limit with methods in classes, so we'll be able to do just about anything we need to do in these methods. Let's see how we can add methods to our classes.

## Adding Methods

To add a method to our class, we can simply add a function declaration inside of our class. In fact, all of the functions we've been creating up to this point have been inside of a class. The only difference is that we'll now be able to remove the `static` keyword from our function declarations. We'll discuss more about exactly what that keyword does later in this chapter.

So, let's add the methods we need to our `Student` class:

```java
import java.lang.Math;

public class Student{
  String name = "name";
  int age = 19;
  String student_id = "123456987";
  int credits = 0;
  double gpa = 0.0;
  
  void birthday(){
    this.age = this.age + 1;
  }
  
  void grade(int credits, int grade_points){
    int current_points = (int)Math.round(this.gpa * this.credits);
    this.credits += credits;
    current_points += grade_points;
    this.gpa = current_points / this.credits;
  }
}
```

The `birthday()` method is pretty straightforward. When that method is called, we simply increase the age of this student by 1 year. However, instead of referencing the `age` variable directly, we are using `this.age` to access the _attribute_ `age` in this class. The keyword `this` refers to the current _instance_ of Student, which we'll learn how to create on the next page. Whenever we want to access an _attribute_ in a class, it is recommended that we always use the keyword `this` in front of it, just to avoid any issues.

The `grade()` method is a bit more complex. It accepts a number of credits and the grade points earned for a class, and then must update the `credits` and `gpa` attributes with that new information. To do this, it must first calculate the current number of grade points the student has earned based on the current GPA, then update those values and recalculate the GPA. Finally, notice that we included a reference to the `Math.round()` method, so we'll also need to import the `java.lang.Math` library at the top of our file in order to use that method. 

{{% notice note "Variable Scope" %}}

We've already discussed variable scope earlier in this course. Recall that variables declared inside of a block are not accessible outside of the block. Similarly, two different functions may reuse variable names, because they are in different scopes. 

The same applies to classes. A class may have an attribute named `age`, but a method inside of the class may also declare a local variable named `age`. Therefore, we must be careful to make sure that we access the correct variable, usually by using the `this` keyword to access the attribute variable. Here's a short example:

```java
public class Test{
  int age = 15;
  
  void foo(){
    int age = 12;
    System.out.println(age);      // 12
    System.out.println(this.age); // 15
  }
  
  void bar(){
    System.out.println(age); // 15
  }
}
```

As we can see, in the method `foo()` we must be careful to use `this.age` to refer to the attribute, since there is another variable named `age` declared in that method. However, in the method `bar()` we see that `age` automatically references the attribute, since there is no other variable named `age` defined in that scope. 

This can lead to some confusion in our code. So, we should always get in the habit of using `this` to refer to any attributes, just to avoid any unintended problems later on.

{{% /notice %}}

Let's go ahead and add the `promotion()` method to the `Teacher` class as well. That method should accept a single integer as a parameter, and then add that value to the Teacher's current salary. We won't worry about adding methods to the `Main` class at this point: we'll cover those methods in the next few pages. 

Use the first test below to check that we've included the correct methods in the `Student` and `Teacher` classes. Then, use the second test to confirm that those methods work correctly. Each test below is worth 5 points in this module, for a total of 10 points. 

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}