---
title: "With"
pre: "6. "
weight: 60
---

<!--{{< youtube Mr6OPmyKRCM  >}}-->

<!--[Video Materials]({{% relref "./video" %}})-->

<!-- TODO Redo Video so it doesn't close stdin -->

Lastly, Python includes another new statement that is relevant to dealing with exceptions, called the **With** statement.

## With

To understand how the **With** statement works in Python, let's look at an example:

```python
import sys
import traceback
import io

try:
    if len(sys.argv) >1:
        with open(sys.argv[1]) as input_file:
            data = "".join(input_file.readlines())
            reader = io.StringIO(data)
    else:
        reader = sys.stdin 
    
    x = int(reader.readline())
    print(x)

  
except ValueError as e:
  print("ValueError: {}".format(e))
except FileNotFoundError as e:
  print("FileNotFoundError: {}".format(e))

```

In this example, we are first using the standard **If** statement to either open a file provided as the first command-line argument, or else we are reading input from the terminal. 

If there is a file provided, we open it using a **with** statement.  This statement is used to create a _context manager_ in Python. In short, it allows languages developers to define things that must always be done before and after a resource, such as an open file, is used. In this example, in addition to opening the file, it will make sure the `infile` is closed when we leave the with block.  The other statements manipulate the file into StringIO object that uses the same methods as sys.stdin.

When the code in the `with` statement throws an exception, Python will automatically perform the cleanup operations for the resource listed in the `with`. So, when we are reading input from a file, it would close that file and make sure that it isn't damaged or left open when our program crashes. 

In addition, any additional exceptions thrown when trying to close the file are _suppressed_ by the system, so we only see the exception that caused the initial error. This is much better than using a `finally` statement to close the file, since we'd have to run the risk of throwing a second exception inside of the `finally` statement. 

This type of statement is great when writing programs that will handle large amounts of input, either by connecting to a database, reading from a file, or using the Internet to communicate with a server. Many standard Python libraries can be used in this way, especially if they require a `close()` or other cleanup method to be called when we are finished using them. So, a `with` statement is a great way to make sure those programs are able to handle exceptions without leaving the system in an unstable state. 

<p style="color:red"><b>WARNING:</b> avoid using **with** in conjunction with stdin. <br> `with sys.stdin as reader:` is bad.  Python will dutifully close the stdin at the end of the with-block -- making it unavailable to the program a second time.  This would be like having to close and reopen Word, because every time you hit `return` the keyboard stopped working.</p>

More on `with ... as ...:` after we cover File input.