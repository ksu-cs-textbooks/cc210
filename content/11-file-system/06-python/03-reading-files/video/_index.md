---
title: "Python Read Files"
pre: "3.P. "
weight: 31
hidden: true
date: 2019-09-23T00:00:26-05:00
---

{{< youtube tdBCzDVmqqo >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

To read files using Python, we've been using some simple starter code. The code shown here is pretty much exactly what we saw in an earlier chapter on exception handling.

This starter code is using the `open()` method built in to Python to open the file provided as a command-line argument. If no file is provided, then it will use the terminal, or `sys.stdin` to read input.

The only difference is that this code will use `sys.exit()` to stop the program if the file provided as a command-line argument cannot be opened. Most of the programs in this chapter and beyond use this behavior, since we really want to make sure we are reading input from a file instead of the terminal when we provide one as input, even if it causes an error.

Inside of the **with** statement, we can use the reader object just like we have in our previous programs. Nothing else has really changed there. See if you can complete the sample program on this page to confirm that your new starter code is working properly.
