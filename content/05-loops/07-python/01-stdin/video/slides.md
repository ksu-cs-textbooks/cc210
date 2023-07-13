---
type: "reveal"
hidden: true
---
<br>
<section>
  <pre class="stretch" style="font-size: 0.7em;"><code class="python"># Load required modules
import sys
<br>
# If an argument is present,
# we are reading from a file
# specified in sys.argv[1]
if len(sys.argv) > 1:
  reader = open(sys.argv[1])
# If no argument, read from stdin
else:
  reader = sys.stdin
<br>
x = int(reader.readline())
print(x)</code></pre>
</section>
<section>
  <pre class="stretch" style="font-size: 0.7em;"><code class="python"># Load required modules
<mark>import sys</mark>
<br>
# If an argument is present,
# we are reading from a file
# specified in sys.argv[1]
if len(sys.argv) > 1:
  reader = open(sys.argv[1])
# If no argument, read from stdin
else:
  reader = sys.stdin
<br>
x = int(reader.readline())
print(x)</code></pre>
</section>
<section>
  <h3>Forgot Import?</h3>
  <pre><code class="no-highlight">NameError: name 'sys' is not defined</code></pre>
</section>
<section>
  <pre class="stretch" style="font-size: 0.7em;"><code class="python"># Load required modules
import sys
<br>
# If an argument is present,
# we are reading from a file
# specified in sys.argv[1]
<mark>if len(sys.argv) > 1:
  reader = open(sys.argv[1])</mark>
# If no argument, read from stdin
else:
  reader = sys.stdin
<br>
x = int(reader.readline())
print(x)</code></pre>
</section>
<section>
  <pre class="stretch" style="font-size: 0.7em;"><code class="python"># Load required modules
import sys
<br>
# If an argument is present,
# we are reading from a file
# specified in sys.argv[1]
if len(sys.argv) > 1:
  reader = open(sys.argv[1])
# If no argument, read from stdin
<mark>else:
  reader = sys.stdin</mark>
<br>
x = int(reader.readline())
print(x)</code></pre>
</section>
<section>
  <pre class="stretch" style="font-size: 0.7em;"><code class="python"># Load required modules
import sys
<br>
# If an argument is present,
# we are reading from a file
# specified in sys.argv[1]
if len(sys.argv) > 1:
  reader = open(sys.argv[1])
# If no argument, read from stdin
else:
  reader = sys.stdin
<br>
<mark>x = int(reader.readline())</mark>
print(x)</code></pre>
</section>
<section>
  <pre class="" style="font-size: 0.9em;"><code class="python">x = int(reader.readline())
y = float(reader.readline())</code></pre>
</section>
<section>
  <pre class="stretch" style="font-size: 0.7em;"><code class="python"># Load required modules
<mark>import sys</mark>
<br>
# If an argument is present,
# we are reading from a file
# specified in sys.argv[1]
<mark>if len(sys.argv) > 1:
  reader = open(sys.argv[1])</mark>
# If no argument, read from stdin
<mark>else:
  reader = sys.stdin</mark>
<br>
x = <mark>int(reader.readline())</mark>
print(x)</code></pre>
</section>
<br>