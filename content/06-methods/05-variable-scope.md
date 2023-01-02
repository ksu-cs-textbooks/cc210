---
title: "Variable Scope"
pre: "5. "
weight: 50
---

Another topic we must revisit is _variable scope_. Recall from an earlier chapter we learned how variables may only be referenced after they've been defined, and in many cases only within the method or block they are defined in. Now that we are dealing with multiple methods, we must once again discuss variable scope and how it applies to this situation.

## Method Scope

In general, all of the scope rules we've learned still apply. For example, a variable declared in a method can only be accessed within that method. In that way, different methods may use the same variable names to refer to different variables. In addition, as we've seen in the earlier examples, a method may define parameters using the same variable names as the variables that are used as arguments to that method. It may seem confusing to some, but to others it makes perfect sense.

## Class Scope

Most programming languages also allow us to create variables at the class level, inside a class but outside of any method. Those variables can then be referenced within any of the class's method, allowing us to share data between methods without using parameters and return values.

Here's a quick example in pseudo code:

```tex
CLASS math{

pi = 3.1415926535

FUNCTION main(){
  r = 3.0
  area = calculateArea(r)
  print(area)
  }
  
FUNCTION calculateArea(r){
  return r * r * pi
  }
}  

```

In this example, we have created a class variable named `pi` to store the value of {{< math >}}$ \pi ${{< /math >}} for our entire program. Then, we can use that variable just like any other inside of the `calculateArea` method.

Of course, we can assign and edit class variables just like any other variable:

```tex
0   CLASS foo{
1   people = 1
2   
3   FUCNTION main(){
4     people = people + 1
5     foo()
6     print(people)
7     }
8     
9   FUNCTION foo(){
10    people = people * 3
11    }
12  }
```

In this example, the `main` method will print {{< math >}}$ 6 ${{< /math >}} as the value of `people`. Since that variable is declared in the _class scope_, it can be accessed and changed by any method. 


### Tracing the program

By default, we assume all programs start with a call to main().  Thus the trace of this program is { 3, 4, 5,  9, 10, 11, 6, 7 }.


## Shadowing Variables-- Using the Same Variable Names

Sometimes we may want to have a variable inside of our methods use the same name as a class variable, this is a type of **shadowing**. Shadowing occurs whenever an inner scope name hides (in its shadow) an outer scope variable of the same name.  Here's a modified version of the code above showing that situation:


```tex
  CLASS foo{
    people = 1
   
   FUNCTION main(){
     people = people + 1
     foo(people)
     print(people)
     }
     
     
   FUNCTION foo(people){
     people = people * 3
     }
  }
```

In this example, the variable `people` is a parameter inside of the `foo` method. So, it is an entirely different variable than the class variable named `people`. Because of this, whenever we use the variable `people` inside of `foo`, we are referring to the _method scope_ or _local scope_ variable people. Therefore, the class-scope value is not updated, and `main` will simply print {{< math >}}$ 2 ${{< /math >}} instead of {{< math >}}$ 6 ${{< /math >}}. 

Shadowing is not necessarily bad, and may be unavoidable in large programs using multiple imported modules.  There are only so many good names.  

