---
title: "For Loop"
pre: "3. "
weight: 30
---
The syntax for a **For** loop in Java is a bit complex, and has many different parts. Here's the general format:

```java
for(<initializers>; <loop condition>; <updaters>){
  <loop code block>
}
```

Let's break this syntax down into each individual part to understand how it works.

First, the `<initializers>` section is used to create and initialize any variables that we'd like to use as _loop counters_ inside of the loop. For example, we could use `int i = 0` in that section to create a single integer variable `i` and set its initial value to `0`. We may also declare multiple variables of the same type, separating each with a comma or `,`. In that instance, we could say `int i = 0, j = 1`, which would declare two new integer variables, `i` and `j`, and set their values to `0` and `1`, respectively. Finally, we can choose to leave that section blank, as it is not required at all. In either case, we must end that section with a semicolon `;` before moving on to the next section. This section is executed just once, before the first iteration of the loop itself. We'll explore a full example below. 

The `<loop condition>` section is the same as in a **While** loop. It must evaluate to a single Boolean value, either `true` or `false`, which is used to determine if the loop continues executing or not. This section must also end with a semicolon `;`, and is generally required in a **For** loop. 

Finally, the `<updaters>` section can include one or more statements used to increment (update) the values of the loop counter variables. This section is executed at the end of each iteration of the loop, _before_ the Boolean expression is evaluated again. Generally, we would include code such as `i++` or `i = i + 2` in this section. Similar to the `<initializers>` section, multiple update statements can be included in this section, separated by a comma `,`. So, we could use `i++, j++` to increment the values of both `i` and `j` in the same loop. 

Let's look at an example. Here's a flowchart from earlier in this chapter containing a **For** loop:

![For Loop Flowchart](/images/05-loop/5.4.forloop.png)

This flowchart corresponds to the following code in Java. Once again, we'll assume `x` is hard-coded for now:

```java
int x = 8;
for(int i = 1; i <= x; i++){
  System.out.println(i);
}
```

In this **For** loop, we can clearly see the three parts. First, we have `int i = 1` as the _initializer_. It creates a new variable and gives it an initial value. Then, we see `i <= 8` is our loop's Boolean condition. Finally, we have `i++` as the lone _updater_, since it updates the value of the loop counter `i` by incrementing it by {{< math >}}$ 1 ${{< /math >}}. 

To understand how this **For** loop functions in practice, let's look at an equivalent **While** loop:

```java
int x = 8;

//initializers
int i = 1;

while(i <= x){
  System.out.println(i);
  
  //updaters
  i++;
}
```

These loops are exactly identical in terms of how the code is executed. In a **For** loop, the initializers are performed once at the beginning, before the loop really starts. Then, we evaluate the Boolean expression and determine if we should enter the loop and perform those operations. At the end of each loop iteration, the updaters are executed to update the values of any loop counters, before the loop repeats back to the Boolean expression. 
 

{{% notice info "For Loops and Variable Scope" %}}

**For** loops in Java have one important caveat when it comes to variable scope. As expected, any variables declared in the initializers section of a **For** loop may be accessed from within the **For** loop itself, but they may also be accessed in the Boolean expression or the updaters section as well. They cannot, however, be accessed outside of the **For** loop.

However, any variables declared inside the **For** loop _cannot_ be accessed in either the Boolean expression or the updaters. In effect, a **For** loop in Java has two levels of scope, one containing the variables declared in the initializers, and another for just the code inside the loop. Generally this doesn't pose a problem, but it is an important distinction to be aware of. 

{{% /notice %}}

Here's one more example of a **For** loop in Java, using three loop counters instead of just one:

```java
int sum = 0;
for(int i = 0, j = 1, k = 20; i + j < k; i++, j++, k--){
  sum += i + j + k;
}
```

Notice that there are three variables initialized in the initializer, which is `int i = 0, j = 1, k = 20`. In addition, there are three variables updated in the updater, which is `i++, j++, k--`. While it is uncommon for most programmers to use multiple loop counters in a single **For** loop, it is important to understand how it can be done. 

{{% notice note "Missing Curly Braces?" %}}

In Java, it is possible to have loop constructs without curly braces, just like we saw for conditional constructs in an earlier. In that case, the next line of code immediately following the `while` or `for` will be the only line repeated inside of the loop.

Consider this code for example:

```java
int x = 0;
while(x < 5)
  x++;
```

This code is valid, and will compile and run properly. However, just like with conditional constructs, if we want to add a second line to the inside of the loop, we'll need to remember to add curly braces for our code to work properly. 

In addition, we can omit parts of a **For** loop, as in this example:

```java
int x = 0;
for( ; x < 5 ; )
  x++;
```

Here, we've omitted both the initializers and updaters of the **For** loop. Those parts are considered optional, and either one can be left out. However, in this case, it may make more sense to convert this to a **While** loop instead. 

{{% /notice %}}