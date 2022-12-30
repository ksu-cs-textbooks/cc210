---
title: "If-Else Statement"
pre: "2. "
weight: 20
---

The **If-Else** statement in Java is very similar to the **If** statement. In Java, the syntax for an **If-Else** statement is shown below:

```java
if(<Boolean expression>){
  <true block>
}else{
  <false block>
}
```

As expected, Java will first evaluate the `<Boolean expression>` to a single Boolean value. If that value is `true`, it will execute the instructions in the `<true block>`, which can be one or more lines of code, or even additional constructs as we'll see later. If that value is `false`, then the program will execute the code in the `<false block>` instead. In essence, the **If-Else** statement simply adds a second code block and the `else` keyword after an **If-** statement. 

Let's take a look at a few code examples, just to see how this construct works in practice. First, let's consider the program represented by this flowchart from earlier in the chapter:

![If-Then Flowchart](/images/04-cond/4.4.ifthenelse.png)

This flowchart corresponds to the following code in Java. In this case, we'll assume `x` is hard-coded for now:

```java
int x = 1;
if(x >= 0){
  System.out.println(x);
}else{
  System.out.println(-1 * x);
}
System.out.println("Goodbye");
```

As we can see, this program uses `x >= 0` as the Boolean logic expression inside of the **If-Else** statement. If it is `true`, then it will output the value of `x`. If it is `false`, the program will output the value `(-1 * x)`, which represents the inverse of `x`. 

Here's one more example. In this program, we'd like to calculate the difference between two numbers, but we'd only like to output a positive number. So, our code may look something like this:

```java
int x = 3;
int y = 8;
if(x > y){
  int difference = x - y;
  System.out.println(difference);
}else{
  int difference = y - x;
  System.out.println(difference);
}
```

In this program, we are simply checking to see if `x > y`. If so, we know that `x - y` will be a positive number. Otherwise, we can assume that `y - x` will be either a positive number or {{< math >}}$ 0 ${{< /math >}}. In either case, we see that this program will produce the correct output. 

{{% notice info "Missing Curly Braces?" %}}

In Java, it is possible to have an **If** or **If-Else** statement without curly braces. In that case, the next line of code immediately following the `if` or `else` will be the only line considered inside of that branch.

Consider this code for example:

```java
int x = 4;
if(x == 5)
System.out.println(true);
else
System.out.println(false);
```

This code is valid, and will compile and run properly. However, it is very difficult to read because of the indentation. 

In addition, if we want to add another line of code to each branch, we might accidentally do the following:

```java
int x = 4;
if(x == 5)
x = 0;
System.out.println(true);
else
x++;
System.out.println(false);
```

This code will **not** compile and run properly, because the `else` statement cannot be attached to the appropriate `if` statement. So, we'd need to add curly braces to make this code make sense to the compiler. 

Beyond that, it can be very difficult to read code that is not properly indented, regardless of the use of curly braces. So, it is a best practice to always include curly braces in your conditional statements and indent each block, even if those changes aren't necessarily required in some cases.

{{% /notice %}}