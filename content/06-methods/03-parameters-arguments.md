---
title: "Parameters & Arguments"
pre: "3. "
weight: 30
---

When we are writing methods in our code, we may need to provide some input to our methods. This allows our method to perform the same action using different data each time, making them much more flexible. So, let's look at how to do that in pseudo code and discuss some of the terminology we'll need to understand first.

## Parameters

When we define a method, we can also list a number of _parameters_, or inputs, that the method can _accept_. Depending on the language we are using, we may need to provide either a _name_, or possibly a _type_ and a _name_ for each parameter. In addition, many languages allow us to accept _variable length parameters_, which we'll cover in detail later in this module. 

So, in our code, we can define a method that accepts parameters in this way:

```tex
FUNCTION foo(parameter1, parameter2){
  print(parameter1)
  print(parameter2)
  }
```

Typically, each parameter is listed in the method's definition. So, this example defines a method named `foo` that accepts two parameters, `parameter1` and `parameter2`. Together, they make up the method's _signature_, which allows our programs to find them. Therefore, no two methods may share the same signature. Instead, they must either use a different name, or a different number of parameters. In statically typed languages such as Java, we can also vary the types of each parameter instead, not just the number of parameters.

## Arguments

Of course, when we want to call a method in our code, we must provide values for each parameter. Those values are known as _arguments_ to the method. In pseudocode, it might look something like this:

```tex
FUNCTION main(){
  foo("abc", "xyz")
  }
```

In that example, we see `foo("abc", "xyz")`, which is calling our method named `foo`. Inside, it provides two _arguments_, one for each _parameter_ of the method. So, inside of our method, the variable `parameter1` will be `"abc"`, and `parameter2` will be `"xyz"`. Pretty straightforward, right? 

{{% notice info "Parameters vs. Arguments" %}}

Of course, many programmers use the terms _parameters_ and _arguments_ interchangeably as well, but we'll try to stick to the following definitions:

* **Parameter**: an input variable defined as part of a method's definition or signature
* **Argument**: a specific value provided to a method as part of a method call or invocation

{{% /notice %}}