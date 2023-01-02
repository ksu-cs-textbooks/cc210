---
type: "reveal"
hidden: true
---
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .55em"><code class="java">public class Return{
  public static void main(String[] args){
    int returnValue = last(1, 3, 5, 7, 9);
    System.out.println(returnValue);
  }
<br>
  static int last(int ... items){
    if(items.length > 0){
      return items[items.length - 1];
    }
    return -1;
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
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .55em"><code class="java">public class Return{
  public static void <mark>main</mark>(String[] args){
    int returnValue = last(1, 3, 5, 7, 9);
    System.out.println(returnValue);
  }
<br>
  static int last(int ... items){
    if(items.length > 0){
      return items[items.length - 1];
    }
    return -1;
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
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .55em"><code class="java">public class Return{
  public static void main(String[] args){
    <mark>int returnValue = last(1, 3, 5, 7, 9);</mark>
    System.out.println(returnValue);
  }
<br>
  static int last(int ... items){
    if(items.length > 0){
      return items[items.length - 1];
    }
    return -1;
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
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .55em"><code class="java">public class Return{
  public static void main(String[] args){
    int returnValue = <mark>last(1, 3, 5, 7, 9);</mark>
    System.out.println(returnValue);
  }
<br>
  static int last(int ... items){
    if(items.length > 0){
      return items[items.length - 1];
    }
    return -1;
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
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .55em"><code class="java">public class Return{
  public static void main(String[] args){
    int returnValue = <mark>last(1, 3, 5, 7, 9);</mark>
    System.out.println(returnValue);
  }
<br>
  static int <mark>last(int ... items)</mark>{
    if(items.length > 0){
      return items[items.length - 1];
    }
    return -1;
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
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .55em"><code class="java">public class Return{
  public static void main(String[] args){
    int returnValue = <mark>last(1, 3, 5, 7, 9);</mark>
    System.out.println(returnValue);
  }
<br>
  static int <mark>last(int ... items)</mark>{
    if(items.length > 0){
      return items[items.length - 1];
    }
    return -1;
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>last</b><br>items =<br>[1, 3, 5, 7, 9]</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .55em"><code class="java">public class Return{
  public static void main(String[] args){
    int returnValue = <mark>last(1, 3, 5, 7, 9);</mark>
    System.out.println(returnValue);
  }
<br>
  static int last(int ... items){
    <mark>if(items.length > 0){</mark>
      return items[items.length - 1];
    }
    return -1;
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>last</b><br>items =<br>[1, 3, 5, 7, 9]</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .55em"><code class="java">public class Return{
  public static void main(String[] args){
    int returnValue = <mark>last(1, 3, 5, 7, 9);</mark>
    System.out.println(returnValue);
  }
<br>
  static int last(int ... items){
    if(items.length > 0){
      <mark>return items[items.length - 1];</mark>
    }
    return -1;
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>last</b><br>items =<br>[1, 3, 5, 7, 9]</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .55em"><code class="java">public class Return{
  public static void main(String[] args){
    int returnValue = <mark>last(1, 3, 5, 7, 9);</mark>
    System.out.println(returnValue);
  }
<br>
  static int last(int ... items){
    if(items.length > 0){
      <mark>return items[items.length - 1];</mark>
    }
    return -1;
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>last</b><br>items =<br>[1, 3, 5, 7, <mark>9</mark>]</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .55em"><code class="java">public class Return{
  public static void main(String[] args){
    int returnValue = <mark>9</mark>
    System.out.println(returnValue);
  }
<br>
  static int last(int ... items){
    if(items.length > 0){
      <mark>return items[items.length - 1];</mark>
    }
    return -1;
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>last</b><br>items =<br>[1, 3, 5, 7, <mark>9</mark>]</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .55em"><code class="java">public class Return{
  public static void main(String[] args){
    <mark>int returnValue = 9</mark>
    System.out.println(returnValue);
  }
<br>
  static int last(int ... items){
    if(items.length > 0){
      return items[items.length - 1];
    }
    return -1;
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>main</b><br>returnValue = 9</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .55em"><code class="java">public class Return{
  public static void main(String[] args){
    int returnValue = last(1, 3, 5, 7, 9);
    <mark>System.out.println(returnValue);</mark>
  }
<br>
  static int last(int ... items){
    if(items.length > 0){
      return items[items.length - 1];
    }
    return -1;
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>main</b><br>returnValue = 9</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .55em"><code class="java">public class Return{
  public static void main(String[] args){
    int returnValue = last(1, 3, 5, 7, 9);
    System.out.println(returnValue);
  }
<br>
  static int last(int ... items){
    if(items.length > 0){
      return items[items.length - 1];
    }
    <mark>return -1;</mark>
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"></p>
  </div>
</section>
<br>