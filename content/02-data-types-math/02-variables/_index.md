---
title: "Variables"
pre: "2. "
weight: 20
---

{{% youtube nk4XkiGKick %}}

[Video Materials]({{<relref "./video">}})

First, let's talk about variables. A _variable_ is a placeholder for another value in a computer program. Most students first learn about variables in a mathematics course, such as Algebra. For example, in math, we might see the equation {{< math >}}$ x + 5 = 10 ${{< /math >}}, where {{< math >}}$ x ${{< /math >}} is a variable, or placeholder, for a value. Using the algebraic rules, we can solve that equation to find that {{< math >}}$ x = 5 ${{< /math >}}.

Variables in a computer program share some similarities with variables in math, but have some differences as well. First, variables in a computer program are also placeholders that represent a value. However, in programming, instead of representing an _unknown_ value, variables in a computer program represent a _stored_ value, one which we can always access. 

![Cardboard Box Labelled Height](/images/02-data/2.2.cardboardbox.png)[^1]

[^1]: Orignial Image Credit: Karen Arnold on Public Domain Pictures.net https://www.publicdomainpictures.net/en/view-image.php?image=56626&picture=cardboard-box-white-background

One way to think about variables in a computer program is to imagine them as a cardboard box. When we _declare_ a variable, we are making a new box and giving it a name, which is the _identifier_ of the variable. In the picture above, we've declared a variable named `height`. 

Then, we can store a value in that variable, using a statement such as `height = 42`, which will put the number 42 inside of the `height` variable. This is an _assignment_ statement, which we'll cover in detail in this chapter. 

Later in our program, we can then access the value stored in that variable and use it for calculations or output. For example, if we have additional variables named `width` and `area`, and have already stored the value 10 in `width` using `width = 10`, we can calculate the area of rectangular object using a statement such as `area = width * height`. This would use the current values in the `height` and `width` variables, and then store the result in the variable named `area`. 

Behind the scenes, each time we declare a variable, we are telling the computer to set aside a small piece of memory in which to store something. We give the variable a name when we declare it, and then we can use that name to store or retrieve data from the location in memory our computer gave us. 

Using variables effectively is a essential to writing good computer programs. This chapter will introduce many of the concepts related to dealing with variables and data in our code. 