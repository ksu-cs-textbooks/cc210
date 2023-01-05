---
type: "reveal"
hidden: true
---
<section>
  <h3>Maps (Dictionaries)</h3>
  <ul>
    <li>Associate <b>key</b> with <b>value</b></li>
    <li>Key & value can be any data type</li>
    <li>Easily searchable by key</li>
    <li>Store and retrieve data quickly</li>
  </ul>
</section>
<section>
  <p style="font-size: .7em">The program will store a map that associates lines of input with random integers. When a line of input is read, the program will check to see if that line has already been used as a key in the map. If so, it will return the value associated with that key.</p>
  <p style="font-size: .7em">If the map does not contain an entry for that key, the program should generate a new random integer and store it in the map, using the input line as the key.</p>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">import java.util.Map;
import java.util.HashMap;
import java.util.Random;<br>
public class MapExample{<br>
  public static Map&lt;String, Integer> map;
  public static Random random;<br>
  public static int getOutput(String inp){<br>
  }
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">import java.util.Map;
import java.util.HashMap;
import java.util.Random;<br>
public class MapExample{<br>
  public static Map&lt;String, Integer> map;
  public static Random random;<br>
  public static int getOutput(String inp){
    if(map == null){
      map = new HashMap&lt;String, Integer>();
    }
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">import java.util.Map;
import java.util.HashMap;
import java.util.Random;<br>
public class MapExample{<br>
  public static <mark>Map&lt;String, Integer> map</mark>;
  public static Random random;<br>
  public static int getOutput(String inp){
    if(map == null){
      map = new HashMap&lt;String, Integer>();
    }
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">import java.util.Map;
import java.util.HashMap;
import java.util.Random;<br>
public class MapExample{<br>
  public static Map&lt;String, Integer> map;
  public static Random random;<br>
  public static int getOutput(String inp){
    if(map == null){
      map = new <mark>HashMap&lt;String, Integer>()</mark>;
    }
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">import java.util.Map;
import java.util.HashMap;
import java.util.Random;<br>
public class MapExample{<br>
  public static Map<mark>&lt;String, Integer></mark> map;
  public static Random random;<br>
  public static int getOutput(String inp){
    if(map == null){
      map = new HashMap<mark>&lt;String, Integer></mark>();
    }
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">import java.util.Map;
import java.util.HashMap;
import java.util.Random;<br>
public class MapExample{<br>
  public static Map&lt;String, Integer> map;
  public static Random random;<br>
  public static int getOutput(String inp){
    if(map == null){
      map = new HashMap&lt;String, Integer>();
    }
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">import java.util.Map;
import java.util.HashMap;
import java.util.Random;<br>
public class MapExample{<br>
  public static Map&lt;String, Integer> map;
  public static Random random;<br>
  public static int getOutput(String inp){
    if(map == null){
      map = new HashMap&lt;String, Integer>();
    }
    if(random == null){
      random = new Random();
    }
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">import java.util.Map;
import java.util.HashMap;
import java.util.Random;<br>
public class MapExample{<br>
  public static Map&lt;String, Integer> map;
  public static Random random;<br>
  public static int getOutput(String inp){
    if(map == null){
      map = new HashMap&lt;String, Integer>();
    }
    if(random == null){
      random = new Random();
    }
    if(map.containsKey(inp)){<br>
    }
  }
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">import java.util.Map;
import java.util.HashMap;
import java.util.Random;<br>
public class MapExample{<br>
  public static Map&lt;String, Integer> map;
  public static Random random;<br>
  public static int getOutput(String inp){
    if(map == null){
      map = new HashMap&lt;String, Integer>();
    }
    if(random == null){
      random = new Random();
    }
    if(map.containsKey(inp)){
      return map.get(inp);
    }
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">import java.util.Map;
import java.util.HashMap;
import java.util.Random;<br>
public class MapExample{<br>
  public static Map&lt;String, Integer> map;
  public static Random random;<br>
  public static int getOutput(String inp){
    if(map == null){
      map = new HashMap&lt;String, Integer>();
    }
    if(random == null){
      random = new Random();
    }
    if(map.containsKey(inp)){
      return map.get(inp);
    }else{
      int newNumber = random.nextInt();<br><br>
    }
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">import java.util.Map;
import java.util.HashMap;
import java.util.Random;<br>
public class MapExample{<br>
  public static Map&lt;String, Integer> map;
  public static Random random;<br>
  public static int getOutput(String inp){
    if(map == null){
      map = new HashMap&lt;String, Integer>();
    }
    if(random == null){
      random = new Random();
    }
    if(map.containsKey(inp)){
      return map.get(inp);
    }else{
      int newNumber = random.nextInt();
      map.put(inp, newNumber);<br>
    }
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">import java.util.Map;
import java.util.HashMap;
import java.util.Random;<br>
public class MapExample{<br>
  public static Map&lt;String, Integer> map;
  public static Random random;<br>
  public static int getOutput(String inp){
    if(map == null){
      map = new HashMap&lt;String, Integer>();
    }
    if(random == null){
      random = new Random();
    }
    if(map.containsKey(inp)){
      return map.get(inp);
    }else{
      int newNumber = random.nextInt();
      map.put(inp, newNumber);
      return newNumber;
    }
  }
}</code></pre>
  </div>
</section><br>