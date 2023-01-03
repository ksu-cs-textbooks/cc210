---
type: "reveal"
hidden: true
---<br>
<section>
	<pre class="stretch" style="font-size: .5em"><code class="python">import sys<br>
try:
  with open(sys.argv[1], "w") as writer:<br>
except Exception as e:
  # unknown exception
  print("Exception: {}".format(e))
  sys.exit()</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .5em"><code class="python">import sys<br>
try:
  with open(sys.argv[1]<mark>, "w"</mark>) as writer:<br>
except Exception as e:
  # unknown exception
  print("Exception: {}".format(e))
  sys.exit()</code></pre>
</section><br><br>
<section>
	<pre class="stretch" style="font-size: .5em"><code class="python">import sys<br>
try:
  with open(sys.argv[1], "w") as writer:
    <mark>writer.write("Hello World")
    writer.write("\n")</mark><br>
except Exception as e:
  # unknown exception
  print("Exception: {}".format(e))
  sys.exit()</code></pre>
</section><br><br><br>
<section>
	<pre class="stretch" style="font-size: .5em"><code class="python">import sys<br>
try:
  with open(<mark>sys.argv[1]</mark>, "w") as writer:
    writer.write("Hello World")
    writer.write("\n")<br>
<mark>except IndexError as e:
  # no arguments provided
  print("IndexError: {}".format(e))
  sys.exit()</mark>
except Exception as e:
  # unknown exception
  print("Exception: {}".format(e))
  sys.exit()</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .5em"><code class="python">import sys<br>
try:
  with open(sys.argv[1], "w") as writer:
    <mark>writer.write("Hello World")</mark>
    writer.write("\n")<br>
except IndexError as e:
  # no arguments provided
  print("IndexError: {}".format(e))
  sys.exit()
<mark>except IOError as e:
  # unable to write to the file
  print("IOError: {}".format(e))
  sys.exit()</mark>
except Exception as e:
  # unknown exception
  print("Exception: {}".format(e))
  sys.exit()</code></pre>
</section><br><br><br>
<section>
	<pre class="stretch" style="font-size: .5em"><code class="python">import sys<br>
try:
  with open(sys.argv[1], "w") as writer:
    writer.write("Hello World")
    writer.write("\n")<br>
except IndexError as e:
  # no arguments provided
  print("IndexError: {}".format(e))
  sys.exit()
except IOError as e:
  # unable to write to the file
  print("IOError: {}".format(e))
  sys.exit()
except Exception as e:
  # unknown exception
  print("Exception: {}".format(e))
  sys.exit()</code></pre>
</section><br>