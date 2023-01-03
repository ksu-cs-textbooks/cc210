---
type: "reveal"
hidden: true
---<br>
<section>
	<img class="stretch plain" src="/images/10-except/8.4.handle.png">
</section><br>
<section>
	<img class="stretch plain" src="/images/10-except/8.4.try.png">
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
# If an argument is present, we are reading from a file
# specified in sys.argv[1]
if len(sys.argv) > 1:
  reader = open(sys.argv[1])<br>
# If no argument, read from stdin
else:
  reader = sys.stdin<br>
x = int(reader.readline())
print(x)
</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
<mark>try:</mark>
# If an argument is present, we are reading from a file
# specified in sys.argv[1]
if len(sys.argv) > 1:
  reader = open(sys.argv[1])<br>
# If no argument, read from stdin
else:
  reader = sys.stdin<br>
x = int(reader.readline())
print(x)
</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
<mark># If an argument is present, we are reading from a file
# specified in sys.argv[1]
if len(sys.argv) > 1:
  reader = open(sys.argv[1])<br>
# If no argument, read from stdin
else:
  reader = sys.stdin<br>
x = int(reader.readline())
print(x)</mark>
</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  <mark># If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)</mark>
</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)
</code></pre>
</section><br><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)<br>
<mark>except Exception as e:</mark><br>
</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)<br>
except <mark>Exception</mark> as e:<br>
</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)<br>
except Exception <mark>as</mark> e:<br>
</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)<br>
except Exception as e:<br>
</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)<br>
except Exception as e:
  <mark>print("Error!")</mark>
</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)<br>
except Exception as e:
  print("Error!")
</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = <mark>open(sys.argv[1])</mark><br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)<br>
except Exception as e:
  print("Error!")
</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)<br>
except <mark>Exception</mark> as e:
  print("Error!")
</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)<br>
except <mark>FileNotFoundError</mark> as e:
  print("Error!")
</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)<br>
except FileNotFoundError as e:
  print(<mark>"Error!"</mark>)
</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)<br>
except FileNotFoundError as e:
  print(<mark>"Error: File Not Found!"</mark>)
</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)<br>
except FileNotFoundError as e:
  print("Error: File Not Found!")
</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = <mark>int(reader.readline())</mark>
  print(x)<br>
except FileNotFoundError as e:
  print("Error: File Not Found!")
</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)<br>
except FileNotFoundError as e:
  print("Error: File Not Found!")
<mark>except ValueError as e:
  print("Error: Input Does Not Match Expected Format!")</mark>
</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)<br>
except FileNotFoundError as e:
  print("Error: File Not Found!")
except ValueError as e:
  print("Error: Input Does Not Match Expected Format!")
</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(<mark>reader.readline()</mark>)
  print(x)<br>
except FileNotFoundError as e:
  print("Error: File Not Found!")
except ValueError as e:
  print("Error: Input Does Not Match Expected Format!")
</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)<br>
except FileNotFoundError as e:
  print("Error: File Not Found!")
except ValueError as e:
  print("Error: Input Does Not Match Expected Format!")
<mark>except OSError as e:
  print("Error: OS Exception!")
</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)<br>
except FileNotFoundError as e:
  print("Error: File Not Found!")
except ValueError as e:
  print("Error: Input Does Not Match Expected Format!")
except OSError as e:
  print("Error: OS Exception!")
</code></pre>
</section><br><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)<br>
<mark>except OSError as e:
  print("Error: OS Exception!")
except FileNotFoundError as e:
  print("Error: File Not Found!")
except ValueError as e:
  print("Error: Input Does Not Match Expected Format!")</mark>
</code></pre>
</section><br><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)<br>
<mark style="background-color: red">except OSError as e:
  print("Error: OS Exception!")
except FileNotFoundError as e:
  print("Error: File Not Found!")
except ValueError as e:
  print("Error: Input Does Not Match Expected Format!")</mark>
</code></pre>
</section><br><br>
<section>
	<h2>Exception Hierarchy</h2>
	<img class="stretch plain" src="/images/10-except/8.7.p.3.filenotfound.png">
</section><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)<br>
<mark style="background-color: red">except OSError as e:
  print("Error: OS Exception!")
except FileNotFoundError as e:
  print("Error: File Not Found!")
except ValueError as e:
  print("Error: Input Does Not Match Expected Format!")</mark>
</code></pre>
</section><br><br><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)<br>
<mark>except FileNotFoundError as e:
  print("Error: File Not Found!")
except ValueError as e:
  print("Error: Input Does Not Match Expected Format!")
except OSError as e:
  print("Error: OS Exception!")</mark>
</code></pre>
</section><br><br>
<section>
	<pre class="stretch" style="font-size: .49em"><code class="python"># Load required modules
import sys<br>
try:
  # If an argument is present, we are reading from a file
  # specified in sys.argv[1]
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])<br>
  # If no argument, read from stdin
  else:
    reader = sys.stdin<br>
  x = int(reader.readline())
  print(x)<br>
except FileNotFoundError as e:
  print("Error: File Not Found!")
except ValueError as e:
  print("Error: Input Does Not Match Expected Format!")
except OSError as e:
  print("Error: OS Exception!")
</code></pre>
</section><br>