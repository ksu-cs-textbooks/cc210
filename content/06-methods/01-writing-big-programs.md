---
title: "Writing Big Programs"
pre: "1. "
weight: 10
---

Throughout this course so far, we've written several programs.  But we may start to notice that we are repeating lines of code over and over again. 

As programs get bigger, it can also be difficult to manage all of the code and make sure we are not missing something. A small typing error in one part of the code can become very difficult to find when there is so much code to check.

For example, consider a program that needs to write the same output to multiple output files. Right now, if we wanted to write that program, it might contain code that performs these steps:

```tex
open file1
write to file1
write to file1
close file1

open file2
write to file2
write to file2
close file2

open file3
write to file3
write to file3
close file3

open file4
write to file4
write to file4
close file4
```

As we can see, much of the code in that program is repeated, with only small parts changed. Is there a different way we could write this program to make it simpler?