---
type: "reveal"
hidden: true
---
<br>
<section>
	<pre class="stretch" style="font-size: .61em"><code class="python">import sys
<br>
try:
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])
  else:
    reader = sys.stdin
<br>
  x = int(reader.readline())
  print(x)
<br>
except ValueError as e:
  print("ValueError: {}".format(e))
except FileNotFoundError as e:
  print("FileNotFoundError: {}".format(e))
finally:
  reader.close()
</code></pre>
</section>
<br>
<br>
<section>
	<pre class="stretch" style="font-size: .61em"><code class="python">import sys
<br>
try:
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])
  else:
    reader = sys.stdin
<br>
  <mark>x = int(reader.readline())
  print(x)</mark>
<br>
except ValueError as e:
  print("ValueError: {}".format(e))
except FileNotFoundError as e:
  print("FileNotFoundError: {}".format(e))
finally:
  reader.close()
</code></pre>
</section>
<br>
<br>
<section>
	<pre class="stretch" style="font-size: .61em"><code class="python">import sys
<br>
try:
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])
  else:
    reader = sys.stdin
<br>
  <mark>x = int(reader.readline())
  print(x)</mark>
<br>
except ValueError as e:
  print("ValueError: {}".format(e))
except FileNotFoundError as e:
  print("FileNotFoundError: {}".format(e))
<mark>finally:
  reader.close()</mark>
</code></pre>
</section>
<br>
<br>
<section>
	<pre class="stretch" style="font-size: .61em"><code class="python">import sys
<br>
try:
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])
  else:
    reader = sys.stdin
<br>
  <mark>with reader:</mark>
  x = int(reader.readline())
  print(x)
<br>
except ValueError as e:
  print("ValueError: {}".format(e))
except FileNotFoundError as e:
  print("FileNotFoundError: {}".format(e))
finally:
  reader.close()
</code></pre>
</section>
<br>
<section>
	<pre class="stretch" style="font-size: .61em"><code class="python">import sys
<br>
try:
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])
  else:
    reader = sys.stdin
<br>
  with reader:
  <mark>x = int(reader.readline())
  print(x)</mark>
<br>
except ValueError as e:
  print("ValueError: {}".format(e))
except FileNotFoundError as e:
  print("FileNotFoundError: {}".format(e))
finally:
  reader.close()
</code></pre>
</section>
<br>
<section>
	<pre class="stretch" style="font-size: .61em"><code class="python">import sys
<br>
try:
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])
  else:
    reader = sys.stdin
<br>
  with reader:
    <mark>x = int(reader.readline())
    print(x)</mark>
<br>
except ValueError as e:
  print("ValueError: {}".format(e))
except FileNotFoundError as e:
  print("FileNotFoundError: {}".format(e))
finally:
  reader.close()
</code></pre>
</section>
<br>
<br>
<br>
<section>
	<pre class="stretch" style="font-size: .61em"><code class="python">import sys
<br>
try:
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])
  else:
    reader = sys.stdin
<br>
  with reader:
    x = int(reader.readline())
    print(x)
<br>
except ValueError as e:
  print("ValueError: {}".format(e))
except FileNotFoundError as e:
  print("FileNotFoundError: {}".format(e))
<s>finally:
  reader.close()</s>
</code></pre>
</section>
<br>
<br>
<section>
	<pre class="stretch" style="font-size: .61em"><code class="python">import sys
<br>
try:
  if len(sys.argv) > 1:
    reader = open(sys.argv[1])
  else:
    reader = sys.stdin
<br>
  with reader:
    x = int(reader.readline())
    print(x)
<br>
except ValueError as e:
  print("ValueError: {}".format(e))
except FileNotFoundError as e:
  print("FileNotFoundError: {}".format(e))
</code></pre>
</section>
<br>
<section>
	<pre class="stretch" style="font-size: .61em"><code class="python">import sys
<br>
try:
<br>
  <mark>with open(sys.argv[1]) as reader:</mark>
    x = int(reader.readline())
    print(x)
<br>
except ValueError as e:
  print("ValueError: {}".format(e))
except FileNotFoundError as e:
  print("FileNotFoundError: {}".format(e))
</code></pre>
</section>
<br>