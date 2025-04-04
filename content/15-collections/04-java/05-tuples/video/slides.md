---
type: "reveal"
hidden: true
---
<section>
  <h3>Tuples</h3>
  <ul>
    <li>Finite ordered list of values</li>
    <li>Multiple values in a single object</li>
    <li>Similar to a simple class or list</li>
    <li><i>Not included in Java by default</i></li>
  </ul>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .6em"><code class="java">public class IntTuple{
  public int first;
  public int second;<br>
  public IntTuple(int one, int two){
    this.first = one;
    this.second = two;
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .6em"><code class="java">public class IntTuple{
  <mark>public int first;</mark>
  public int second;<br>
  public IntTuple(int one, int two){
    this.first = one;
    this.second = two;
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .6em"><code class="java">public class IntTuple{
  public int first;
  <mark>public int second;</mark><br>
  public IntTuple(int one, int two){
    this.first = one;
    this.second = two;
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .6em"><code class="java">public class IntTuple{
  public int first;
  public int second;<br>
  <mark>public IntTuple(int one, int two){
    this.first = one;
    this.second = two;
  }</mark>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .6em"><code class="java">public class IntTuple{
  public int first;
  public int second;<br>
  public IntTuple(int one, int two){
    this.first = one;
    this.second = two;
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class IntTuple{
  public int first;
  public int second;<br>
  public IntTuple(int one, int two){
    this.first = one;
    this.second = two;
  }<br>
  @Override
  public String toString(){
    return String.format("(%d, %d)", this.first, this.second);
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class IntTuple{
  public int first;
  public int second;<br>
  public IntTuple(int one, int two){
    this.first = one;
    this.second = two;
  }<br>
  @Override
  public String toString(){
    return String.format("(%d, %d)", this.first, this.second);
  }<br>
  @Override
  public boolean equals(Object obj){
    // code here
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .47em"><code class="java">@Override
public boolean equals(Object obj){<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .47em"><code class="java">@Override
public boolean equals(Object obj){
  //check of obj is null
  if(obj == null){
    return false;
  }<br><br><br><br><br><br><br><br><br><br><br><br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .47em"><code class="java">@Override
public boolean equals(Object obj){
  //check of obj is null
  if(obj == null){
    return false;
  }
  // check if they are the same instance
  if(this == obj){
    return true;
  }<br><br><br><br><br><br><br><br>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .47em"><code class="java">@Override
public boolean equals(Object obj){
  //check of obj is null
  if(obj == null){
    return false;
  }
  // check if they are the same instance
  if(this == obj){
    return true;
  }
  // check if obj is same type
  if(!(obj instanceof IntTuple)){
    return false;
  }<br><br><br><br>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .47em"><code class="java">@Override
public boolean equals(Object obj){
  //check of obj is null
  if(obj == null){
    return false;
  }
  // check if they are the same instance
  if(this == obj){
    return true;
  }
  // check if obj is same type
  if(!(obj instanceof IntTuple)){
    return false;
  }
  // cast to same type
  IntTuple tuple = (IntTuple)obj;<br><br>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .47em"><code class="java">@Override
public boolean equals(Object obj){
  //check of obj is null
  if(obj == null){
    return false;
  }
  // check if they are the same instance
  if(this == obj){
    return true;
  }
  // check if obj is same type
  if(!(obj instanceof IntTuple)){
    return false;
  }
  // cast to same type
  IntTuple tuple = (IntTuple)obj;
  // check if all fields are the same
  return tuple.first == this.first && tuple.second == this.second;
}</code></pre>
  </div>
</section><br><br><br><br>
<section>
  <p style="font-size: .6em">When a player makes a guess, the program should respond with one of the four cardinal directions: "North", "South", "East", "West", indicating the direction of the hidden item from the guess. For simplicity, the program will only respond "North" or "South" if the player's guess is not on the same row, or x coordinate, as the location, and "East" or "West" only if the player's guess is on the same row as the location. If the player guesses correctly, simply print "Found!" and terminate the program. If the player repeats a guess, the program should print "Repeat!" instead of a cardinal direction.</p>
  <p style="font-size: .6em">The hidden location should be randomly generated and stored in an instance of the IntTuple class defined above as a global variable, and the program should maintain a global list of IntTuples representing the locations already guessed.</p>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">import java.util.Random;
import java.util.List;
import java.util.LinkedList;<br>
public class TupleExample{<br>
  public static List&lt;IntTuple> guesses;
  public static Random random;
  public static IntTuple location;<br>
  public static String makeGuess(int x, int y){<br>
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">import java.util.Random;
import java.util.List;
import java.util.LinkedList;<br>
public class TupleExample{<br>
  public static List&lt;IntTuple> guesses;
  public static Random random;
  public static IntTuple location;<br>
  public static String makeGuess(int x, int y){
    if(guesses == null){
      guesses = new LinkedList&lt;IntTuple>();
    }
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">import java.util.Random;
import java.util.List;
import java.util.LinkedList;<br>
public class TupleExample{<br>
  public static List&lt;IntTuple> guesses;
  public static Random random;
  public static IntTuple location;<br>
  public static String makeGuess(int x, int y){
    if(guesses == null){
      guesses = new LinkedList&lt;IntTuple>();
    }
    if(random == null){
      random = new Random();
    }
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">import java.util.Random;
import java.util.List;
import java.util.LinkedList;<br>
public class TupleExample{<br>
  public static List&lt;IntTuple> guesses;
  public static Random random;
  public static IntTuple location;<br>
  public static String makeGuess(int x, int y){
    if(guesses == null){
      guesses = new LinkedList&lt;IntTuple>();
    }
    if(random == null){
      random = new Random();
    }
    if(location == null){
      location = new IntTuple(random.nextInt(10), random.nextInt(10));
    }
  }
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">import java.util.Random;
import java.util.List;
import java.util.LinkedList;<br>
public class TupleExample{<br>
  public static List&lt;IntTuple> guesses;
  public static Random random;
  public static IntTuple location;<br>
  public static String makeGuess(int x, int y){
    if(guesses == null){
      guesses = new LinkedList&lt;IntTuple>();
    }
    if(random == null){
      random = new Random();
    }
    if(location == null){
      location = new IntTuple(random.nextInt(10), random.nextInt(10));
    }
    <mark>// MORE CODE GOES HERE</mark>
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">IntTuple guess = new IntTuple(x, y);<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">IntTuple guess = new IntTuple(x, y);
if(guess.equals(location)){
  return "Found!";
}<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">IntTuple guess = new IntTuple(x, y);
if(guess.equals(location)){
  return "Found!";
}
if(guesses.contains(guess)){
  return "Repeat!";
}<br><br><br><br><br><br><br><br><br><br><br><br>
</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">IntTuple guess = new IntTuple(x, y);
if(guess.equals(location)){
  return "Found!";
}
if(guesses.contains(guess)){
  return "Repeat!";
}
guesses.add(guess);<br><br><br><br><br><br><br><br><br><br><br>
</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">IntTuple guess = new IntTuple(x, y);
if(guess.equals(location)){
  return "Found!";
}
if(guesses.contains(guess)){
  return "Repeat!";
}
guesses.add(guess);
if(guess.first > location.first){
  return "North";
}
if(guess.first &lt; location.first){
  return "South";
}<br><br><br><br><br>
</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="java">IntTuple guess = new IntTuple(x, y);
if(guess.equals(location)){
  return "Found!";
}
if(guesses.contains(guess)){
  return "Repeat!";
}
guesses.add(guess);
if(guess.first > location.first){
  return "North";
}
if(guess.first &lt; location.first){
  return "South";
}
if(guess.second > location.second){
  return "West";
}else{
  return "East";
}
</code></pre>
  </div>
</section><br>