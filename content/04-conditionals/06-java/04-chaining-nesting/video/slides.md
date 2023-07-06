---
type: "reveal"
hidden: true
---

<section>
  <img class="stretch plain" src="/images/04-cond/chaining1.png">
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch"><code class="java">
    </code></pre>
  </div>
  <div style="width: 30%">
    <img class="plain" src="/images/04-cond/chaining1.png">
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch"><code class="java">
    </code></pre>
  </div>
  <div style="width: 30%">
    <img class="plain" src="/images/04-cond/chaining2.png">
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch"><code class="java"><mark>public static void main(String[] args){

}</mark></code></pre>
  </div>
  <div style="width: 30%">
    <img class="plain" src="/images/04-cond/chaining2.png">
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch"><code class="java">public static void main(String[] args){

}</code></pre>
  </div>
  <div style="width: 30%">
    <img class="plain" src="/images/04-cond/chaining3.png">
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch"><code class="java">public static void main(String[] args){
  <mark>int x = 3;</mark>
}</code></pre>
  </div>
  <div style="width: 30%">
    <img class="plain" src="/images/04-cond/chaining3.png">
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch"><code class="java">public static void main(String[] args){
  int x = 3;
}</code></pre>
  </div>
  <div style="width: 30%">
    <img class="plain" src="/images/04-cond/chaining4.png">
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch"><code class="java">public static void main(String[] args){
  int x = 3;
  <mark>if(x < 0){

  }</mark>
}</code></pre>
  </div>
  <div style="width: 30%">
    <img class="plain" src="/images/04-cond/chaining4.png">
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch"><code class="java">public static void main(String[] args){
  int x = 3;
  if(x < 0){

  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <img class="plain" src="/images/04-cond/chaining5.png">
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch"><code class="java">public static void main(String[] args){
  int x = 3;
  if(x < 0){
    <mark>System.out.println(-1);</mark>
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <img class="plain" src="/images/04-cond/chaining5.png">
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch"><code class="java">public static void main(String[] args){
  int x = 3;
  if(x < 0){
    System.out.println(-1);
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <img class="plain" src="/images/04-cond/chaining6.png">
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch"><code class="java">public static void main(String[] args){
  int x = 3;
  if(x < 0){
    System.out.println(-1);
  }
  <mark>if(x == 0){
    System.out.println(0);
  }</mark>
}</code></pre>
  </div>
  <div style="width: 30%">
    <img class="plain" src="/images/04-cond/chaining6.png">
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch"><code class="java">public static void main(String[] args){
  int x = 3;
  if(x < 0){
    System.out.println(-1);
  }
  if(x == 0){
    System.out.println(0);
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <img class="plain" src="/images/04-cond/chaining7.png">
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch"><code class="java">public static void main(String[] args){
  int x = 3;
  if(x < 0){
    System.out.println(-1);
  }
  if(x == 0){
    System.out.println(0);
  }
  <mark>if(x > 0){
    System.out.println(1);
  }</mark>
}</code></pre>
  </div>
  <div style="width: 30%">
    <img class="plain" src="/images/04-cond/chaining7.png">
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch"><code class="java">public static void main(String[] args){
  int x = 3;
  if(x < 0){
    System.out.println(-1);
  }
  if(x == 0){
    System.out.println(0);
  }
  if(x > 0){
    System.out.println(1);
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <img class="plain" src="/images/04-cond/chaining1.png">
  </div>
</section>
<section>
  <img class="stretch plain" src="/images/04-cond/nesting1.png">
</section>
<section>
  <div style="float: right; width: 60%">
    <pre class="stretch"><code class="java">
    </code></pre>
  </div>
  <div style="width: 40%">
    <img class="plain" src="/images/04-cond/nesting2.png">
  </div>
</section>
<section>
  <div style="float: right; width: 60%">
    <pre class="stretch"><code class="java">
    </code></pre>
  </div>
  <div style="width: 40%">
    <img class="plain" src="/images/04-cond/nesting3.png">
  </div>
</section>
<section>
  <div style="float: right; width: 60%">
    <pre class="stretch" style="font-size: 0.45em"><code class="java"><mark>public static void main(String[] args){
  int x = 3;
}</mark></code></pre>
  </div>
  <div style="width: 40%">
    <img class="plain" src="/images/04-cond/nesting3.png">
  </div>
</section>
<section>
  <div style="float: right; width: 60%">
    <pre class="stretch" style="font-size: 0.45em"><code class="java">public static void main(String[] args){
  int x = 3;
}</code></pre>
  </div>
  <div style="width: 40%">
    <img class="plain" src="/images/04-cond/nesting4.png">
  </div>
</section>
<section>
  <div style="float: right; width: 60%">
    <pre class="stretch" style="font-size: 0.45em"><code class="java">public static void main(String[] args){
  int x = 3;
  <mark>if(x < 0){

  }else{

  }</mark>
}</code></pre>
  </div>
  <div style="width: 40%">
    <img class="plain" src="/images/04-cond/nesting4.png">
  </div>
</section>
<section>
  <div style="float: right; width: 60%">
    <pre class="stretch" style="font-size: 0.45em"><code class="java">public static void main(String[] args){
  int x = 3;
  if(x < 0){

  }else{

  }
}</code></pre>
  </div>
  <div style="width: 40%">
    <img class="plain" src="/images/04-cond/nesting5.png">
  </div>
</section>
<section>
  <div style="float: right; width: 60%">
    <pre class="stretch" style="font-size: 0.45em"><code class="java">public static void main(String[] args){
  int x = 3;
  if(x < 0){
    <mark>System.out.println(-1);</mark>
  }else{

  }
}</code></pre>
  </div>
  <div style="width: 40%">
    <img class="plain" src="/images/04-cond/nesting5.png">
  </div>
</section>
<section>
  <div style="float: right; width: 60%">
    <pre class="stretch" style="font-size: 0.45em"><code class="java">public static void main(String[] args){
  int x = 3;
  if(x < 0){
    System.out.println(-1);
  }else{

  }
}</code></pre>
  </div>
  <div style="width: 40%">
    <img class="plain" src="/images/04-cond/nesting6.png">
  </div>
</section>
<section>
  <div style="float: right; width: 60%">
    <pre class="stretch" style="font-size: 0.45em"><code class="java">public static void main(String[] args){
  int x = 3;
  if(x < 0){
    System.out.println(-1);
  }else{
    <mark>if(x == 0){

    }else{

    }</mark>
  }
}</code></pre>
  </div>
  <div style="width: 40%">
    <img class="plain" src="/images/04-cond/nesting6.png">
  </div>
</section>
<section>
  <div style="float: right; width: 60%">
    <pre class="stretch" style="font-size: 0.45em"><code class="java">public static void main(String[] args){
  int x = 3;
  if(x < 0){
    System.out.println(-1);
  }else{
    if(x == 0){

    }else{

    }
  }
}</code></pre>
  </div>
  <div style="width: 40%">
    <img class="plain" src="/images/04-cond/nesting7.png">
  </div>
</section>
<section>
  <div style="float: right; width: 60%">
    <pre class="stretch" style="font-size: 0.45em"><code class="java">public static void main(String[] args){
  int x = 3;
  if(x < 0){
    System.out.println(-1);
  }else{
    if(x == 0){
      <mark>System.out.println(0);</mark>
    }else{
      <mark>System.out.println(1);</mark>
    }
  }
}</code></pre>
  </div>
  <div style="width: 40%">
    <img class="plain" src="/images/04-cond/nesting7.png">
  </div>
</section>
<section>
  <div style="float: right; width: 60%">
    <pre class="stretch" style="font-size: 0.45em"><code class="java">public static void main(String[] args){
  int x = 3;
  if(x < 0){
    System.out.println(-1);
  }else{
    if(x == 0){
      System.out.println(0);
    }else{
      System.out.println(1);
    }
  }
}</code></pre>
  </div>
  <div style="width: 40%">
    <img class="plain" src="/images/04-cond/nesting2.png">
  </div>
</section>
<section>
  <div style="float: right; width: 60%">
    <pre class="stretch" style="font-size: 0.45em"><code class="java">public static void main(String[] args){
  int x = 3;
  if(x < 0){
    System.out.println(-1);
  }else <mark>if(x == 0){
    System.out.println(0);
  }else if(x > 0){
    System.out.println(1);
  }</mark>
}</code></pre>
  </div>
  <div style="width: 40%">
    <img class="plain" src="/images/04-cond/nesting2.png">
  </div>
</section>
<section>
  <div style="float: right; width: 60%">
    <pre class="stretch" style="font-size: 0.45em"><code class="java">public static void main(String[] args){
  int x = 3;
  if(x < 0){
    System.out.println(-1);
  }else if(x == 0){
    System.out.println(0);
  }else if(x > 0){
    System.out.println(1);
  }<mark>else{
    //this should never happen
    System.out.println("ERROR!");
  }</mark>
}</code></pre>
  </div>
  <div style="width: 40%">
    <img class="plain" src="/images/04-cond/nesting2.png">
  </div>
</section>
<section>
  <div style="float: right; width: 60%">
    <pre class="stretch" style="font-size: 0.45em"><code class="java">public static void main(String[] args){
  int x = 3;
  if(x < 0){
    System.out.println(-1);
  }else if(x == 0){
    System.out.println(0);
  }else if(x > 0){
    System.out.println(1);
  }else{
    //this should never happen
    System.out.println("ERROR!");
  }
}</code></pre>
  </div>
  <div style="width: 40%">
    <img class="plain" src="/images/04-cond/nesting2.png">
  </div>
</section>
