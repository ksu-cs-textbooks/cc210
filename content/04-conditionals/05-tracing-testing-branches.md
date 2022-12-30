---
title: "Tracing & Testing Branches"
pre: "5. "
weight: 50
---

<!-- TODO Rewrite & Simplify? -->

## Testing for complete coverage

Every program should be tested.  Better test sets, the set of different inputs against which a program should be tested, ensure that every line of code is reached (executed) at least once when all tests have been run.  This is referred to as test coverage.  

### "Complete" coverage 

Consider

```
1   a <- INPUT(some integer)
2   b <- ""
3   IF (a % 2 == 0) 
4   {
5     b <- "not"
6   }
7   DISPLAY( a + " is "+ b + "even")
```

If "1" is entered for line one, the trace of the program is {1,2,3,7}.  Since 1%2 is `1`, the body of the if statement is skipped. Thus a test set of {{1}} provides 4/7 or 57% coverage.

If "2" is entered the trace of the program is {1,2,3,4,5,6,7}. Since 1%2 is `0`, the body of the if statement is executed.  Thus a test set of {{2}} seems to provide full coverage.

####  Using {{2}}

Lets follow what happens
1. line 1 -- a is assigned the value `1`
2. line 2 -- b is assigned the value "" (the empty string)
3. line 3 -- 2 % 2 is 0, so we go into the IF-body
4. lines 4, 5 -- b is assigned the value "not"
5. line 6 -- exit IF body
6. line 7 -- prints " 2 is not even"

ER, okay lets fix the program and re-run

```
1   a <- INPUT(some integer)
2   b <- ""
3   IF (a % 2 == 0) 
4   {
5     b <- ""
6   }
7   DISPLAY( a + " is "+ b + "even")
```
####  Using {{2}} Redux

Lets follow what happens
1. line 1 -- a is assigned the value `1`
2. line 2 -- b is assigned the value "" (the empty string)
3. line 3 -- 2 % 2 is 0, so we go into the IF-body
4. lines 4, 5 -- b is assigned the value ""
5. line 6 -- exit IF body
6. line 7 -- prints "2 is even"

Success?  We have 100% coverage on the lines of code and the right answer, but we are not done.

## Boundary values

The problem is 100% code coverage is <b>necessary but not sufficient</b> to ensure a good test set.  

This introduces the concept of boundary values. The condition `(a % 2 == 0)` creates a boundary where some values will go into the IF-body and some will skip it.  It is also <b>necessary but not sufficient</b> to test both sides of every boundary.  

We need a value for a that will make  `(a % 2 == 0)` false.  Lets choose `3`.

Checking 3 reveals we have a problem, as the result is "3 is even".  This leads to another quick fix.

```
1   a <- INPUT(some integer)
2   b <- "not"
3   IF (a % 2 == 0) 
4   {
5     b <- ""
6   }
7   DISPLAY( a + " is "+ b + "even")
```

Finally, using the the test set {{2}, {3}} we get the correct answers, have complete code coverage and have tested every boundary.


{{% notice note "Boundary Values" %}}

Sometimes it is infeasible to use all boundary values.  Consider `IF (a<b){...}` where `a` and `b` are integers. There are an infinite number of a,b combinations to test--testing all of these conditions is not realistic.  Making sure you test at least once where a&lt;b and once where a&ge;b should be the minimum.

However, when one side of a comparison is a constant number, such as the `1` in `a/b > 1`.  It is generally considered a good idea to test values at the boundary and slightly outside the boundary. 

{{% /notice %}}

## Perfect Testing Is Impossible

Except for the most trivial programs, it is impossible to exhaustively test a program for correctness. However, using boundary testing and coverage testing as a guide, you will be able to develop fairly robust test sets for CC-210.

In practice exhaustive comprehensive testing is not even attempted.   There is a type of programming, called high-assurance or safety-critical that uses specialized languages, structures and techniques to logically prove certain properties are always true.  The symbolic math and logic background required for this types of programming lies beyond the scope of the Computational Core program.

##  How you Write a Program Influences How you Test 

### Should you always specify an ELSE?

What if we had started with

```
1   a <- INPUT(some integer)
3   IF (a % 2 == 0) 
4   {
5     b <- ""
6   }
7   ELSE
8   {
9     b<- "not"
10  }
11  DISPLAY( a + " is "+ b + "even")
```
It would have been obvious that {2} did not provide complete coverage, maybe we would have come up with {{2},{3}} faster.

### Should you avoid complex conditions?

How many "boundary" values do you need for `IF (p == 105 and t == 273) { ... } ` ?

### Balance "readability" with "testability"

The goal when writing any program is that other reading your code should understand what is going on.

```
1   IF (p == 105 and t == 273) 
2   { 
3    ... 
4   }
5
6   IF (p == 105 ) 
7   { 
8      IF (t == 273) 
9      { 
10         ... 
11     }
12     ELSE
13     {
14      do nothing
15     }
16  }
17  ELSE
18  {
19     do nothing
20  }
```

Here lines 1-4 and 6 - 20 do the same thing.  It is easier, as a programmer, to read lines 1-4. However, a novice tester may have an easier time determining test cases for  6-20.  Personally[^1], I would go with 1-4.   

[^1]: George Lavezzi