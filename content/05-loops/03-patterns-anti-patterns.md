---
title: "Patterns & Anti-Patterns"
pre: "3. "
weight: 30
---

## Patterns

Software "patterns"  are designs or practices which have proven to be beneficial to software development.  By following patterns, developers ensure other programmers can follow the code semantics (logic) and therefore maintain or modify it. 

Think of them like building codes.  By following the plumbing codes when building a house, the builder ensures the plumbing is safe and effective, and that it can be maintained or modified by future plumbers should that be desired.

Patterns represent a consensus of the programming community of an efficient, maintainable way to solve the generalized problem for which it is designed.

Most patterns deal with design issues, and are beyond the scope of CC 210; a few deal with coding and we will introduce them where appropriate.

## Anti-Patterns

These represent the "traps"  of coding.  Code styles and designs which are syntacticly and semantically correct, but have proven to be difficult to maintain, inefficient and hard to modify are labeled as Anti-Patterns.  Anti-Patterns still work, they are just bad designs or implementations.

### Anti-Pattern: Ambiguous Naming

Ambiguous naming is usually the result of rushed or expedient coding.

Consider the code

```tex
FUNCTION lnf(f,l){
    DISPLAY ( l + ", " + f)
}
```

It is not obvious to the reader what this function intends.  You could add comments 

```tex
# Displays last_name, first name
FUNCTION lnf(f,l){
    # f- fist name, l- last name
    DISPLAY ( l + ", " + f)
}
```

but that only addresses some of the symptoms, not the problem.  If you happen to be reading the definition, you are okay.  But if you run into it "in the wild"  `lnf(gn,dn)`, you will need to then go find the definition of `lnf()` to understand what is going on.  The problem is the code itself is hard to read and comprehend.

```tex
FUNCTION displayLastNameFirstName(first, last){
    DISPLAY ( last + ", " + first)
```

This final definition is good.  The names are unambiguous and explanatory.  Encountering `displayLastNameFirstName(gn,dn)` is verbose enough to let a code reader intuit that `gn,dn` resolve to names, which will be printed in a particular order.  Better would be `displayLastNameFirstName(givenName,dynasticName)`.

### Anti-Pattern: Redundant Boolean Comparisons

Consider `IF ((numCars > 5) = True)`.  This is a typical beginning programmer statement.  It is resolved in order:

1. numCars value is looked up
2. numCars value is compared to 5 (>)
3. `(numCars > 5)` is replaced with either True or False (lets say it is False)
4. False is compared to True (=)
5. `False = True` is replaced with False
6.  IF (FALSE) is evaluated

However, steps 4 and 5 are unnecessary.  This should have been written `IF (numCars > 5)`.  Any comparison to a Boolean constant is ALWAYS unnecessary.  

<table>
  <tr><td> True = True</td><td>True</td></tr>
  <tr><td> False = True</td><td>False</td></tr>
  <tr><td> True = False</td><td>False</td></tr>
  <tr><td> False = False</td><td>True</td></tr>
  <tr><td> True != True</td><td>False</td></tr>
  <tr><td> False != True</td><td>True</td></tr>
  <tr><td> True != False</td><td>True</td></tr>
  <tr><td> False != False</td><td>False</td></tr>
</table>

Redundant Boolean comparisons typically indicate the programmer does not understand the comparison abstraction, the IF semantics, or both.

