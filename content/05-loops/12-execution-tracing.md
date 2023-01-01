---
title: "Execution Tracing"
pre: "12. "
weight: 120
---

<!-- TODO Rewrite -->

_This page adapted from K-State's CC 110 course, Lavezzi, 2021._

## Code coverage and boundary values

The same basic principles that apply to test cases for `IF`s apply to `REPEAT WHILE`.  Some test cases  should carry execution into the loop, some should by-pass the loop. When practical, you can use boundary values on with respect to the loop conditional statement.

## Tracing a basic loop

Consider

```text
1    a <- 0
2    REPEAT WHILE (a < 3){
3       DISPLAY(a)
4       a <- a + 1
5       }
6    DISPLAY("done")
```

The trace of this program  is {1,2,3,4,5,  2,3,4,5,   2,3,4,5,   2,6,}.  `a` starts as `0` and becomes `1` then `2` then `3` each time `line 4` is executed.

Often to get full loop body coverage will require several test cases.

Consider

```text
1    a <- ?
2    REPEAT WHILE (a < 6){
3       IF (a MOD 2 = 0){
4         DISPLAY( a + "is even")
5       }
6       ELSE{
7         DISPLAY( a + "is odd")
8       }
9       a <- a + 2
10   }
11   DISPLAY("done")
```

Here, if a starts as even, say `2`; the trace would be {1,2,3,4,5,9,10,  2,3,4,5,9,10   2,11}.  Lines 6,7,8 are never reached if a starts off even.  Good candidates for test values of `a` are: 5, 6 (boundary values for while condition) and 1,2 testing the odd-even logic coverage inside the loop.  

Could you count "5" as both a boundary and coverage value?  Sure, but I typically want to see a couple of actual "loops" before I call something tested.

###  Tracking values in Loops

You will need to become adept at keeping track of the values of variables as the are modified by loop traversals.

In the code above, if `1    a <-3 ` were the first line, the trace would be 
```
line         1, 2, 3, 6, 7, 8, 9,   2, 3, 6, 7, 8, 9,  2, 11  
value of a   3  3  3     3     5    5  5     5     7   7   7
```  
where the value of `a` at various stages of execution is provided.