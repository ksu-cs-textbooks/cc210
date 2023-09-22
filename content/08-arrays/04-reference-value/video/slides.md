---
type: "reveal"
hidden: true
---
<br>
<section>
  <h3>Call by Value</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue1.png">
  <div style="float: left; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = 5
  y = addThree(x)
  print(x)
  print(y)
<br>
define addThree(x)
  x = x + 3
  return x
    </code></pre>
    </div>
</section>
<br>
<br>
<section>
  <h3>Call by Value</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue1.png">
  <div style="float: left; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  <mark>x = 5</mark>
  y = addThree(x)
  print(x)
  print(y)
<br>
define addThree(x)
  x = x + 3
  return x
    </code></pre>
    </div>
</section>
<br>
<br>
<section>
  <h3>Call by Value</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue2.png">
  <div style="float: left; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  <mark>x = 5</mark>
  y = addThree(x)
  print(x)
  print(y)
<br>
define addThree(x)
  x = x + 3
  return x
    </code></pre>
    </div>
</section>
<br>
<br>
<section>
  <h3>Call by Value</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue2.png">
  <div style="float: left; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = 5
  <mark>y = addThree(x)</mark>
  print(x)
  print(y)
<br>
define addThree(x)
  x = x + 3
  return x
    </code></pre>
    </div>
</section>
<br>
<br>
<section>
  <h3>Call by Value</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue3.png">
  <div style="float: left; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = 5
  <mark>y = addThree(x)</mark>
  print(x)
  print(y)
<br>
define addThree(x)
  x = x + 3
  return x
    </code></pre>
    </div>
</section>
<br>
<br>
<section>
  <h3>Call by Value</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue3.png">
  <div style="float: left; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = 5
  y = addThree(x)
  print(x)
  print(y)
<br>
<mark>define addThree(x)</mark>
  x = x + 3
  return x
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<section>
  <h3>Call by Value</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue4.png">
  <div style="float: left; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = 5
  y = addThree(x)
  print(x)
  print(y)
<br>
<mark>define addThree(x)</mark>
  x = x + 3
  return x
    </code></pre>
    </div>
</section>
<br>
<br>
<section>
  <h3>Call by Value</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue4.png">
  <div style="float: left; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = 5
  y = addThree(<mark>x</mark>)
  print(x)
  print(y)
<br>
define addThree(<mark>x</mark>)
  x = x + 3
  return x
    </code></pre>
    </div>
</section>
<br>
<br>
<section>
  <h3>Call by Value</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue5.png">
  <div style="float: left; width: 65%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = 5
  y = addThree(<mark>x</mark>)
  print(x)
  print(y)
<br>
define addThree(<mark>x</mark>)
  x = x + 3
  return x
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<section>
  <h3>Call by Value</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue5.png">
  <div style="float: left; width: 65%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = 5
  y = addThree(x)
  print(x)
  print(y)
<br>
define addThree(x)
  <mark>x = x + 3</mark>
  return x
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<section>
  <h3>Call by Value</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue6.png">
  <div style="float: left; width: 65%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = 5
  y = addThree(x)
  print(x)
  print(y)
<br>
define addThree(x)
  <mark>x = x + 3</mark>
  return x
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<section>
  <h3>Call by Value</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue6.png">
  <div style="float: left; width: 65%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = 5
  y = addThree(x)
  print(x)
  print(y)
<br>
define addThree(x)
  x = x + 3
  <mark>return x</mark>
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<section>
  <h3>Call by Value</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue7.png">
  <div style="float: left; width: 65%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = 5
  y = addThree(x)
  print(x)
  print(y)
<br>
define addThree(x)
  x = x + 3
  <mark>return x</mark>
    </code></pre>
    </div>
</section>
<br>
<br>
<section>
  <h3>Call by Value</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue7.png">
  <div style="float: left; width: 65%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = 5
  <mark>y = addThree(x)</mark>
  print(x)
  print(y)
<br>
define addThree(x)
  x = x + 3
  return x
    </code></pre>
    </div>
</section>
<br>
<section>
  <h3>Call by Value</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue8.png">
  <div style="float: left; width: 65%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = 5
  <mark>y = addThree(x)</mark>
  print(x)
  print(y)
<br>
define addThree(x)
  x = x + 3
  return x
    </code></pre>
    </div>
</section>
<br>
<br>
<section>
  <h3>Call by Value</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue8.png">
  <div style="float: left; width: 65%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = 5
  y = addThree(x)
  <mark>print(x)</mark>
  <mark>print(y)</mark>
<br>
define addThree(x)
  x = x + 3
  return x
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<section>
  <h3>Call by Reference</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue1.png">
  <div style="float: left; width: 65%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = {1, 2}
  changeLast(x)
  print(x[0])
  print(x[1])
<br>
define changeLast(x)
  x[1] = 5
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<section>
  <h3>Call by Reference</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue1.png">
  <div style="float: left; width: 65%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  <mark>x = {1, 2}</mark>
  changeLast(x)
  print(x[0])
  print(x[1])
<br>
define changeLast(x)
  x[1] = 5
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<br>
<section>
  <h3>Call by Reference</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue9.png">
  <div style="float: left; width: 65%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  <mark>x = {1, 2}</mark>
  changeLast(x)
  print(x[0])
  print(x[1])
<br>
define changeLast(x)
  x[1] = 5
    </code></pre>
    </div>
</section>
<br>
<br>
<section>
  <h3>Call by Reference</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue10.png">
  <div style="float: left; width: 65%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  <mark>x = {1, 2}</mark>
  changeLast(x)
  print(x[0])
  print(x[1])
<br>
define changeLast(x)
  x[1] = 5
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<br>
<section>
  <h3>Call by Reference</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue10.png">
  <div style="float: left; width: 65%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = {1, 2}
  <mark>changeLast(x)</mark>
  print(x[0])
  print(x[1])
<br>
define changeLast(x)
  x[1] = 5
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<br>
<section>
  <h3>Call by Reference</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue10.png">
  <div style="float: left; width: 65%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = {1, 2}
  changeLast(x)
  print(x[0])
  print(x[1])
<br>
<mark>define changeLast(x)</mark>
  x[1] = 5
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<section>
  <h3>Call by Reference</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue11.png">
  <div style="float: left; width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = {1, 2}
  changeLast(x)
  print(x[0])
  print(x[1])
<br>
<mark>define changeLast(x)</mark>
  x[1] = 5
    </code></pre>
    </div>
</section>
<br>
<br>
<section>
  <h3>Call by Reference</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue11.png">
  <div style="float: left; width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = {1, 2}
  changeLast(<mark>x</mark>)
  print(x[0])
  print(x[1])
<br>
define changeLast(<mark>x</mark>)
  x[1] = 5
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<section>
  <h3>Call by Reference</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue12.png">
  <div style="float: left; width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = {1, 2}
  changeLast(<mark>x</mark>)
  print(x[0])
  print(x[1])
<br>
define changeLast(<mark>x</mark>)
  x[1] = 5
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<section>
  <h3>Call by Reference</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue12.png">
  <div style="float: left; width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = {1, 2}
  changeLast(x)
  print(x[0])
  print(x[1])
<br>
define changeLast(x)
  <mark>x[1] = 5</mark>
    </code></pre>
    </div>
</section>
<br>
<section>
  <h3>Call by Reference</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue13.png">
  <div style="float: left; width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = {1, 2}
  changeLast(x)
  print(x[0])
  print(x[1])
<br>
define changeLast(x)
  <mark>x[1] = 5</mark>
    </code></pre>
    </div>
</section>
<br>
<br>
<section>
  <h3>Call by Reference</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue13.png">
  <div style="float: left; width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = {1, 2}
  <mark>changeLast(x)</mark>
  print(x[0])
  print(x[1])
<br>
define changeLast(x)
  x[1] = 5
    </code></pre>
    </div>
</section>
<br>
<section>
  <h3>Call by Reference</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue14.png">
  <div style="float: left; width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = {1, 2}
  <mark>changeLast(x)</mark>
  print(x[0])
  print(x[1])
<br>
define changeLast(x)
  x[1] = 5
    </code></pre>
    </div>
</section>
<br>
<section>
  <h3>Call by Reference</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue14.png">
  <div style="float: left; width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = {1, 2}
  changeLast(x)
  <mark>print(x[0])</mark>
  <mark>print(x[1])</mark>
<br>
define changeLast(x)
  x[1] = 5
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<section>
  <h3>Reassignment</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue1.png">
  <div style="float: left; width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = {1, 2}
  changeLast(x)
  print(x[0])
  print(x[1])
<br>
define changeLast(x)
  x = {3, 4}
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<section>
  <h3>Reassignment</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue1.png">
  <div style="float: left; width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  <mark>x = {1, 2}</mark>
  changeLast(x)
  print(x[0])
  print(x[1])
<br>
define changeLast(x)
  x = {3, 4}
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<section>
  <h3>Reassignment</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue10.png">
  <div style="float: left; width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  <mark>x = {1, 2}</mark>
  changeLast(x)
  print(x[0])
  print(x[1])
<br>
define changeLast(x)
  x = {3, 4}
    </code></pre>
    </div>
</section>
<br>
<br>
<section>
  <h3>Reassignment</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue10.png">
  <div style="float: left; width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = {1, 2}
  <mark>changeLast(x)</mark>
  print(x[0])
  print(x[1])
<br>
define changeLast(x)
  x = {3, 4}
    </code></pre>
    </div>
</section>
<br>
<br>
<section>
  <h3>Reassignment</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue10.png">
  <div style="float: left; width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = {1, 2}
  changeLast(x)
  print(x[0])
  print(x[1])
<br>
<mark>define changeLast(x)</mark>
  x = {3, 4}
    </code></pre>
    </div>
</section>
<br>
<br>
<section>
  <h3>Reassignment</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue11.png">
  <div style="float: left; width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = {1, 2}
  changeLast(x)
  print(x[0])
  print(x[1])
<br>
<mark>define changeLast(x)</mark>
  x = {3, 4}
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<section>
  <h3>Reassignment</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue11.png">
  <div style="float: left; width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = {1, 2}
  changeLast(<mark>x</mark>)
  print(x[0])
  print(x[1])
<br>
define changeLast(<mark>x</mark>)
  x = {3, 4}
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<section>
  <h3>Reassignment</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue12.png">
  <div style="float: left; width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = {1, 2}
  changeLast(<mark>x</mark>)
  print(x[0])
  print(x[1])
<br>
define changeLast(<mark>x</mark>)
  x = {3, 4}
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<section>
  <h3>Reassignment</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue12.png">
  <div style="float: left; width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = {1, 2}
  changeLast(x)
  print(x[0])
  print(x[1])
<br>
define changeLast(x)
  <mark>x = {3, 4}</mark>
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<section>
  <h3>Reassignment</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue15.png">
  <div style="float: left; width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = {1, 2}
  changeLast(x)
  print(x[0])
  print(x[1])
<br>
define changeLast(x)
  <mark>x = {3, 4}</mark>
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<section>
  <h3>Reassignment</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue15.png">
  <div style="float: left; width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = {1, 2}
  <mark>changeLast(x)</mark>
  print(x[0])
  print(x[1])
<br>
define changeLast(x)
  x = {3, 4}
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<section>
  <h3>Reassignment</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue16.png">
  <div style="float: left; width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = {1, 2}
  <mark>changeLast(x)</mark>
  print(x[0])
  print(x[1])
<br>
define changeLast(x)
  x = {3, 4}
    </code></pre>
    </div>
</section>
<br>
<br>
<br>
<section>
  <h3>Reassignment</h3>
  <img class="plain" style="height: 800px" src="/images/08-array/callvalue16.png">
  <div style="float: left; width: 60%">
    <pre class="stretch" style="font-size: .5em"><code class="javascript">define main()
  x = {1, 2}
  changeLast(x)
  <mark>print(x[0])</mark>
  <mark>print(x[1])</mark>
<br>
define changeLast(x)
  x = {3, 4}
    </code></pre>
    </div>
</section>
<br>