---
title: "Loop Control"
pre: "3. "
weight: 30
---

Python also includes both the `break` and `continue` keywords. They are pretty straightforward and easy to follow.

## Break

Here's the flowchart showing a program with a `break` statement from earlier in this chapter:

![Break Flowchart](/images/05-loop/5.5.break.png)

This flowchart corresponds to the following code in Python. Once again, we'll assume `x` is hard-coded for now:

```python
x = 8
i = 1
while True:
  if x % i != 0:
    print(i)
    break
  i = i + 1
```

This code shows us an example of an infinite **While** loop, sometimes referred to as a **While-True** loop. In this case, we are simply using the keyword `True` as our Boolean expression, so the loop will always continue to run unless we use the `break` keyword to leave it. So, in this code, once `x % i != 0` evaluates to `True`, we reach the `break` keyword and then exit the loop. 

## Continue

Here's the flowchart showing a program with a `continue` statement from earlier in this chapter:

![Continue Flowchart](/images/05-loop/5.5.continue.png)

This flowchart corresponds to the following code in Python. Once again, we'll assume `x` is hard-coded for now:

```python
x = 8
for i in range(1, x+1):
  if x % i != 0:
    continue
  print(i)
```

In this example, we see a **For** loop that contains a `continue` statement inside of it. Here, it is important to remember that, even though the `continue` statement tells the program to go back to the beginning of the loop, `i` will still be updated to the next value in the list. This is one of the unique features of a **For** loop compared to a similar **While** loop. If we rewrote this program using a **While** loop, we'd have to remember to update the value of `i` manually before the `continue` keyword, as in this example:

```python
x = 8
i = 1
while i <= x:
  if x % i != 0:
    i += 1
    continue
  print(i)
  i += 1
```

Notice that we had to include an extra `i += 1` before the `continue` keyword. Otherwise, the loop would repeat without updating the value of `i`, causing it to become infinitely stuck. 

{{% notice tip "Try It!" %}}

Try the preceding code as the body for `main()` in `Loops.py` and see what happens when you remove the `i += 1` statement directly above the `continue` keyword. Does it cause any problems?

_**Hint:**_ When using a program via the terminal, you can press `CTRL` + `c` to stop a running program if it locks up or starts infinitely looping. 

{{% /notice %}}