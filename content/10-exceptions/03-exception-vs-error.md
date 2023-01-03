---
title: "Exception vs. Error"
pre: "3. "
weight: 30
---

Problems in a computer program can typically be divided into two categories: _exceptions_ and _errors_. While these terms are used interchangeably by many programmers, there is a specific difference between these two types of problems. In this course, we'll try to stick to the following convention:

* **Exception**: An exception is a problem encountered by a running computer program (we could also say "at runtime") which can be _handled_, or detected and corrected, by the program itself. This may include asking the user to provide new input, manipulating data, or retrying an operation that failed. 
* **Error**: An error is a problem which _cannot_ be solved by the program itself, and usually results in the program's termination. This could include syntax errors and unexpected system issues, such as a lack of memory. 

We'll see many examples of both exceptions and errors later in this chapter.