---
title: "Types"
pre: "1. "
weight: 10
---

The Python programming language is a _dynamically typed_ language. This means that a variable in our programs can store any type of data at any time, and we can even use the same variable to store different data types at different times in the same program. When we attempt to access the data stored in our variable, the Python interpreter determines if the data type of the variable can be used for that operation.

The major advantage of this approach is that it is very quick and easy to build programs in this language without worrying about the types of data that may be used. We could be storing integers, floating point numbers, or any other data type, and we won't have to change the variables we are using in our program.

The biggest downside to this approach is that it can be a bit more difficult to debug errors in our programs related to data types. While any variable can store any type, we must still make sure that we are using the correct types of data in each operation. In Python, the interpreter will only give us an error when we try to use a variable with an invalid data type stored inside it. 

To make dealing with types a bit easier, when dealing with mixed integer-float math, Python will automatically convert the integer into a float type without any additional code. For example, an integer in Python can be treated as a floating point number, since a floating point number has a larger size than an integer. 

However, the opposite case is not true. In Python, we cannot treat a floating point number as an integer without explicitly converting the data type. We'll see how to do that later in this chapter. 