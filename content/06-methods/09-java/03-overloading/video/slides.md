---
type: "reveal"
hidden: true
---
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .36em"><code class="java">public class Overloading{
  public static void main(String[] args){
    max(2, 3);
    max(3, 4, 5);
  }
<br>
  static void max(int x, int y){
    if(x >= y){
      System.out.println(x);
    }else{
      System.out.println(y);
    }
  }
<br>
  static void max(int x, int y, int z){
    if(x >= y){
      if(x >= z){
        System.out.println(x);
      }else{
        System.out.println(z);
      }
    }else{
      if(y >= z){
        System.out.println(y);
      }else{
        System.out.println(z);
      }
    }
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
    <pre class="stretch" style="font-size: .36em"><code class="java">public class Overloading{
  public static void <mark>main</mark>(String[] args){
    max(2, 3);
    max(3, 4, 5);
  }
<br>
  static void max(int x, int y){
    if(x >= y){
      System.out.println(x);
    }else{
      System.out.println(y);
    }
  }
<br>
  static void max(int x, int y, int z){
    if(x >= y){
      if(x >= z){
        System.out.println(x);
      }else{
        System.out.println(z);
      }
    }else{
      if(y >= z){
        System.out.println(y);
      }else{
        System.out.println(z);
      }
    }
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
    <pre class="stretch" style="font-size: .36em"><code class="java">public class Overloading{
  public static void main(String[] args){
    <mark>max(2, 3);</mark>
    max(3, 4, 5);
  }
<br>
  static void max(int x, int y){
    if(x >= y){
      System.out.println(x);
    }else{
      System.out.println(y);
    }
  }
<br>
  static void max(int x, int y, int z){
    if(x >= y){
      if(x >= z){
        System.out.println(x);
      }else{
        System.out.println(z);
      }
    }else{
      if(y >= z){
        System.out.println(y);
      }else{
        System.out.println(z);
      }
    }
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
    <pre class="stretch" style="font-size: .36em"><code class="java">public class Overloading{
  public static void main(String[] args){
    <mark>max(2, 3);</mark>
    max(3, 4, 5);
  }
<br>
  static void <mark>max</mark>(int x, int y){
    if(x >= y){
      System.out.println(x);
    }else{
      System.out.println(y);
    }
  }
<br>
  static void <mark>max</mark>(int x, int y, int z){
    if(x >= y){
      if(x >= z){
        System.out.println(x);
      }else{
        System.out.println(z);
      }
    }else{
      if(y >= z){
        System.out.println(y);
      }else{
        System.out.println(z);
      }
    }
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
    <pre class="stretch" style="font-size: .36em"><code class="java">public class Overloading{
  public static void main(String[] args){
    <mark>max(2, 3);</mark>
    max(3, 4, 5);
  }
<br>
  static void <mark>max(int x, int y)</mark>{
    if(x >= y){
      System.out.println(x);
    }else{
      System.out.println(y);
    }
  }
<br>
  static void <mark>max(int x, int y, int z)</mark>{
    if(x >= y){
      if(x >= z){
        System.out.println(x);
      }else{
        System.out.println(z);
      }
    }else{
      if(y >= z){
        System.out.println(y);
      }else{
        System.out.println(z);
      }
    }
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
    <pre class="stretch" style="font-size: .36em"><code class="java">public class Overloading{
  public static void main(String[] args){
    <mark>max(2, 3);</mark>
    max(3, 4, 5);
  }
<br>
  static void <mark>max(int x, int y)</mark>{
    if(x >= y){
      System.out.println(x);
    }else{
      System.out.println(y);
    }
  }
<br>
  static void max(int x, int y, int z){
    if(x >= y){
      if(x >= z){
        System.out.println(x);
      }else{
        System.out.println(z);
      }
    }else{
      if(y >= z){
        System.out.println(y);
      }else{
        System.out.println(z);
      }
    }
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
    <pre class="stretch" style="font-size: .36em"><code class="java">public class Overloading{
  public static void main(String[] args){
    <mark>max(2, 3);</mark>
    max(3, 4, 5);
  }
<br>
  static void <mark>max(int x, int y)</mark>{
    if(x >= y){
      System.out.println(x);
    }else{
      System.out.println(y);
    }
  }
<br>
  static void max(int x, int y, int z){
    if(x >= y){
      if(x >= z){
        System.out.println(x);
      }else{
        System.out.println(z);
      }
    }else{
      if(y >= z){
        System.out.println(y);
      }else{
        System.out.println(z);
      }
    }
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>max:</b><br>x = 2<br>y = 3</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .36em"><code class="java">public class Overloading{
  public static void main(String[] args){
    <mark>max(2, 3);</mark>
    max(3, 4, 5);
  }
<br>
  static void max(int x, int y){
    <mark>if(x >= y){
      System.out.println(x);
    }else{
      System.out.println(y);
    }</mark>
  }
<br>
  static void max(int x, int y, int z){
    if(x >= y){
      if(x >= z){
        System.out.println(x);
      }else{
        System.out.println(z);
      }
    }else{
      if(y >= z){
        System.out.println(y);
      }else{
        System.out.println(z);
      }
    }
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>max:</b><br>x = 2<br>y = 3</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .36em"><code class="java">public class Overloading{
  public static void main(String[] args){
    max(2, 3);
    <mark>max(3, 4, 5);</mark>
  }
<br>
  static void max(int x, int y){
    if(x >= y){
      System.out.println(x);
    }else{
      System.out.println(y);
    }
  }
<br>
  static void max(int x, int y, int z){
    if(x >= y){
      if(x >= z){
        System.out.println(x);
      }else{
        System.out.println(z);
      }
    }else{
      if(y >= z){
        System.out.println(y);
      }else{
        System.out.println(z);
      }
    }
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .36em"><code class="java">public class Overloading{
  public static void main(String[] args){
    max(2, 3);
    <mark>max(3, 4, 5);</mark>
  }
<br>
  static void max(int x, int y){
    if(x >= y){
      System.out.println(x);
    }else{
      System.out.println(y);
    }
  }
<br>
  static void <mark>max(int x, int y, int z)</mark>{
    if(x >= y){
      if(x >= z){
        System.out.println(x);
      }else{
        System.out.println(z);
      }
    }else{
      if(y >= z){
        System.out.println(y);
      }else{
        System.out.println(z);
      }
    }
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
    <pre class="stretch" style="font-size: .36em"><code class="java">public class Overloading{
  public static void main(String[] args){
    max(2, 3);
    <mark>max(3, 4, 5);</mark>
  }
<br>
  static void max(int x, int y){
    if(x >= y){
      System.out.println(x);
    }else{
      System.out.println(y);
    }
  }
<br>
  static void <mark>max(int x, int y, int z)</mark>{
    if(x >= y){
      if(x >= z){
        System.out.println(x);
      }else{
        System.out.println(z);
      }
    }else{
      if(y >= z){
        System.out.println(y);
      }else{
        System.out.println(z);
      }
    }
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>max</b><br>x = 3<br>y = 4<br>z = 5</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .36em"><code class="java">public class Overloading{
  public static void main(String[] args){
    max(2, 3);
    <mark>max(3, 4, 5);</mark>
  }
<br>
  static void max(int x, int y){
    if(x >= y){
      System.out.println(x);
    }else{
      System.out.println(y);
    }
  }
<br>
  static void max(int x, int y, int z){
    <mark>if(x >= y){
      if(x >= z){
        System.out.println(x);
      }else{
        System.out.println(z);
      }
    }else{
      if(y >= z){
        System.out.println(y);
      }else{
        System.out.println(z);
      }
    }</mark>
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>max</b><br>x = 3<br>y = 4<br>z = 5</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Overloading{
  public static void main(String[] args){
    max(2, 3);
    max(3, 4, 5);
    max(5, 6, 7, 8);
    max(10, 11, 12, 13, 14, 15, 16);
  }
<br>
  static void max(int ... values){
    if(values.length > 0){
      int max = values[0];
      for(int i : values){
        if(i > max){
          max = i;
        }
      }
      System.out.println(max);
    }
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
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Overloading{
  public static void main(String[] args){
    <mark>max(2, 3);</mark>
    max(3, 4, 5);
    max(5, 6, 7, 8);
    max(10, 11, 12, 13, 14, 15, 16);
  }
<br>
  static void max(int ... values){
    if(values.length > 0){
      int max = values[0];
      for(int i : values){
        if(i > max){
          max = i;
        }
      }
      System.out.println(max);
    }
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
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Overloading{
  public static void main(String[] args){
    <mark>max(2, 3);</mark>
    max(3, 4, 5);
    max(5, 6, 7, 8);
    max(10, 11, 12, 13, 14, 15, 16);
  }
<br>
  static void <mark>max(int ... values)</mark>{
    if(values.length > 0){
      int max = values[0];
      for(int i : values){
        if(i > max){
          max = i;
        }
      }
      System.out.println(max);
    }
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
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Overloading{
  public static void main(String[] args){
    <mark>max(2, 3);</mark>
    max(3, 4, 5);
    max(5, 6, 7, 8);
    max(10, 11, 12, 13, 14, 15, 16);
  }
<br>
  static void <mark>max(int ... values)</mark>{
    if(values.length > 0){
      int max = values[0];
      for(int i : values){
        if(i > max){
          max = i;
        }
      }
      System.out.println(max);
    }
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>max</b><br>values =<br>[2, 3]</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Overloading{
  public static void main(String[] args){
    <mark>max(2, 3);</mark>
    max(3, 4, 5);
    max(5, 6, 7, 8);
    max(10, 11, 12, 13, 14, 15, 16);
  }
<br>
  static void max(int ... values){
    <mark>if(values.length > 0){
      int max = values[0];
      for(int i : values){
        if(i > max){
          max = i;
        }
      }
      System.out.println(max);
    }</mark>
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>max</b><br>values =<br>[2, 3]</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Overloading{
  public static void main(String[] args){
    max(2, 3);
    <mark>max(3, 4, 5);</mark>
    max(5, 6, 7, 8);
    max(10, 11, 12, 13, 14, 15, 16);
  }
<br>
  static void max(int ... values){
    if(values.length > 0){
      int max = values[0];
      for(int i : values){
        if(i > max){
          max = i;
        }
      }
      System.out.println(max);
    }
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
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Overloading{
  public static void main(String[] args){
    max(2, 3);
    <mark>max(3, 4, 5);</mark>
    max(5, 6, 7, 8);
    max(10, 11, 12, 13, 14, 15, 16);
  }
<br>
  static void <mark>max(int ... values)</mark>{
    if(values.length > 0){
      int max = values[0];
      for(int i : values){
        if(i > max){
          max = i;
        }
      }
      System.out.println(max);
    }
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Overloading{
  public static void main(String[] args){
    max(2, 3);
    <mark>max(3, 4, 5);</mark>
    max(5, 6, 7, 8);
    max(10, 11, 12, 13, 14, 15, 16);
  }
<br>
  static void <mark>max(int ... values)</mark>{
    if(values.length > 0){
      int max = values[0];
      for(int i : values){
        if(i > max){
          max = i;
        }
      }
      System.out.println(max);
    }
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>max</b><br>values =<br>[3, 4, 5]</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Overloading{
  public static void main(String[] args){
    max(2, 3);
    max(3, 4, 5);
    <mark>max(5, 6, 7, 8);</mark>
    max(10, 11, 12, 13, 14, 15, 16);
  }
<br>
  static void <mark>max(int ... values)</mark>{
    if(values.length > 0){
      int max = values[0];
      for(int i : values){
        if(i > max){
          max = i;
        }
      }
      System.out.println(max);
    }
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>max</b><br>values =<br>[5, 6, 7, 8]</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 75%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Overloading{
  public static void main(String[] args){
    max(2, 3);
    max(3, 4, 5);
    max(5, 6, 7, 8);
    <mark>max(10, 11, 12, 13, 14, 15, 16);</mark>
  }
<br>
  static void <mark>max(int ... values)</mark>{
    if(values.length > 0){
      int max = values[0];
      for(int i : values){
        if(i > max){
          max = i;
        }
      }
      System.out.println(max);
    }
  }
}</code></pre>
  </div>
  <div style="width: 25%">
    <h4>Variables</h4>
    <p style="font-size: .7em"><b>max</b><br>values =<br>[10, 11, 12, 13, 14, 15, 16]</p>
  </div>
</section>
<br>