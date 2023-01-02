---
type: "reveal"
hidden: true
---
<br>
<section>
	<pre class="" style="font-size: .7em"><code class="java">static void foo(String message){
  System.out.println("Message: " + message);
}</code></pre>
</section>
<br>
<br>
<section>
	<pre class="" style="font-size: .7em"><code class="java">static void foo(<mark>String message</mark>){
  System.out.println("Message: " + message);
}</code></pre>
</section>
<br>
<br>
<section>
	<pre class="" style="font-size: .7em"><code class="java">static void foo(<mark>String</mark> message){
  System.out.println("Message: " + message);
}</code></pre>
</section>
<br>
<br>
<section>
	<pre class="" style="font-size: .7em"><code class="java">static void foo(String <mark>message</mark>){
  System.out.println("Message: " + message);
}</code></pre>
</section>
<br>
<br>
<section>
	<pre class="" style="font-size: .7em"><code class="java">static void foo(String <mark>message</mark>){
  System.out.println("Message: " + <mark>message</mark>);
}</code></pre>
</section>
<br>
<br>
<section>
	<pre class="" style="font-size: .7em"><code class="java">static void foo(String <mark>message</mark>){
  System.out.println("Message: " + <mark>message</mark>);
}</code></pre>
</section>
<br>
<br>
<section>
	<pre class="" style="font-size: .7em"><code class="java">static void foo(String message){
  System.out.println("Message: " + message);
}
<br>
//somewhere in another function
foo("Hello World!");</code></pre>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .44em"><code class="java">public class Parameters{
  public static void main(String[] args){
    int x = 5;
    int y = 10;
    int z = 8;
    bar(x, y, z);
    foo(y, true);
  }
<br>
  static void foo(int output, boolean longMessage){
    if(longMessage){
      System.out.println("The value was " + output);
    }else{
      System.out.println("Val: " + output);
    }
  }
<br>
  static void bar(int a, int b, int c){
    System.out.println(a + ", " + b + ", " + c);
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"></p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .44em"><code class="java">public class Parameters{
  public static void <mark>main</mark>(String[] args){
    int x = 5;
    int y = 10;
    int z = 8;
    bar(x, y, z);
    foo(y, true);
  }
<br>
  static void foo(int output, boolean longMessage){
    if(longMessage){
      System.out.println("The value was " + output);
    }else{
      System.out.println("Val: " + output);
    }
  }
<br>
  static void bar(int a, int b, int c){
    System.out.println(a + ", " + b + ", " + c);
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"></p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .44em"><code class="java">public class Parameters{
  public static void main(String[] args){
    <mark>int x = 5;
    int y = 10;
    int z = 8;</mark>
    bar(x, y, z);
    foo(y, true);
  }
<br>
  static void foo(int output, boolean longMessage){
    if(longMessage){
      System.out.println("The value was " + output);
    }else{
      System.out.println("Val: " + output);
    }
  }
<br>
  static void bar(int a, int b, int c){
    System.out.println(a + ", " + b + ", " + c);
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"></p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .44em"><code class="java">public class Parameters{
  public static void main(String[] args){
    <mark>int x = 5;
    int y = 10;
    int z = 8;</mark>
    bar(x, y, z);
    foo(y, true);
  }
<br>
  static void foo(int output, boolean longMessage){
    if(longMessage){
      System.out.println("The value was " + output);
    }else{
      System.out.println("Val: " + output);
    }
  }
<br>
  static void bar(int a, int b, int c){
    System.out.println(a + ", " + b + ", " + c);
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>main</b><br>x = 5<br>y = 10<br>z = 8</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .44em"><code class="java">public class Parameters{
  public static void main(String[] args){
    int x = 5;
    int y = 10;
    int z = 8;
    <mark>bar(x, y, z);</mark>
    foo(y, true);
  }
<br>
  static void foo(int output, boolean longMessage){
    if(longMessage){
      System.out.println("The value was " + output);
    }else{
      System.out.println("Val: " + output);
    }
  }
<br>
  static void bar(int a, int b, int c){
    System.out.println(a + ", " + b + ", " + c);
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>main</b><br>x = 5<br>y = 10<br>z = 8</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .44em"><code class="java">public class Parameters{
  public static void main(String[] args){
    int x = 5;
    int y = 10;
    int z = 8;
    <mark>bar(x, y, z);</mark>
    foo(y, true);
  }
<br>
  static void foo(int output, boolean longMessage){
    if(longMessage){
      System.out.println("The value was " + output);
    }else{
      System.out.println("Val: " + output);
    }
  }
<br>
  static void <mark>bar</mark>(int a, int b, int c){
    System.out.println(a + ", " + b + ", " + c);
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>main</b><br>x = 5<br>y = 10<br>z = 8</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .44em"><code class="java">public class Parameters{
  public static void main(String[] args){
    int x = 5;
    int y = 10;
    int z = 8;
    bar(<mark>x</mark>, y, z);
    foo(y, true);
  }
<br>
  static void foo(int output, boolean longMessage){
    if(longMessage){
      System.out.println("The value was " + output);
    }else{
      System.out.println("Val: " + output);
    }
  }
<br>
  static void bar(<mark>int a</mark>, int b, int c){
    System.out.println(a + ", " + b + ", " + c);
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>main</b><br>x = 5<br>y = 10<br>z = 8</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .44em"><code class="java">public class Parameters{
  public static void main(String[] args){
    int x = 5;
    int y = 10;
    int z = 8;
    bar(<mark>x</mark>, y, z);
    foo(y, true);
  }
<br>
  static void foo(int output, boolean longMessage){
    if(longMessage){
      System.out.println("The value was " + output);
    }else{
      System.out.println("Val: " + output);
    }
  }
<br>
  static void bar(<mark>int a</mark>, int b, int c){
    System.out.println(a + ", " + b + ", " + c);
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>main</b><br>x = 5<br>y = 10<br>z = 8<br><br><b>bar</b><br><mark>a = 5</mark></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .44em"><code class="java">public class Parameters{
  public static void main(String[] args){
    int x = 5;
    int y = 10;
    int z = 8;
    bar(x, <mark>y</mark>, z);
    foo(y, true);
  }
<br>
  static void foo(int output, boolean longMessage){
    if(longMessage){
      System.out.println("The value was " + output);
    }else{
      System.out.println("Val: " + output);
    }
  }
<br>
  static void bar(int a, <mark>int b</mark>, int c){
    System.out.println(a + ", " + b + ", " + c);
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>main</b><br>x = 5<br>y = 10<br>z = 8<br><br><b>bar</b><br>a = 5<br><mark>b = 10</mark></p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .44em"><code class="java">public class Parameters{
  public static void main(String[] args){
    int x = 5;
    int y = 10;
    int z = 8;
    bar(x, y, <mark>z</mark>);
    foo(y, true);
  }
<br>
  static void foo(int output, boolean longMessage){
    if(longMessage){
      System.out.println("The value was " + output);
    }else{
      System.out.println("Val: " + output);
    }
  }
<br>
  static void bar(int a, int b, <mark>int c</mark>){
    System.out.println(a + ", " + b + ", " + c);
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>main</b><br>x = 5<br>y = 10<br>z = 8<br><br><b>bar</b><br>a = 5<br>b = 10<br><mark>c = 8</mark></p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .44em"><code class="java">public class Parameters{
  public static void main(String[] args){
    int x = 5;
    int y = 10;
    int z = 8;
    <mark>bar(x, y, z);</mark>
    foo(y, true);
  }
<br>
  static void foo(int output, boolean longMessage){
    if(longMessage){
      System.out.println("The value was " + output);
    }else{
      System.out.println("Val: " + output);
    }
  }
<br>
  static void bar(int a, int b, int c){
    <mark>System.out.println(a + ", " + b + ", " + c);</mark>
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>main</b><br>x = 5<br>y = 10<br>z = 8<br><br><b>bar</b><br>a = 5<br>b = 10<br>c = 8</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .44em"><code class="java">public class Parameters{
  public static void main(String[] args){
    int x = 5;
    int y = 10;
    int z = 8;
    bar(x, y, z);
    <mark>foo(y, true);</mark>
  }
<br>
  static void foo(int output, boolean longMessage){
    if(longMessage){
      System.out.println("The value was " + output);
    }else{
      System.out.println("Val: " + output);
    }
  }
<br>
  static void bar(int a, int b, int c){
    System.out.println(a + ", " + b + ", " + c);
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>main</b><br>x = 5<br>y = 10<br>z = 8</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .44em"><code class="java">public class Parameters{
  public static void main(String[] args){
    int x = 5;
    int y = 10;
    int z = 8;
    bar(x, y, z);
    <mark>foo(y, true);</mark>
  }
<br>
  static void <mark>foo(int output, boolean longMessage)</mark>{
    if(longMessage){
      System.out.println("The value was " + output);
    }else{
      System.out.println("Val: " + output);
    }
  }
<br>
  static void bar(int a, int b, int c){
    System.out.println(a + ", " + b + ", " + c);
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>main</b><br>x = 5<br>y = 10<br>z = 8</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .44em"><code class="java">public class Parameters{
  public static void main(String[] args){
    int x = 5;
    int y = 10;
    int z = 8;
    bar(x, y, z);
    <mark>foo(y, true);</mark>
  }
<br>
  static void <mark>foo(int output, boolean longMessage)</mark>{
    if(longMessage){
      System.out.println("The value was " + output);
    }else{
      System.out.println("Val: " + output);
    }
  }
<br>
  static void bar(int a, int b, int c){
    System.out.println(a + ", " + b + ", " + c);
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>main</b><br>x = 5<br>y = 10<br>z = 8<br><br><b>foo</b><br>output = 10<br>longMessage = true</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .44em"><code class="java">public class Parameters{
  public static void main(String[] args){
    int x = 5;
    int y = 10;
    int z = 8;
    bar(x, y, z);
    <mark>foo(y, true);</mark>
  }
<br>
  static void foo(int output, boolean longMessage){
    <mark>if(longMessage){
      System.out.println("The value was " + output);
    }else{
      System.out.println("Val: " + output);
    }</mark>
  }
<br>
  static void bar(int a, int b, int c){
    System.out.println(a + ", " + b + ", " + c);
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>main</b><br>x = 5<br>y = 10<br>z = 8<br><br><b>foo</b><br>output = 10<br>longMessage = true</p>
  </div>
</section>
<br>