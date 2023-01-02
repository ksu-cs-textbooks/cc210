---
type: "reveal"
hidden: true
---
<br>
<section>
  <h2>String Length</h2>
  <pre class="" style="font-size: .8em"><code class="python">s = "This"
print(len(s))
<br>
t = "This \"is\" that"
print(len(t))</code></pre>
</section>
<br>
<section>
  <h2>String Length</h2>
  <pre class="" style="font-size: .8em"><code class="python">s = "<mark>T</mark>h<mark>i</mark>s"
print(len(s))
<br>
t = "This \"is\" that"
print(len(t))</code></pre>
</section>
<br>
<section>
  <h2>String Length</h2>
  <pre class="" style="font-size: .8em"><code class="python">s = "This"
print(len(s))  # 4
<br>
t = "This \"is\" that"
print(len(t))</code></pre>
</section>
<br>
<section>
  <h2>String Length</h2>
  <pre class="" style="font-size: .8em"><code class="python">>s = "This"
print(len(s))  # 4
<br>
t = "<mark>T</mark>h<mark>i</mark>s<mark> </mark>\"<mark>i</mark>s<mark>\"</mark> <mark>t</mark>h<mark>a</mark>t"
print(len(t))</code></pre>
</section>
<br>
<section>
  <h2>String Length</h2>
  <pre class="" style="font-size: .8em"><code class="python">s = "This"
print(len(s))  # 4
<br>
t = "This \"is\" that"
print(len(t))  # 14</code></pre>
</section>
<br>
<section>
  <h2>String Comparison</h2>
  <pre class="stretch" style="font-size: .79em"><code class="python">s1 = "This"
s2 = "This"
s3 = "this"
<br>
print(s1 == s2)
print(s1 == s3)</code></pre>
</section>
<br>
<section>
  <h2>String Comparison</h2>
  <pre class="stretch" style="font-size: .79em"><code class="python">s1 = "This"
s2 = "This"
s3 = "this"
<br>
print(s1 == s2)  # True
print(s1 == s3)  # False</code></pre>
</section>
<br>
<section>
  <h2>String Comparison</h2>
  <pre class="stretch" style="font-size: .79em"><code class="python">s1 = "This"
s2 = "That"
<br>
if s1 &lt; s2:
  print("s1 comes first")
else:
  print("s2 comes first")
</code></pre>
</section>
<br>
<section>
  <h2>String Comparison</h2>
  <pre class="stretch" style="font-size: .79em"><code class="python">s1 = "This"
s2 = "That"
<br>
if <mark>s1 &lt; s2</mark>:
  print("s1 comes first")
else:
  print("s2 comes first")
</code></pre>
</section>
<br>
<section>
  <h2>String Comparison</h2>
  <pre class="stretch" style="font-size: .79em"><code class="python">s1 = "This"
s2 = "That"
<br>
if s1 &lt; s2:  # False
  print("s1 comes first")
else:
  <mark>print("s2 comes first")</mark>
</code></pre>
</section>
<br>
<section>
  <h2>String Concatenation</h2>
  <pre class="stretch" style="font-size: .79em"><code class="python">s1 = "This"
s2 = "That"
x = 42
<br>
s3 = s1 + s2
s4 = "" + str(x)
<br>
print(s3)
print(s4)</code></pre>
</section>
<br>
<section>
  <h2>String Concatenation</h2>
  <pre class="stretch" style="font-size: .79em"><code class="python">s1 = <mark>"This"</mark>
s2 = <mark>"That"</mark>
x = 42
<br>
s3 = <mark>s1 + s2</mark>
s4 = "" + str(x)
<br>
print(s3)
print(s4)</code></pre>
</section>
<br>
<section>
  <h2>String Concatenation</h2>
  <pre class="stretch" style="font-size: .79em"><code class="python">s1 = "This"
s2 = "That"
x = 42
<br>
s3 = s1 + s2
s4 = "" + str(x)
<br>
print(s3) # "ThisThat"
print(s4)</code></pre>
</section>
<br>
<section>
  <h2>String Concatenation</h2>
  <pre class="stretch" style="font-size: .79em"><code class="python">s1 = "This"
s2 = "That"
x = 42
<br>
s3 = s1 + s2
s4 = "" + str(x)
<br>
print(s3) # "ThisThat"
print(s4) # "42"</code></pre>
</section>
<br>
<section>
  <h2>Searching Strings</h2>
  <ul style="font-family: monospace">
    <li>in</li>
    <li>not in</li>
    <li>find</li>
    <li>rfind</li>
    <li>startswith</li>
    <li>endswith</li>
  </ul>
</section>
<br>
<section>
  <h2>Manipulating Strings</h2>
  <ul style="font-family: monospace">
    <li>replace</li>
    <li>[x:y] (splice)</li>
    <li>lower</li>
    <li>upper</li>
    <li>strip</li>
    <li>[x] (single character)</li>
  </ul>
</section>
<br>