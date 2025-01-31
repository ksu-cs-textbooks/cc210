---
type: "reveal"
hidden: true
---
<br>
<section>
  <pre class="stretch" style="font-size: .44em"><code class="java">// Load required classes
import java.util.Scanner;
import java.io.File;
<br>
public class Example{
<br>
  public static void main(String[] args) throws Exception{
    // Scanner variable
    Scanner reader;
<br>
    // If an argument is present, we are reading from a file
    // specified in args[0]
    if(args.length > 0){
      reader = new Scanner(new File(args[0]));
<br>
    // If no argument, read from System.in
    }else{
      reader = new Scanner(System.in);
    }
<br>
    <mark> -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- </mark>
<br>
  }
}
  </code></pre>
</section>
<br>
<section>
  <h2>Scanner Input</h2>
  <pre style="font-size: 1em">1 This 2.0 is true</pre>
  <p>Code:</p>
  <pre class="" style="font-size: .64em"><code class="java">int x = reader.nextInt();
String s1 = reader.next();
double d = reader.nextDouble();
String s2 = reader.next();
boolean b = reader.nextBoolean();</code></pre>
</section>
<br>
<section>
  <h2>Scanner Input</h2>
  <pre style="font-size: 1em"><mark>1</mark> This 2.0 is true</pre>
  <p>Code:</p>
  <pre class="" style="font-size: .64em"><code class="java"><mark>int x = reader.nextInt();</mark>
String s1 = reader.next();
double d = reader.nextDouble();
String s2 = reader.next();
boolean b = reader.nextBoolean();</code></pre>
</section>
<br>
<section>
  <h2>Scanner Input</h2>
  <pre style="font-size: 1em"><s>1 </s>This 2.0 is true</pre>
  <p>Code:</p>
  <pre class="" style="font-size: .64em"><code class="java">int x = reader.nextInt();         // x = 1
String s1 = reader.next();
double d = reader.nextDouble();
String s2 = reader.next();
boolean b = reader.nextBoolean();</code></pre>
</section>
<br>
<section>
  <h2>Scanner Input</h2>
  <pre style="font-size: 1em"><s>1 </s><mark>This</mark> 2.0 is true</pre>
  <p>Code:</p>
  <pre class="" style="font-size: .64em"><code class="java">int x = reader.nextInt();         // x = 1
<mark>String s1 = reader.next();</mark>
double d = reader.nextDouble();
String s2 = reader.next();
boolean b = reader.nextBoolean();</code></pre>
</section>
<br>
<section>
  <h2>Scanner Input</h2>
  <pre style="font-size: 1em"><s>1 This </s>2.0 is true</pre>
  <p>Code:</p>
  <pre class="" style="font-size: .64em"><code class="java">int x = reader.nextInt();         // x = 1
String s1 = reader.next();        // s1 = "This"
double d = reader.nextDouble();
String s2 = reader.next();
boolean b = reader.nextBoolean();</code></pre>
</section>
<br>
<section>
  <h2>Scanner Input</h2>
  <pre style="font-size: 1em"><s>1 This </s><mark>2.0</mark> is true</pre>
  <p>Code:</p>
  <pre class="" style="font-size: .64em"><code class="java">int x = reader.nextInt();         // x = 1
String s1 = reader.next();        // s1 = "This"
<mark>double d = reader.nextDouble();</mark>
String s2 = reader.next();
boolean b = reader.nextBoolean();</code></pre>
</section>
<br>
<section>
  <h2>Scanner Input</h2>
  <pre style="font-size: 1em"><s>1 This 2.0 </s>is true</pre>
  <p>Code:</p>
  <pre class="" style="font-size: .64em"><code class="java">int x = reader.nextInt();         // x = 1
String s1 = reader.next();        // s1 = "This"
double d = reader.nextDouble();   // d = 2.0
String s2 = reader.next();
boolean b = reader.nextBoolean();</code></pre>
</section>
<br>
<section>
  <h2>Scanner Input</h2>
  <pre style="font-size: 1em"><s>1 This 2.0 </s><mark>is</mark> true</pre>
  <p>Code:</p>
  <pre class="" style="font-size: .64em"><code class="java">int x = reader.nextInt();         // x = 1
String s1 = reader.next();        // s1 = "This"
double d = reader.nextDouble();   // d = 2.0
<mark>String s2 = reader.next();</mark>
boolean b = reader.nextBoolean();</code></pre>
</section>
<br>
<section>
  <h2>Scanner Input</h2>
  <pre style="font-size: 1em"><s>1 This 2.0 is </s>true</pre>
  <p>Code:</p>
  <pre class="" style="font-size: .64em"><code class="java">int x = reader.nextInt();         // x = 1
String s1 = reader.next();        // s1 = "This"
double d = reader.nextDouble();   // d = 2.0
String s2 = reader.next();        // s2 = "is"
boolean b = reader.nextBoolean();</code></pre>
</section>
<br>
<section>
  <h2>Scanner Input</h2>
  <pre style="font-size: 1em"><s>1 This 2.0 is </s><mark>true</mark></pre>
  <p>Code:</p>
  <pre class="" style="font-size: .64em"><code class="java">int x = reader.nextInt();         // x = 1
String s1 = reader.next();        // s1 = "This"
double d = reader.nextDouble();   // d = 2.0
String s2 = reader.next();        // s2 = "is"
<mark>boolean b = reader.nextBoolean();</mark></code></pre>
</section>
<br>
<section>
  <h2>Scanner Input</h2>
  <pre style="font-size: 1em"><s>1 This 2.0 is true</s></pre>
  <p>Code:</p>
  <pre class="" style="font-size: .64em"><code class="java">int x = reader.nextInt();         // x = 1
String s1 = reader.next();        // s1 = "This"
double d = reader.nextDouble();   // d = 2.0
String s2 = reader.next();        // s2 = "is"
boolean b = reader.nextBoolean(); // b = true</code></pre>
</section>
<br>
<section>
  <h2>Incorrect Input</h2>
  <pre style="font-size: 1em"><s>1 This 2.0 is </s><mark>not</mark> true</pre>
  <p>Code:</p>
  <pre class="" style="font-size: .64em"><code class="java">int x = reader.nextInt();         // x = 1
String s1 = reader.next();        // s1 = "This"
double d = reader.nextDouble();   // d = 2.0
String s2 = reader.next();        // s2 = "is"
<mark>boolean b = reader.nextBoolean();</mark></code></pre>
</section>
<br>
<section>
  <h2>Incorrect Input</h2>
  <pre style="font-size: 1em"><s>1 This 2.0 is </s><mark>not</mark> true</pre>
  <p>Code:</p>
  <pre class="" style="font-size: .64em"><code class="java">int x = reader.nextInt();         // x = 1
String s1 = reader.next();        // s1 = "This"
double d = reader.nextDouble();   // d = 2.0
String s2 = reader.next();        // s2 = "is"
<mark>boolean b = reader.nextBoolean();</mark>
<mark style="background-color: red"> java.util.InputMismatchException </mark></code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em">This 1
2.0 true</pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java">String line1 = reader.nextLine();
String[] line1Parts = line1.split(" ");
String s1 = line1Parts[0];
int x = Integer.parseInt(line1Parts[1]);
<br>
String line2 = reader.nextLine();
String[] line2Parts = line2.split(" ");
double d = Double.parseDouble(line2Parts[0]);
boolean b = Boolean.parseBoolean(line2Parts[1]);</code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em"><mark>This 1</mark>
2.0 true</pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java"><mark>String line1 = reader.nextLine();</mark>
String[] line1Parts = line1.split(" ");
String s1 = line1Parts[0];
int x = Integer.parseInt(line1Parts[1]);
<br>
String line2 = reader.nextLine();
String[] line2Parts = line2.split(" ");
double d = Double.parseDouble(line2Parts[0]);
boolean b = Boolean.parseBoolean(line2Parts[1]);</code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em"><s>This 1</s>
2.0 true</pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java">String line1 = reader.nextLine();       // "This 1"
String[] line1Parts = line1.split(" ");
String s1 = line1Parts[0];
int x = Integer.parseInt(line1Parts[1]);
<br>
String line2 = reader.nextLine();
String[] line2Parts = line2.split(" ");
double d = Double.parseDouble(line2Parts[0]);
boolean b = Boolean.parseBoolean(line2Parts[1]);</code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em"><s>This 1</s>
2.0 true</pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java">String line1 = reader.nextLine();       // "This 1"
<mark>String[] line1Parts = line1.split(" ");</mark>
String s1 = line1Parts[0];
int x = Integer.parseInt(line1Parts[1]);
<br>
String line2 = reader.nextLine();
String[] line2Parts = line2.split(" ");
double d = Double.parseDouble(line2Parts[0]);
boolean b = Boolean.parseBoolean(line2Parts[1]);</code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em"><s>This 1</s>
2.0 true</pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java">String line1 = reader.nextLine();       // <mark>"This 1"</mark>
<mark>String[] line1Parts = line1.split(" ");</mark>
String s1 = line1Parts[0];
int x = Integer.parseInt(line1Parts[1]);
<br>
String line2 = reader.nextLine();
String[] line2Parts = line2.split(" ");
double d = Double.parseDouble(line2Parts[0]);
boolean b = Boolean.parseBoolean(line2Parts[1]);</code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em"><s>This 1</s>
2.0 true</pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java">String line1 = reader.nextLine();       // "This 1"
String[] line1Parts = line1.split(" "); // ["This", "1"]
String s1 = line1Parts[0];
int x = Integer.parseInt(line1Parts[1]);
<br>
String line2 = reader.nextLine();
String[] line2Parts = line2.split(" ");
double d = Double.parseDouble(line2Parts[0]);
boolean b = Boolean.parseBoolean(line2Parts[1]);</code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em"><s>This 1</s>
2.0 true</pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java">String line1 = reader.nextLine();       // "This 1"
String[] line1Parts = line1.split(" "); // ["This", "1"]
<mark>String s1 = line1Parts[0];</mark>
int x = Integer.parseInt(line1Parts[1]);
<br>
String line2 = reader.nextLine();
String[] line2Parts = line2.split(" ");
double d = Double.parseDouble(line2Parts[0]);
boolean b = Boolean.parseBoolean(line2Parts[1]);</code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em"><s>This 1</s>
2.0 true</pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java">String line1 = reader.nextLine();       // "This 1"
String[] line1Parts = line1.split(" "); // [<mark>"This"</mark>, "1"]
<mark>String s1 = line1Parts[0];</mark>
int x = Integer.parseInt(line1Parts[1]);
<br>
String line2 = reader.nextLine();
String[] line2Parts = line2.split(" ");
double d = Double.parseDouble(line2Parts[0]);
boolean b = Boolean.parseBoolean(line2Parts[1]);</code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em"><s>This 1</s>
2.0 true</pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java">String line1 = reader.nextLine();       // "This 1"
String[] line1Parts = line1.split(" "); // ["This", "1"]
String s1 = line1Parts[0];              // "This"
int x = Integer.parseInt(line1Parts[1]);
<br>
String line2 = reader.nextLine();
String[] line2Parts = line2.split(" ");
double d = Double.parseDouble(line2Parts[0]);
boolean b = Boolean.parseBoolean(line2Parts[1]);</code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em"><s>This 1</s>
2.0 true</pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java">String line1 = reader.nextLine();       // "This 1"
String[] line1Parts = line1.split(" "); // ["This", "1"]
String s1 = line1Parts[0];              // "This"
<mark>int x = Integer.parseInt(line1Parts[1]);</mark>
<br>
String line2 = reader.nextLine();
String[] line2Parts = line2.split(" ");
double d = Double.parseDouble(line2Parts[0]);
boolean b = Boolean.parseBoolean(line2Parts[1]);</code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em"><s>This 1</s>
2.0 true</pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java">String line1 = reader.nextLine();       // "This 1"
String[] line1Parts = line1.split(" "); // ["This", <mark>"1"</mark>]
String s1 = line1Parts[0];              // "This"
int x = Integer.parseInt(<mark>line1Parts[1]</mark>);
<br>
String line2 = reader.nextLine();
String[] line2Parts = line2.split(" ");
double d = Double.parseDouble(line2Parts[0]);
boolean b = Boolean.parseBoolean(line2Parts[1]);</code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em"><s>This 1</s>
2.0 true</pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java">String line1 = reader.nextLine();       // "This 1"
String[] line1Parts = line1.split(" "); // ["This", <mark>"1"</mark>]
String s1 = line1Parts[0];              // "This"
int x = <mark>Integer.parseInt("1");</mark>
<br>
String line2 = reader.nextLine();
String[] line2Parts = line2.split(" ");
double d = Double.parseDouble(line2Parts[0]);
boolean b = Boolean.parseBoolean(line2Parts[1]);</code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em"><s>This 1</s>
2.0 true</pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java">String line1 = reader.nextLine();       // "This 1"
String[] line1Parts = line1.split(" "); // ["This", "1"]
String s1 = line1Parts[0];              // "This"
int x = Integer.parseInt(line1Parts[1]);// 1
<br>
String line2 = reader.nextLine();
String[] line2Parts = line2.split(" ");
double d = Double.parseDouble(line2Parts[0]);
boolean b = Boolean.parseBoolean(line2Parts[1]);</code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em"><s>This 1</s>
<mark>2.0 true</mark></pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java">String line1 = reader.nextLine();       // "This 1"
String[] line1Parts = line1.split(" "); // ["This", "1"]
String s1 = line1Parts[0];              // "This"
int x = Integer.parseInt(line1Parts[1]);// 1
<br>
<mark>String line2 = reader.nextLine();
String[] line2Parts = line2.split(" ");</mark>
double d = Double.parseDouble(line2Parts[0]);
boolean b = Boolean.parseBoolean(line2Parts[1]);</code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em"><s>This 1</s>
<s>2.0 true</s></pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java">String line1 = reader.nextLine();       // "This 1"
String[] line1Parts = line1.split(" "); // ["This", "1"]
String s1 = line1Parts[0];              // "This"
int x = Integer.parseInt(line1Parts[1]);// 1
<br>
String line2 = reader.nextLine();       // "2.0 true"
String[] line2Parts = line2.split(" "); // ["2.0", "true"]
double d = Double.parseDouble(line2Parts[0]);
boolean b = Boolean.parseBoolean(line2Parts[1]);</code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em"><s>This 1</s>
<s>2.0 true</s></pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java">String line1 = reader.nextLine();       // "This 1"
String[] line1Parts = line1.split(" "); // ["This", "1"]
String s1 = line1Parts[0];              // "This"
int x = Integer.parseInt(line1Parts[1]);// 1
<br>
String line2 = reader.nextLine();       // "2.0 true"
String[] line2Parts = line2.split(" "); // ["2.0", "true"]
<mark>double d = Double.parseDouble(line2Parts[0]);</mark>
boolean b = Boolean.parseBoolean(line2Parts[1]);</code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em"><s>This 1</s>
<s>2.0 true</s></pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java">String line1 = reader.nextLine();       // "This 1"
String[] line1Parts = line1.split(" "); // ["This", "1"]
String s1 = line1Parts[0];              // "This"
int x = Integer.parseInt(line1Parts[1]);// 1
<br>
String line2 = reader.nextLine();       // "2.0 true"
String[] line2Parts = line2.split(" "); // [<mark>"2.0"</mark>, "true"]
double d = Double.parseDouble(<mark>line2Parts[0]</mark>);
boolean b = Boolean.parseBoolean(line2Parts[1]);</code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em"><s>This 1</s>
<s>2.0 true</s></pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java">String line1 = reader.nextLine();       // "This 1"
String[] line1Parts = line1.split(" "); // ["This", "1"]
String s1 = line1Parts[0];              // "This"
int x = Integer.parseInt(line1Parts[1]);// 1
<br>
String line2 = reader.nextLine();       // "2.0 true"
String[] line2Parts = line2.split(" "); // ["2.0", "true"]
double d = <mark>Double.parseDouble("2.0");</mark>
boolean b = Boolean.parseBoolean(line2Parts[1]);</code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em"><s>This 1</s>
<s>2.0 true</s></pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java">String line1 = reader.nextLine();       // "This 1"
String[] line1Parts = line1.split(" "); // ["This", "1"]
String s1 = line1Parts[0];              // "This"
int x = Integer.parseInt(line1Parts[1]);// 1
<br>
String line2 = reader.nextLine();       // "2.0 true"
String[] line2Parts = line2.split(" "); // ["2.0", "true"]
double d = Double.parseDouble(line2Parts[0]);    // 2.0
boolean b = Boolean.parseBoolean(line2Parts[1]);</code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em"><s>This 1</s>
<s>2.0 true</s></pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java">String line1 = reader.nextLine();       // "This 1"
String[] line1Parts = line1.split(" "); // ["This", "1"]
String s1 = line1Parts[0];              // "This"
int x = Integer.parseInt(line1Parts[1]);// 1
<br>
String line2 = reader.nextLine();       // "2.0 true"
String[] line2Parts = line2.split(" "); // ["2.0", "true"]
double d = Double.parseDouble(line2Parts[0]);    // 2.0
<mark>boolean b = Boolean.parseBoolean(line2Parts[1]);</mark></code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em"><s>This 1</s>
<s>2.0 true</s></pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java">String line1 = reader.nextLine();       // "This 1"
String[] line1Parts = line1.split(" "); // ["This", "1"]
String s1 = line1Parts[0];              // "This"
int x = Integer.parseInt(line1Parts[1]);// 1
<br>
String line2 = reader.nextLine();       // "2.0 true"
String[] line2Parts = line2.split(" "); // ["2.0", <mark>"true"</mark>]
double d = Double.parseDouble(line2Parts[0]);    // 2.0
boolean b = Boolean.parseBoolean(<mark>line2Parts[1]</mark>);</code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em"><s>This 1</s>
<s>2.0 true</s></pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java">String line1 = reader.nextLine();       // "This 1"
String[] line1Parts = line1.split(" "); // ["This", "1"]
String s1 = line1Parts[0];              // "This"
int x = Integer.parseInt(line1Parts[1]);// 1
<br>
String line2 = reader.nextLine();       // "2.0 true"
String[] line2Parts = line2.split(" "); // ["2.0", <mark>"true"</mark>]
double d = Double.parseDouble(line2Parts[0]);    // 2.0
boolean b = <mark>Boolean.parseBoolean("true");</mark></code></pre>
</section>
<br>
<section>
  <h2>Split & Parse Input</h2>
  <pre style="font-size: 1em"><s>This 1</s>
<s>2.0 true</s></pre>
  <p>Code:</p>
  <pre class="stretch" style="font-size: .58em"><code class="java">String line1 = reader.nextLine();       // "This 1"
String[] line1Parts = line1.split(" "); // ["This", "1"]
String s1 = line1Parts[0];              // "This"
int x = Integer.parseInt(line1Parts[1]);// 1
<br>
String line2 = reader.nextLine();       // "2.0 true"
String[] line2Parts = line2.split(" "); // ["2.0", "true"]
double d = Double.parseDouble(line2Parts[0]);    // 2.0
boolean b = Boolean.parseBoolean(line2Parts[1]); // true</code></pre>
</section>
<br>