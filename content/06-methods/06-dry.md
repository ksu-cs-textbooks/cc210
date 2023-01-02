---
title: "DRY: Don't Repeat Yourself"
pre: "6. "
weight: 60
---

One major mantra among programmers is **Don't Repeat Yourself (DRY)**, and it's a very important concept to keep in mind when writing programs that can use methods. In essence, anytime we find ourselves writing the same or similar code multiple times in our program, we may want to ask ourselves if it would be better to make that piece of code a method. That way, we only have to write it once, and if there are any problems with that code, we only have to remember to change it in one place instead of everywhere we've used it. 

## DRY Example

To really understand how DRY can improve our code, let's look at a quick example:

```tex
FUNCTION main(){
   a <- 1
   b <- 0
   c <- -4
   root_1 <- (-b - SQUAREROOT(b*b - 4*a*c)) / (2 * a)
   root_2 <- (-b + SQUAREROOT(b*b - 4*a*c)) / (2 * a)
   print (root_1, root_2)

   a <- 2
   b <- 7
   c <- 3
   root_1 <- (-b - SQUAREROOT(b*b - 4*a*c)) / (2 * a)
   root_2 <- (-b + SQUAREROOT(b*b - 4*a*c)) / (2 * a)
   print (root_1, root_2)
}
```

Of course, this is a very simple example calculating the roots of a quadratic equation. 

{{< math >}}
$$ax^2 + bx + c$$
{{< /math >}}

Let's apply the DRY principle to simplify this program:

```tex
FUNCTION main(){
  quadratic(1,0,-4)
  quadratic(2,7,3)
  }
  
FUNCTION quadratic(a,b,c){
   root_1 <- (-b - SQUAREROOT(b*b - 4*a*c)) / (2 * a)
   root_2 <- (-b + SQUAREROOT(b*b - 4*a*c)) / (2 * a)
   print (root_1, root_2)
  }
```

There! We've moved all of the code for calculating the roots for the quadratic equation, printing each root at the end. Then, we can simplify the code in `main` by simply calling that method anytime we want to calculate the roots .

This could be further reduced by "pre calculating"  the discriminant. 

```tex
FUNCTION main(){
  quadratic(1,0,-4)
  quadratic(2,7,3)
  }
  
FUNCTION quadratic(a,b,c){
   d = discriminant(a , b, c)
   root_1 <- (-b - SQUAREROOT(d)) / (2 * a)
   root_2 <- (-b + SQUAREROOT(d) / (2 * a)
   print (root_1, root_2)
  }
  
FUNCTION discriminant(a,b,c){
   RETURN b*b - 4*a*c
}
```

You could even throw in a test for real-number roots, recall that if the discriminant is negative there are no real roots. How and where is left for you to puzzle out, it can be done in a few places.

Properly following the DRY principle when writing code will make our programs simpler, easier to maintain, and hopefully easier to debug. In effect, it is definitely a good idea to add a new method to our code anytime we find ourselves typing something twice, or copy and pasting code. 