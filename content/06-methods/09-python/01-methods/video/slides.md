---
type: "reveal"
hidden: true
---
<br>
<section>
	<pre class="" style="font-size: .8em"><code class="python">def foo():
  print("Foo")
  return
</code></pre>
</section>
<br>
<br>
<section>
	<pre class="" style="font-size: .8em"><code class="python"><mark>def</mark> foo():
  print("Foo")
  return
</code></pre>
</section>
<br>
<br>
<section>
	<pre class="" style="font-size: .8em"><code class="python">def <mark>foo</mark>():
  print("Foo")
  return
</code></pre>
</section>
<br>
<br>
<section>
	<pre class="" style="font-size: .8em"><code class="python">def foo<mark>()</mark>:
  print("Foo")
  return
</code></pre>
</section>
<br>
<br>
<section>
	<pre class="" style="font-size: .8em"><code class="python">def foo():<mark>
  print("Foo")
  return</mark>
</code></pre>
</section>
<br>
<br>
<section>
	<pre class="" style="font-size: .8em"><code class="python">def foo:
  print("Foo")
  <mark>return</mark>
</code></pre>
</section>
<br>
<br>
<section>
	<pre class="" style="font-size: .8em"><code class="python">def foo:
  print("Foo")
  return
</code></pre>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">def main():
  print("Main 1")
  foo()
  print("Main 2")
  foo()
  print("Main 3")
<br>
def foo():
  print("Foo 1")
  return
<br>
# main guard
if __name__ == "__main__":
  main()
</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em"></p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python"><mark>def main():
  print("Main 1")
  foo()
  print("Main 2")
  foo()
  print("Main 3")</mark>
<br>
def foo():
  print("Foo 1")
  return
<br>
# main guard
if __name__ == "__main__":
  main()
</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em"></p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">def main():
  print("Main 1")
  foo()
  print("Main 2")
  foo()
  print("Main 3")
<br>
<mark>def foo():
  print("Foo 1")
  return</mark>
<br>
# main guard
if __name__ == "__main__":
  main()
</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em"></p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">def main():
  print("Main 1")
  foo()
  print("Main 2")
  foo()
  print("Main 3")
<br>
def foo():
  print("Foo 1")
  return
<br>
# main guard
<mark>if __name__ == "__main__":</mark>
  main()
</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em"></p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">def main():
  print("Main 1")
  foo()
  print("Main 2")
  foo()
  print("Main 3")
<br>
def foo():
  print("Foo 1")
  return
<br>
# main guard
if __name__ == "__main__":
  <mark>main()</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em"></p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">def <mark>main</mark>():
  print("Main 1")
  foo()
  print("Main 2")
  foo()
  print("Main 3")
<br>
def foo():
  print("Foo 1")
  return
<br>
# main guard
if __name__ == "__main__":
  <mark>main()</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em"></p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">def main():
  <mark>print("Main 1")</mark>
  foo()
  print("Main 2")
  foo()
  print("Main 3")
<br>
def foo():
  print("Foo 1")
  return
<br>
# main guard
if __name__ == "__main__":
  <mark>main()</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em"></p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">def main():
  <mark>print("Main 1")</mark>
  foo()
  print("Main 2")
  foo()
  print("Main 3")
<br>
def foo():
  print("Foo 1")
  return
<br>
# main guard
if __name__ == "__main__":
  <mark>main()</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em"><mark>Main 1</mark></p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">def main():
  print("Main 1")
  <mark>foo()</mark>
  print("Main 2")
  foo()
  print("Main 3")
<br>
def foo():
  print("Foo 1")
  return
<br>
# main guard
if __name__ == "__main__":
  <mark>main()</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">def main():
  print("Main 1")
  <mark>foo()</mark>
  print("Main 2")
  foo()
  print("Main 3")
<br>
def <mark>foo</mark>():
  print("Foo 1")
  return
<br>
# main guard
if __name__ == "__main__":
  <mark>main()</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">def main():
  print("Main 1")
  <mark>foo()</mark>
  print("Main 2")
  foo()
  print("Main 3")
<br>
def foo():
  <mark>print("Foo 1")</mark>
  return
<br>
# main guard
if __name__ == "__main__":
  <mark>main()</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">def main():
  print("Main 1")
  <mark>foo()</mark>
  print("Main 2")
  foo()
  print("Main 3")
<br>
def foo():
  <mark>print("Foo 1")</mark>
  return
<br>
# main guard
if __name__ == "__main__":
  <mark>main()</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1<br><mark>Foo 1</mark></p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">def main():
  print("Main 1")
  <mark>foo()</mark>
  print("Main 2")
  foo()
  print("Main 3")
<br>
def foo():
  print("Foo 1")
  <mark>return</mark>
<br>
# main guard
if __name__ == "__main__":
  <mark>main()</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1<br>Foo 1</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">def main():
  print("Main 1")
  foo()
  <mark>print("Main 2")</mark>
  foo()
  print("Main 3")
<br>
def foo():
  print("Foo 1")
  return
<br>
# main guard
if __name__ == "__main__":
  <mark>main()</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1<br>Foo 1</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">def main():
  print("Main 1")
  foo()
  <mark>print("Main 2")</mark>
  foo()
  print("Main 3")
<br>
def foo():
  print("Foo 1")
  return
<br>
# main guard
if __name__ == "__main__":
  <mark>main()</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1<br>Foo 1<br><mark>Main 2</mark></p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">def main():
  print("Main 1")
  foo()
  print("Main 2")
  <mark>foo()</mark>
  print("Main 3")
<br>
def foo():
  print("Foo 1")
  return
<br>
# main guard
if __name__ == "__main__":
  <mark>main()</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1<br>Foo 1<br>Main 2</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">def main():
  print("Main 1")
  foo()
  print("Main 2")
  <mark>foo()</mark>
  print("Main 3")
<br>
<mark>def foo():
  print("Foo 1")
  return</mark>
<br>
# main guard
if __name__ == "__main__":
  <mark>main()</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1<br>Foo 1<br>Main 2</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">def main():
  print("Main 1")
  foo()
  print("Main 2")
  <mark>foo()</mark>
  print("Main 3")
<br>
<mark>def foo():
  print("Foo 1")
  return</mark>
<br>
# main guard
if __name__ == "__main__":
  <mark>main()</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1<br>Foo 1<br>Main 2<br><mark>Foo 1</mark></p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">def main():
  print("Main 1")
  foo()
  print("Main 2")
  foo()
  <mark>print("Main 3")</mark>
<br>
def foo():
  print("Foo 1")
  return
<br>
# main guard
if __name__ == "__main__":
  <mark>main()</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1<br>Foo 1<br>Main 2<br>Foo 1</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">def main():
  print("Main 1")
  foo()
  print("Main 2")
  foo()
  <mark>print("Main 3")</mark>
<br>
def foo():
  print("Foo 1")
  return
<br>
# main guard
if __name__ == "__main__":
  <mark>main()</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1<br>Foo 1<br>Main 2<br>Foo 1<br><mark>Main 3</mark></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">def main():
  print("Main 1")
  foo()
  print("Main 2")
  foo()
  print("Main 3")
<br>
def foo():
  print("Foo 1")
  return
<br>
# main guard
if __name__ == "__main__":
  <mark>main()</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1<br>Foo 1<br>Main 2<br>Foo 1<br>Main 3</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">def main():
  print("Main 1")
  foo()
  print("Main 2")
  foo()
  print("Main 3")
<br>
def foo():
  print("Foo 1")
  return
<br>
# main guard
if __name__ == "__main__":
  main()
</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1<br>Foo 1<br>Main 2<br>Foo 1<br>Main 3</p>
  </div>
</section>
<br>