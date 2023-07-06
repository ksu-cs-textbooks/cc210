---
type: "reveal"
hidden: true
---

<section>
  <h3>Problem Statement</h3>
  <blockquote class="stretch" style="text-align: left">Write a program that accepts a positive integer that represents a year, and prints whether that year is a leap year or not. If the year is a leap year, it should print output similar to "2000 is a Leap Year". If not, it should print output similar to "2001 is not a Leap Year".</blockquote>
</section>
<section>
  <h3>Leap Years</h3>
  <blockquote class="stretch" style="text-align: left">Every year that is exactly divisible by four is a leap year, except for years that are exactly divisible by 100, but these centurial years are leap years if they are exactly divisible by 400. For example, the years 1700, 1800, and 1900 are not leap years, but the year 2000 is. - USNO</blockquote>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that accepts a positive integer that represents a year...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python"># Load required modules
<mark>import sys</mark>
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that accepts a positive integer that represents a year...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python"># Load required modules
import sys
<br>
# If an argument is present
# we are reading from a file
# specified in sys.argv[1]
<mark>if len(sys.argv) > 1:</mark>
  <mark>reader = open(sys.argv[1])</mark>
# If no argument, read from stdin
<mark>else:</mark>
  <mark>reader = sys.stdin</mark>
<br>
# -=-=-=-=- MORE CODE GOES HERE -=-=-=-=-
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that accepts a positive integer that represents a year...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python"># Load required modules
import sys
<br>
# If an argument is present
# we are reading from a file
# specified in sys.argv[1]
if len(sys.argv) > 1:
  reader = open(sys.argv[1])
# If no argument, read from stdin
else:
  reader = sys.stdin
<br>
<mark># -=-=-=-=- MORE CODE GOES HERE -=-=-=-=-</mark>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that accepts a positive integer that represents a year...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that accepts a positive <mark>integer that represents a year</mark>...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python"><mark>year = int(reader.readline())</mark>
<br>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that accepts a positive <mark>integer that represents a year</mark>...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">year = int(reader.readline())
<br>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that accepts a <mark>positive integer</mark> that represents a year...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">year = int(reader.readline())
<mark>if year <= 0:
  print("Error")
else:
  # more code here
</mark>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that accepts a <mark>positive integer</mark> that represents a year...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">year = int(reader.readline())
if year <= 0:
  print("Error")
else:
  # more code here
<br>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Every year that is exactly divisible by four is a leap year, except...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">year = int(reader.readline())
if year <= 0:
  print("Error")
else:
  # more code here
<br>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Every year that is exactly <mark>divisible by four is a leap year</mark>, except...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">year = int(reader.readline())
if year <= 0:
  print("Error")
else:
  <mark>if year % 4 == 0:</mark>
    # divisible by 4
  <mark>else:</mark>
    # not divisible by 4
    <mark>print("no")</mark>
<br>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Every year that is exactly <mark>divisible by four is a leap year</mark>, except...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">year = int(reader.readline())
if year <= 0:
  print("Error")
else:
  if year % 4 == 0:
    # divisible by 4
  else:
    # not divisible by 4
    print("no")
<br>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...except for years that are exactly divisible by 100, but...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">year = int(reader.readline())
if year <= 0:
  print("Error")
else:
  if year % 4 == 0:
    # divisible by 4
  else:
    # not divisible by 4
    print("no")
<br>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...except for years that are <mark>exactly divisible by 100</mark>, but...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">year = int(reader.readline())
if year <= 0:
  print("Error")
else:
  if year % 4 == 0:
    # divisible by 4
    <mark>if year % 100 == 0:</mark>
      # divisible by 4 and 100
      <mark>print("no")</mark>
    <mark>else:</mark>
      # divisible by 4 but not 100
      <mark>print("yes")</mark>
  else:
    # not divisible by 4
    print("no")
<br>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...except for years that are <mark>exactly divisible by 100</mark>, but...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">year = int(reader.readline())
if year <= 0:
  print("Error")
else:
  if year % 4 == 0:
    # divisible by 4
    if year % 100 == 0:
      # divisible by 4 and 100
      print("no")
    else:
      # divisible by 4 but not 100
      print("yes")
  else:
    # not divisible by 4
    print("no")
<br>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...but these centurial years are leap years if they are exactly divisible by 400.</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">year = int(reader.readline())
if year <= 0:
  print("Error")
else:
  if year % 4 == 0:
    # divisible by 4
    if year % 100 == 0:
      # divisible by 4 and 100
      print("no")
    else:
      # divisible by 4 but not 100
      print("yes")
  else:
    # not divisible by 4
    print("no")
<br>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...but these centurial years are leap years if they are <mark>exactly divisible by 400.</mark></p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">year = int(reader.readline())
if year <= 0:
  print("Error")
else:
  if year % 4 == 0:
    # divisible by 4
    if year % 100 == 0:
      # divisible by 4 and 100
      <mark>print("no")</mark>
    else:
      # divisible by 4 but not 100
      print("yes")
  else:
    # not divisible by 4
    print("no")
<br>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...but these centurial years are leap years if they are <mark>exactly divisible by 400.</mark></p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">year = int(reader.readline())
if year <= 0:
  print("Error")
else:
  if year % 4 == 0:
    # divisible by 4
    if year % 100 == 0:
      # divisible by 4 and 100
      <mark>if year % 400 == 0:</mark>
        # divisible by 4 and 100 and 400
        <mark>print("yes")</mark>
      <mark>else:</mark>
        # divisible by 4 and 100 not 400
        <mark>print("no")</mark>
    else:
      # divisible by 4 but not 100
      print("yes")
  else:
    # not divisible by 4
    print("no")
<br>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...but these centurial years are leap years if they are <mark>exactly divisible by 400.</mark></p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">year = int(reader.readline())
if year <= 0:
  print("Error")
else:
  if year % 4 == 0:
    # divisible by 4
    if year % 100 == 0:
      # divisible by 4 and 100
      if year % 400 == 0:
        # divisible by 4 and 100 and 400
        print("yes")
      else:
        # divisible by 4 and 100 not 400
        print("no")
    else:
      # divisible by 4 but not 100
      print("yes")
  else:
    # not divisible by 4
    print("no")
<br>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...positive integer that represents a year...<br>Every year that is exactly divisible by four is a leap year, except for years that are exactly divisible by 100, but these centurial years are leap years if they are exactly divisible by 400.</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python"><mark>year = int(reader.readline())
if year <= 0:
  print("Error")
else:</mark>
  if year % 4 == 0:
    # divisible by 4
    if year % 100 == 0:
      # divisible by 4 and 100
      if year % 400 == 0:
        # divisible by 4 and 100 and 400
        print("yes")
      else:
        # divisible by 4 and 100 not 400
        print("no")
    else:
      # divisible by 4 but not 100
      print("yes")
  else:
    # not divisible by 4
    print("no")
<br>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...<mark>positive integer that represents a year</mark>...<br>Every year that is exactly divisible by four is a leap year, except for years that are exactly divisible by 100, but these centurial years are leap years if they are exactly divisible by 400.</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">year = int(reader.readline())
if year <= 0:
  print("Error")
else:
  <mark>if year % 4 == 0:</mark>
    # divisible by 4
    if year % 100 == 0:
      # divisible by 4 and 100
      if year % 400 == 0:
        # divisible by 4 and 100 and 400
        print("yes")
      else:
        # divisible by 4 and 100 not 400
        print("no")
    else:
      # divisible by 4 but not 100
      print("yes")
  <mark>else:</mark>
    # not divisible by 4
    <mark>print("no")</mark>
<br>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...positive integer that represents a year...<br>Every year that is exactly <mark>divisible by four is a leap year</mark>, except for years that are exactly divisible by 100, but these centurial years are leap years if they are exactly divisible by 400.</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">year = int(reader.readline())
if year <= 0:
  print("Error")
else:
  if year % 4 == 0:
    # divisible by 4
    <mark>if year % 100 == 0:</mark>
      # divisible by 4 and 100
      if year % 400 == 0:
        # divisible by 4 and 100 and 400
        print("yes")
      else:
        # divisible by 4 and 100 not 400
        print("no")
    <mark>else:</mark>
      # divisible by 4 but not 100
      <mark>print("yes")</mark>
  else:
    # not divisible by 4
    print("no")
<br>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...positive integer that represents a year...<br>Every year that is exactly divisible by four is a leap year, <mark>except for years that are exactly divisible by 100</mark>, but these centurial years are leap years if they are exactly divisible by 400</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">year = int(reader.readline())
if year <= 0:
  print("Error")
else:
  if year % 4 == 0:
    # divisible by 4
    if year % 100 == 0:
      # divisible by 4 and 100
      <mark>if year % 400 == 0:</mark>
        # divisible by 4 and 100 and 400
        <mark>print("yes")</mark>
      <mark>else:</mark>
        # divisible by 4 and 100 not 400
        <mark>print("no")</mark>
    else:
      # divisible by 4 but not 100
      print("yes")
  else:
    # not divisible by 4
    print("no")
<br>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...positive integer that represents a year...<br>Every year that is exactly divisible by four is a leap year, except for years that are exactly divisible by 100, <mark>but these centurial years are leap years if they are exactly divisible by 400.</mark></p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">year = int(reader.readline())
if year <= 0:
  print("Error")
else:
  if year % 4 == 0:
    # divisible by 4
    if year % 100 == 0:
      # divisible by 4 and 100
      if year % 400 == 0:
        # divisible by 4 and 100 and 400
        print("yes")
      else:
        # divisible by 4 and 100 not 400
        print("no")
    else:
      # divisible by 4 but not 100
      print("yes")
  else:
    # not divisible by 4
    print("no")
<br>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...positive integer that represents a year...<br>Every year that is exactly divisible by four is a leap year, except for years that are exactly divisible by 100, but these centurial years are leap years if they are exactly divisible by 400.</p>
  </div>
</section>
