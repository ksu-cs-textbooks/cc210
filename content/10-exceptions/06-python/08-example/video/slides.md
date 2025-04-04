---
type: "reveal"
hidden: true
---
<br>
<section>
	<h2>Problem Statement</h2>
</section>
<section>
	<p style="font-size: 0.5em">Write a program to accept a list of numbers, one per line. Input is provided from a file if one is provided as the first command line argument. If a file is not provided, input should be read from the terminal.</p>
	<p style="font-size: 0.5em">The numbers can either be whole numbers or floating point numbers. The program should continue to accept input until a number equal to 0 is input. Of course, if the input in a file ends before a 0, that can be treated as the end of the input.</p>
	<p style="font-size: 0.5em">Once 0  is received or the input ends, the program should print the largest and smallest number provided as input (not including the 0 to end input). Sample outputs are shown below.</p>
	<p style="font-size: 0.5em">The program should catch and handle all common exceptions. When an exception is caught, the program should print the name of the exception, followed by the message included in the exception. It should then continue to accept input (if possible). Specifically, if it is unable to open the file provided, input should be read from the terminal.</p>
</section>
<section>
  <h2>Zoinks!</h2>
	<img class="stretch plain" src="/cc210/images/zoinks.gif">
  <p class="imagecredit">Image Credit: <a href="https://giphy.com/gifs/5hdg7p9NE7VlLWaeRK">Boomerang via Giphy</a></p>
	<p>Let's break it down into smaller parts</p>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">import sys
<br>
reader = open(sys.argv[1])
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Input is provided from a file [or] read from the terminal.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">import sys
<br>
reader = <mark>open(sys.argv[1])</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Input is provided from a file [or] read from the terminal.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">import sys
<br>
<mark>try:</mark>
  reader = open(sys.argv[1])
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Input is provided from a file [or] read from the terminal.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">import sys
<br>
<mark>try:</mark>
  reader = open(sys.argv[1])
<mark>except FileNotFoundError as e:
  print("FileNotFoundError: {}".format(e))</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Input is provided from a file [or] read from the terminal.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">import sys
<br>
try:
  reader = open(sys.argv[1])
except FileNotFoundError as e:
  print("FileNotFoundError: {}".format(e))
  <mark>reader = sys.stdin</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Input is provided from a file [or] read from the terminal.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">import sys
<br>
try:
  reader = open(<mark>sys.argv[1]</mark>)
except FileNotFoundError as e:
  print("FileNotFoundError: {}".format(e))
  reader = sys.stdin
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Input is provided from a file [or] read from the terminal.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">import sys
<br>
try:
  reader = open(<mark>sys.argv[1]</mark>)
except FileNotFoundError as e:
  print("FileNotFoundError: {}".format(e))
  reader = sys.stdin
<mark>except IndexError as e:
  print("IndexError: {}".format(e))
  reader = sys.stdin</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Input is provided from a file [or] read from the terminal.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">import sys
<br>
try:
  reader = open(sys.argv[1])
except FileNotFoundError as e:
  print("FileNotFoundError: {}".format(e))
  reader = sys.stdin
except IndexError as e:
  print("IndexError: {}".format(e))
  reader = sys.stdin
<br>
<mark>with reader:</mark>
<br>
  # more code here
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Input is provided from a file [or] read from the terminal.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">import sys
<br>
try:
  reader = open(sys.argv[1])
except FileNotFoundError as e:
  print("FileNotFoundError: {}".format(e))
  reader = sys.stdin
except IndexError as e:
  print("IndexError: {}".format(e))
  reader = sys.stdin
<br>
with reader:
<br>
  <mark># more code here<mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Input is provided from a file [or] read from the terminal.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">while True:
  string = reader.readline().strip()
  if len(string) == 0:
    raise EOFError("Unexpected End of Input!")
  input = float(string)
  if input == 0.0:
    break
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">list of numbers, one per line... whole numbers or floating point numbers... accept input until a number equal to 0 is input.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">while True:
  string = reader.readline().strip()
  if len(string) == 0:
    raise EOFError("Unexpected End of Input!")
  input = <mark>float(string)</mark>
  if input == 0.0:
    break
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">list of numbers, one per line... <mark>whole numbers or floating point numbers</mark>... accept input until a number equal to 0 is input.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">while True:
  string = reader.readline().strip()
  if len(string) == 0:
    raise EOFError("Unexpected End of Input!")
  input = float(string)
  <mark>if input == 0.0:
    break</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">list of numbers, one per line... whole numbers or floating point numbers... <mark>accept input until a number equal to 0 is input.</mark></p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">while True:
  string = reader.readline().strip()
  if len(string) == 0:
    raise EOFError("Unexpected End of Input!")
  input = <mark>float(string)</mark>
  if input == 0.0:
    break
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">list of numbers, one per line... whole numbers or floating point numbers... accept input until a number equal to 0 is input.</p>
    <p style="font-size: .7em"><mark>The program should catch and handle all common exceptions.</mark></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">while True:
  <mark>try:</mark>
    string = reader.readline().strip()
    if len(string) == 0:
      raise EOFError("Unexpected End of Input!")
    input = float(string)
    if input == 0.0:
      break
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">list of numbers, one per line... whole numbers or floating point numbers... accept input until a number equal to 0 is input.</p>
    <p style="font-size: .7em"><mark>The program should catch and handle all common exceptions.</mark></p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">while True:
  try:
    string = reader.readline().strip()
    if len(string) == 0:
      raise EOFError("Unexpected End of Input!")
    input = <mark>float(string)</mark>
    if input == 0.0:
      break
  <mark>except ValueError as e:
    print("ValueError: {}".format(e))</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">list of numbers, one per line... whole numbers or floating point numbers... accept input until a number equal to 0 is input.</p>
    <p style="font-size: .7em"><mark>The program should catch and handle all common exceptions.</mark></p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">while True:
  try:
    string = reader.readline().strip()
    if len(string) == 0:
      <mark>raise EOFError("Unexpected End of Input!")</mark>
    input = float(string)
    if input == 0.0:
      break
  except ValueError as e:
    print("ValueError: {}".format(e))
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">list of numbers, one per line... whole numbers or floating point numbers... accept input until a number equal to 0 is input.</p>
    <p style="font-size: .7em"><mark>The program should catch and handle all common exceptions.</mark></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">while True:
  try:
    string = reader.readline().strip()
    if len(string) == 0:
      <mark>raise EOFError("Unexpected End of Input!")</mark>
    input = float(string)
    if input == 0.0:
      break
  except ValueError as e:
    print("ValueError: {}".format(e))
  <mark>except EOFError as e:
    print("EOFError: {}".format(e))
    break # out of input, so we should stop there</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">list of numbers, one per line... whole numbers or floating point numbers... accept input until a number equal to 0 is input.</p>
    <p style="font-size: .7em"><mark>The program should catch and handle all common exceptions.</mark></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">while True:
  try:
    string = reader.readline().strip()
    if len(string) == 0:
      raise EOFError("Unexpected End of Input!")
    input = float(string)
    if input == 0.0:
      break
  except ValueError as e:
    print("ValueError: {}".format(e))
  except EOFError as e:
    print("EOFError: {}".format(e))
    break # out of input, so we should stop there
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Once 0 is received or the input ends, the program should print the largest and smallest number provided as input (not including the 0 to end input).</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python"><mark>maximum = 0.0
minimum = 0.0</mark>
<br>
while True:
  try:
    string = reader.readline().strip()
    if len(string) == 0:
      raise EOFError("Unexpected End of Input!")
    input = float(string)
    if input == 0.0:
      break
  except ValueError as e:
    print("ValueError: {}".format(e))
  except EOFError as e:
    print("EOFError: {}".format(e))
    break # out of input, so we should stop there
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Once 0 is received or the input ends, the program should print the largest and smallest number provided as input (not including the 0 to end input).</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python"><mark>maximum = 0.0
minimum = 0.0</mark>
<br>
while True:
  try:
    string = reader.readline().strip()
    if len(string) == 0:
      raise EOFError("Unexpected End of Input!")
    input = float(string)
    if input == 0.0:
      break
<br>
    <mark>if input &lt; minimum or minimum == 0.0:
      minimum = input
    if input > maximum or maximum == 0.0:
      maximum = input</mark>
<br>
  except ValueError as e:
    print("ValueError: {}".format(e))
  except EOFError as e:
    print("EOFError: {}".format(e))
    break # out of input, so we should stop there
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Once 0 is received or the input ends, the program should print the largest and smallest number provided as input (not including the 0 to end input).</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python"><mark>maximum = 0.0
minimum = 0.0</mark>
<br>
while True:
  try:
    string = reader.readline().strip()
    if len(string) == 0:
      raise EOFError("Unexpected End of Input!")
    input = float(string)
    if input == 0.0:
      break
<br>
    <mark>if input &lt; minimum or minimum == 0.0:
      minimum = input
    if input > maximum or maximum == 0.0:
      maximum = input</mark>
<br>
  except ValueError as e:
    print("ValueError: {}".format(e))
  except EOFError as e:
    print("EOFError: {}".format(e))
    break # out of input, so we should stop there
<br>
<mark>print("Maximum: {}".format(maximum))
print("Minimum: {}".format(minimum))</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Once 0 is received or the input ends, the program should print the largest and smallest number provided as input (not including the 0 to end input).</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">maximum = 0.0
minimum = 0.0
<br>
while True:
  try:
    string = reader.readline().strip()
    if len(string) == 0:
      raise EOFError("Unexpected End of Input!")
    input = float(string)
    if input == 0.0:
      break
<br>
    if input &lt; minimum or minimum == 0.0:
      minimum = input
    if input > maximum or maximum == 0.0:
      maximum = input
<br>
  except ValueError as e:
    print("ValueError: {}".format(e))
  except EOFError as e:
    print("EOFError: {}".format(e))
    break # out of input, so we should stop there
<br>
print("Maximum: {}".format(maximum))
print("Minimum: {}".format(minimum))
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Once 0 is received or the input ends, the program should print the largest and smallest number provided as input (not including the 0 to end input).</p>
  </div>
</section>
<br>