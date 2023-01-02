---
type: "reveal"
hidden: true
---

<section>
	<pre class="" style="font-size: .8em"><code class="java">static void foo(){
  System.out.println("Foo");
  return;
}</code></pre>
</section>


<section>
	<pre class="" style="font-size: .8em"><code class="java"><mark>static</mark> void foo(){
  System.out.println("Foo");
  return;
}</code></pre>
</section>

<section>
	<pre class="" style="font-size: .8em"><code class="java">static <mark>void</mark> foo(){
  System.out.println("Foo");
  return;
}</code></pre>
</section>


<section>
	<pre class="" style="font-size: .8em"><code class="java">static void <mark>foo</mark>(){
  System.out.println("Foo");
  return;
}</code></pre>
</section>


<section>
	<pre class="" style="font-size: .8em"><code class="java">static void foo<mark>()</mark>{
  System.out.println("Foo");
  return;
}</code></pre>
</section>


<section>
	<pre class="" style="font-size: .8em"><code class="java">static void foo()<mark>{
  System.out.println("Foo");
  return;
}</mark></code></pre>
</section>


<section>
	<pre class="" style="font-size: .8em"><code class="java">static void foo(){
  System.out.println("Foo");
  <mark>return;</mark>
}</code></pre>
</section>


<section>
	<pre class="" style="font-size: .8em"><code class="java">static void foo(){
  System.out.println("Foo");
  return;
}</code></pre>
</section>



<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Functions{
  public static void main(String[] args){
    System.out.println("Main 1");
    foo();
    System.out.println("Main 2");
    foo();
    System.out.println("Main 3");
    return;
  }<br>
  static void foo(){
    System.out.println("Foo 1");
    return;
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em"></p>
  </div>
</section>


<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Functions{
  public static void <mark>main</mark>(String[] args){
    System.out.println("Main 1");
    foo();
    System.out.println("Main 2");
    foo();
    System.out.println("Main 3");
    return;
  }<br>
  static void foo(){
    System.out.println("Foo 1");
    return;
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em"></p>
  </div>
</section>



<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Functions{
  public static void main(String[] args){
    <mark>System.out.println("Main 1");</mark>
    foo();
    System.out.println("Main 2");
    foo();
    System.out.println("Main 3");
    return;
  }<br>
  static void foo(){
    System.out.println("Foo 1");
    return;
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em"></p>
  </div>
</section>


<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Functions{
  public static void main(String[] args){
    <mark>System.out.println("Main 1");</mark>
    foo();
    System.out.println("Main 2");
    foo();
    System.out.println("Main 3");
    return;
  }<br>
  static void foo(){
    System.out.println("Foo 1");
    return;
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em"><mark>Main 1</mark></p>
  </div>
</section>


<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Functions{
  public static void main(String[] args){
    System.out.println("Main 1");
    <mark>foo();</mark>
    System.out.println("Main 2");
    foo();
    System.out.println("Main 3");
    return;
  }<br>
  static void foo(){
    System.out.println("Foo 1");
    return;
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1</p>
  </div>
</section>



<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Functions{
  public static void main(String[] args){
    System.out.println("Main 1");
    <mark>foo();</mark>
    System.out.println("Main 2");
    foo();
    System.out.println("Main 3");
    return;
  }<br>
  static void <mark>foo</mark>(){
    System.out.println("Foo 1");
    return;
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1</p>
  </div>
</section>



<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Functions{
  public static void main(String[] args){
    System.out.println("Main 1");
    <mark>foo();</mark>
    System.out.println("Main 2");
    foo();
    System.out.println("Main 3");
    return;
  }<br>
  static void foo(){
    <mark>System.out.println("Foo 1");</mark>
    return;
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1</p>
  </div>
</section>


<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Functions{
  public static void main(String[] args){
    System.out.println("Main 1");
    <mark>foo();</mark>
    System.out.println("Main 2");
    foo();
    System.out.println("Main 3");
    return;
  }<br>
  static void foo(){
    <mark>System.out.println("Foo 1");</mark>
    return;
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1<br><mark>Foo 1</mark></p>
  </div>
</section>


<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Functions{
  public static void main(String[] args){
    System.out.println("Main 1");
    <mark>foo();</mark>
    System.out.println("Main 2");
    foo();
    System.out.println("Main 3");
    return;
  }<br>
  static void foo(){
    System.out.println("Foo 1");
    <mark>return;</mark>
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1<br>Foo 1</p>
  </div>
</section>


<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Functions{
  public static void main(String[] args){
    System.out.println("Main 1");
    foo();
    <mark>System.out.println("Main 2");</mark>
    foo();
    System.out.println("Main 3");
    return;
  }<br>
  static void foo(){
    System.out.println("Foo 1");
    return;
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1<br>Foo 1</p>
  </div>
</section>


<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Functions{
  public static void main(String[] args){
    System.out.println("Main 1");
    foo();
    <mark>System.out.println("Main 2");</mark>
    foo();
    System.out.println("Main 3");
    return;
  }<br>
  static void foo(){
    System.out.println("Foo 1");
    return;
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1<br>Foo 1<br><mark>Main 2</mark></p>
  </div>
</section>



<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Functions{
  public static void main(String[] args){
    System.out.println("Main 1");
    foo();
    System.out.println("Main 2");
    <mark>foo();</mark>
    System.out.println("Main 3");
    return;
  }<br>
  static void foo(){
    System.out.println("Foo 1");
    return;
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1<br>Foo 1<br>Main 2</p>
  </div>
</section>


<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Functions{
  public static void main(String[] args){
    System.out.println("Main 1");
    foo();
    System.out.println("Main 2");
    <mark>foo();</mark>
    System.out.println("Main 3");
    return;
  }<br>
  <mark>static void foo(){
    System.out.println("Foo 1");
    return;
  }</mark>
}</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1<br>Foo 1<br>Main 2</p>
  </div>
</section>


<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Functions{
  public static void main(String[] args){
    System.out.println("Main 1");
    foo();
    System.out.println("Main 2");
    <mark>foo();</mark>
    System.out.println("Main 3");
    return;
  }<br>
  <mark>static void foo(){
    System.out.println("Foo 1");
    return;
  }</mark>
}</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1<br>Foo 1<br>Main 2<br><mark>Foo 1</mark></p>
  </div>
</section>


<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Functions{
  public static void main(String[] args){
    System.out.println("Main 1");
    foo();
    System.out.println("Main 2");
    foo();
    <mark>System.out.println("Main 3");</mark>
    return;
  }<br>
  static void foo(){
    System.out.println("Foo 1");
    return;
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1<br>Foo 1<br>Main 2<br>Foo 1</p>
  </div>
</section>


<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Functions{
  public static void main(String[] args){
    System.out.println("Main 1");
    foo();
    System.out.println("Main 2");
    foo();
    <mark>System.out.println("Main 3");</mark>
    return;
  }<br>
  static void foo(){
    System.out.println("Foo 1");
    return;
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1<br>Foo 1<br>Main 2<br>Foo 1<br><mark>Main 3</mark></p>
  </div>
</section>

<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Functions{
  public static void main(String[] args){
    System.out.println("Main 1");
    foo();
    System.out.println("Main 2");
    foo();
    System.out.println("Main 3");
    <mark>return;</mark>
  }<br>
  static void foo(){
    System.out.println("Foo 1");
    return;
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1<br>Foo 1<br>Main 2<br>Foo 1<br>Main 3</p>
  </div>
</section>


<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Functions{
  public static void main(String[] args){
    System.out.println("Main 1");
    foo();
    System.out.println("Main 2");
    foo();
    System.out.println("Main 3");
    return;
  }<br>
  static void foo(){
    System.out.println("Foo 1");
    return;
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <h4>Output:</h4>
    <p style="font-size: .7em">Main 1<br>Foo 1<br>Main 2<br>Foo 1<br>Main 3</p>
  </div>
</section>
