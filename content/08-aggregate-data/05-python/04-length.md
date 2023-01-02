---
title: "List Length"
pre: "4. "
weight: 40
---

Lists in Python do not have a fixed length, so it is important to be able to find the length of a list as we use it. 

To get the length of an existing list, use the built-in function `len()`:

```python
a = []
a.append(1)
a.append(2)
a.append(3)
a.append(4)

b = [True, False, True, False, True]

print(len(a)) # 4
print(len(b)) # 5
```

While it may seem obvious what the size of each list is in this example, there are many instances where we'll be given a list with unknown size from another piece of code. Similarly, as we start working with loops and lists, we'll find that it is very useful to be able to access the length of the list directly. 