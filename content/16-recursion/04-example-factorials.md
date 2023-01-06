---
title: "Example: Factorials"
weight: 20
pre: "4. "
---
The most popular example of using recursion is calculating the factorial of a positive integer {{< math >}}$ N ${{< /math >}}. The factorial of a positive integer {{< math >}}$ N ${{< /math >}} is just the product of all the integers from {{< math >}}$ 1 ${{< /math >}} to {{< math >}}$ N ${{< /math >}}. For example, the factorial of {{< math >}}$ 5 ${{< /math >}}, written as {{< math >}}$ 5! ${{< /math >}}, is calculated as {{< math >}}$ 5 * 4 * 3 * 2 * 1 = 120 ${{< /math >}}. The definition of the factorial function itself is recursive.

{{< math >}}
$$
\text{fact}(N) = N  *  \text{fact}(N - 1)
$$
{{< /math >}}

The corresponding pseudocode is shown below.

```tex
function FACT(N)
    if N == 1
        return 1
    else
        return N * FACT(N-1)
    end if
end function
```

The recursive version of the factorial is slower than the iterative version, especially for high values of {{< math >}}$ N ${{< /math >}}. However, the recursive version is simpler to program and more elegant, which typically results in programs that are easier to maintain over their lifetimes.
