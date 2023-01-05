---
type: "reveal"
hidden: true
---
<section>
  <h3>Lists</h3>
  <ul>
    <li>Store Any Number of Elements</li>
    <li>Searchable</li>
    <li>Remove Elements</li>
    <li>Sortable</li>
  </ul>
</section>
<section>
  <p style="font-size: .7em">Using the integer provided as input, the program should generate a list of numbers representing the <b>Fibonacci sequence</b> containing that many entries.</p>
  <p style="font-size: .7em">Before printing the list, the program should perform two additional operations on the list. First, if the <b>integer provided as input</b> is contained in the list, it <b>should be removed</b>. Secondly, the list should be presented in <b>descending order</b>, with the largest value first.</p>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="java">public static List&lt;Integer> makeList(int x){<br>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="java">public static List&lt;Integer> makeList(int x){
  List&lt;Integer> list = new ArrayList&lt;Integer>();<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="java">public static List&lt;Integer> makeList(int x){
  <mark>List</mark>&lt;Integer> list = new ArrayList&lt;Integer>();<br>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="java">public static List&lt;Integer> makeList(int x){
  List&lt;Integer> list = new <mark>ArrayList</mark>&lt;Integer>();<br>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="java">public static List&lt;Integer> makeList(int x){
  List<mark>&lt;Integer></mark> list = new ArrayList<mark>&lt;Integer></mark>();<br>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="java">public static <mark>List&lt;Integer></mark> makeList(int x){
  List&lt;Integer> list = new ArrayList&lt;Integer>();<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="java">public static List&lt;Integer> makeList(int x){
  List&lt;Integer> list = new ArrayList&lt;Integer>();<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="java">public static List&lt;Integer> makeList(int x){
  List&lt;Integer> list = new ArrayList&lt;Integer>();
  list.add(0);
  list.add(1);
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="java">public static List&lt;Integer> makeList(int x){
  List&lt;Integer> list = new ArrayList&lt;Integer>();
  list.add(0);
  list.add(1);
  for(int i = 2; i &lt; x; i++){<br><br>
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="java">public static List&lt;Integer> makeList(int x){
  List&lt;Integer> list = new ArrayList&lt;Integer>();
  list.add(0);
  list.add(1);
  for(int i = 2; i &lt; x; i++){
    int newNumber = list.get(i-1) + list.get(i-2);<br>
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="java">public static List&lt;Integer> makeList(int x){
  List&lt;Integer> list = new ArrayList&lt;Integer>();
  list.add(0);
  list.add(1);
  for(int i = 2; i &lt; x; i++){
    int newNumber = list.get(i-1) + list.get(i-2);
    list.add(newNumber);
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="java">public static List&lt;Integer> makeList(int x){
  List&lt;Integer> list = new ArrayList&lt;Integer>();
  list.add(0);
  list.add(1);
  for(int i = 2; i &lt; x; i++){
    int newNumber = list.get(i-1) + list.get(i-2);
    list.add(newNumber);
  }
  list.remove(x);
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="java">public static List&lt;Integer> makeList(int x){
  List&lt;Integer> list = new ArrayList&lt;Integer>();
  list.add(0);
  list.add(1);
  for(int i = 2; i &lt; x; i++){
    int newNumber = list.get(i-1) + list.get(i-2);
    list.add(newNumber);
  }
  <mark style="background-color: red">list.remove(x);</mark>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="java">public static List&lt;Integer> makeList(<mark>int x</mark>){
  List<mark>&lt;Integer></mark> list = new ArrayList&lt;Integer>();
  list.add(0);
  list.add(1);
  for(int i = 2; i &lt; x; i++){
    int newNumber = list.get(i-1) + list.get(i-2);
    list.add(newNumber);
  }
  <mark style="background-color: red">list.remove(x);</mark>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="java">public static List&lt;Integer> makeList(int x){
  List&lt;Integer> list = new ArrayList&lt;Integer>();
  list.add(0);
  list.add(1);
  for(int i = 2; i &lt; x; i++){
    int newNumber = list.get(i-1) + list.get(i-2);
    list.add(newNumber);
  }
  list.remove(<mark>(Integer)</mark>x);
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="java">public static List&lt;Integer> makeList(int x){
  List&lt;Integer> list = new ArrayList&lt;Integer>();
  list.add(0);
  list.add(1);
  for(int i = 2; i &lt; x; i++){
    int newNumber = list.get(i-1) + list.get(i-2);
    list.add(newNumber);
  }
  list.remove((Integer)x);
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="java">public static List&lt;Integer> makeList(int x){
  List&lt;Integer> list = new ArrayList&lt;Integer>();
  list.add(0);
  list.add(1);
  for(int i = 2; i &lt; x; i++){
    int newNumber = list.get(i-1) + list.get(i-2);
    list.add(newNumber);
  }
  list.remove((Integer)x);
  Collections.sort(list, Collections.reverseOrder());
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="java">public static List&lt;Integer> makeList(int x){
  List&lt;Integer> list = new ArrayList&lt;Integer>();
  list.add(0);
  list.add(1);
  for(int i = 2; i &lt; x; i++){
    int newNumber = list.get(i-1) + list.get(i-2);
    list.add(newNumber);
  }
  list.remove((Integer)x);
  Collections.sort(list, Collections.reverseOrder());
  return list;
}</code></pre>
  </div>
</section><br>