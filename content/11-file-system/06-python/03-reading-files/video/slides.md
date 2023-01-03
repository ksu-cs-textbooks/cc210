---
type: "reveal"
hidden: true
---<br>
<section>
	<pre class="stretch" style="font-size: .7em"><code class="python">import sys<br>
try:
  reader = open(sys.argv[1])
except FileNotFoundError as e:
  print("FileNotFoundError: {}".format(e))
  sys.exit()
except IndexError as e:
  print("IndexError: {}".format(e))
  reader = sys.stdin<br>
with reader:
  # -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- </code></pre>
</section><br>