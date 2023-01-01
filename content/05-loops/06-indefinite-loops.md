---
title: "Indefinite Loops"
pre: "6. "
weight: 60
---

The count up loop we just discussed is an example of an <b>indefinite</b> loop.  Indefinite loops may execute the loop body 0 or more times.

![Loop Flowchart elements](/images/05-loop/5-loopconstruct_1.png)

For the program sketched above consider what happens if `x <- 0`, or zero is input for `x`.  When the program reaches loop condition `x` will be less than `1` and the loop body will be skipped (or executed 0 times).  If `x<-1`, it would execute once; `x<-7`, seven times.  

Use indefinite loops whenever the decision to loop-again is based on the work done by the last loop iteration.  In our example, the decision to loop again is based on the change in `i`.  Said another way, it is based on the work done to `i` by the loop.

This is a critical concept.  For an indefinite loop to work, the loop body <b>must</b> have an execution path that changes one of the variables in the loop condition.

Consider 

![Loop Flowchart elements](/images/05-loop/5-infiniteLoop.png)

The loop body only changes `j`, the loop condition only considers `i` and `x`.  If `x <-2`, this program will print out `1` an infinite number of times. In practice you will either force restart the program, or the universe will end, before an actual infinite number of `1`s are printed.  This is bad.  

So a good rule of thumb is that the loop body should have a way to change at least one of the variables in an indefinite loop condition.