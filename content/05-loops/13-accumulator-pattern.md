---
title: "Accumulator Pattern"
pre: "13. "
weight: 130
---

One thing loops are frequently used for is the accumulating data about a range of values or a collection of objects.  Generally you loop over a range of values and and "collect" the values that meet certain criteria. Examples:

* Sum up all the integers from 1 to 100 (answer 5050)
* Count all the prime numbers less than 100 (answer 25)

So you 

1. loop value-by-value over the range
2. Test each value to see if it meets the criteria^[sometime called the filter]
3. If the value meets the criteria, update the accumulator

The general pattern is:

![accumulator pattern](/images/05-loop/accumulator.png)

### Example 1
* Sum up all the even integers from 1 to 100 (answer 2550)

```tex
sum <- 0  # accumulator variable
r <- 1    # range value
REPEAT WHILE (r <= 100){
  IF (r MOD 2 = 0){  # criteria for even numbers
    sum <- sum + r
  }
  r <- r + 1
}
DISPLAY(sum)
```

Here we are asked to sum up the even values, so the accumulator gets the value of each even number added to it.  

### Example 2

* Count all the prime numbers integers from 1 to 100.  The Function ISPRIME(int) returns True if int is a prime number, otherwise it returns False.

```tex
count <- 0  # accumulator variable
r <- 1    # range value
REPEAT WHILE (r <= 100){
  IF (ISPRIME(r)){  # criteria for even numbers
    count <- count + 1
  }
  r <- r + 1
}
DISPLAY(count)
```

Here we are asked to count the number of primes, so the accumulator goes up by one every time we find a prime number
