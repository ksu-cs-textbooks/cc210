---
type: "reveal"
hidden: true
---
<br>
<section>
	<h2>Problem Statement</h2>
</section>
<section>
	<p style="font-size: 0.5em">Write a program that will calculate weighted grades for students in a college course. The input will be given in a comma-delimited format. The first line will contain a number of weights as floating-point numbers, separated by commas. The first entry should be ignored.</p>
	<p style="font-size: 0.5em">Each subsequent line of input will contain information for a student. The first entry on that line will contain that student’s name. The rest of the line will contain that student’s scores on each assignment as an integer value, separated by commas. Input will be terminated by the end of the input file, or by a blank line when input is provided via the terminal.</p>
	<p style="font-size: 0.5em">It is guaranteed that at least two lines of input will be provided, the first containing the weights and at least one additional line containing data for a student. In addition, it is guaranteed that each line of input will contain the same number of parts.</p>
	<p style="font-size: 0.5em">The program should output the student’s name, followed by a colon, and a space, and then the student’s score. The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</p>
</section>
<section>
	<h2>Yikes!</h2>
	<p>Let's break it down into smaller parts</p>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python"># Load required modules
import sys
<br>
# If an argument is present, we are reading from a file
# specified in sys.argv[1]
if len(sys.argv) > 1:
  reader = open(sys.argv[1])
<br>
# If no argument, read from stdin
else:
  reader = sys.stdin
<br>
# -=-=-=-=- MORE CODE GOES HERE -=-=-=-=-
</code></pre>
  </div>
  <div style="width: 30%">
    <p>Skeleton</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line will contain a number of weights as floating-point numbers, separated by commas. The first entry should be ignored.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em"><mark>The first line</mark> will contain a number of weights as floating-point numbers, separated by commas. The first entry should be ignored.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python"><mark>weightLine = reader.readline()</mark>
<br>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em"><mark>The first line</mark> will contain a number of weights as floating-point numbers, separated by commas. The first entry should be ignored.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">weightLine = reader.readline()
<br>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line <mark>will contain a number of weights</mark> as floating-point numbers, <mark>separated by commas</mark>. The first entry should be ignored.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">weightLine = reader.readline()
<mark>weightParts = weightLine.split(",")</mark>
<br>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line <mark>will contain a number of weights</mark> as floating-point numbers, <mark>separated by commas</mark>. The first entry should be ignored.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">weightLine = reader.readline()
weightParts = weightLine.split(",")
<br>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line will contain <mark>a number of weights as floating-point numbers</mark>, separated by commas. The first entry should be ignored.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">weightLine = reader.readline()
weightParts = weightLine.split(",")
<br>
<mark>weights = []</mark>
<br>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line will contain <mark>a number of weights as floating-point numbers</mark>, separated by commas. The first entry should be ignored.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">weightLine = reader.readline()
weightParts = weightLine.split(",")
<br>
weights = []
<br>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line will contain <mark>a number of weights</mark> as floating-point numbers, separated by commas. The first entry should be ignored.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">weightLine = reader.readline()
weightParts = weightLine.split(",")
<br>
weights = []
<br>
<mark>for i in range(0, len(weightParts)):
  weights.append(weightParts[i])
</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line will contain <mark>a number of weights</mark> as floating-point numbers, separated by commas. The first entry should be ignored.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">weightLine = reader.readline()
weightParts = weightLine.split(",")
<br>
weights = []
<br>
for i in range(0, len(weightParts)):
  weights.append(<mark>weightParts[i]</mark>)
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line will contain a number of weights as <mark>floating-point numbers</mark>, separated by commas. The first entry should be ignored.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">weightLine = reader.readline()
weightParts = weightLine.split(",")
<br>
weights = []
<br>
for i in range(0, len(weightParts)):
  weights.append(<mark>float(weightParts[i])</mark>)
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line will contain a number of weights as <mark>floating-point numbers</mark>, separated by commas. The first entry should be ignored.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">weightLine = reader.readline()
weightParts = weightLine.split(",")
<br>
weights = []
<br>
for i in range(0, len(weightParts)):
  weights.append(float(weightParts[i]))
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line will contain a number of weights as floating-point numbers, separated by commas. <mark>The first entry should be ignored.</mark></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">weightLine = reader.readline()
weightParts = weightLine.split(",")
<br>
weights = []
<br>
for i in range(<mark>0</mark>, len(weightParts)):
  weights.append(float(weightParts[i]))
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line will contain a number of weights as floating-point numbers, separated by commas. <mark>The first entry should be ignored.</mark></p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">weightLine = reader.readline()
weightParts = weightLine.split(",")
<br>
weights = []
<mark>weights.append(0.0)</mark>
<br>
for i in range(<mark>1</mark>, len(weightParts)):
  weights.append(float(weightParts[i]))
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line will contain a number of weights as floating-point numbers, separated by commas. <mark>The first entry should be ignored.</mark></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">weightLine = reader.readline()
weightParts = weightLine.split(",")
<br>
weights = []
weights.append(0.0)
<br>
for i in range(1, len(weightParts)):
  weights.append(float(weightParts[i]))
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line will contain a number of weights as floating-point numbers, separated by commas. The first entry should be ignored.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">
<br>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">Each subsequent line of input will contain information for a student. ... Input will be terminated by the end of the input file, or by a blank line when input is provided via the terminal.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">
<br>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em"><mark>Each subsequent line of input</mark> will contain information for a student. ... Input will be terminated by the end of the input file, or by a blank line when input is provided via the terminal.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python"><mark>for line in reader:
<br>
</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em"><mark>Each subsequent line of input</mark> will contain information for a student. ... Input will be terminated by the end of the input file, or by a blank line when input is provided via the terminal.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
<br>
<br>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">Each subsequent <mark>line of input will contain information for a student</mark>. ... Input will be terminated by the end of the input file, or by a blank line when input is provided via the terminal.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for <mark>line</mark> in reader:
<br>
  <mark># parse the input</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">Each subsequent <mark>line of input will contain information for a student</mark>. ... Input will be terminated by the end of the input file, or by a blank line when input is provided via the terminal.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
<br>
  # parse the input
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">Each subsequent line of input will contain information for a student. ... Input will be terminated by the end of the input file, <mark>or by a blank line when input is provided via the terminal.</mark></p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  <mark>if not line or len(line.strip()) == 0:
    break</mark>
<br>
  # parse the input
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">Each subsequent line of input will contain information for a student. ... Input will be terminated by the end of the input file, <mark>or by a blank line when input is provided via the terminal.</mark></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  # parse the input
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">Each subsequent line of input will contain information for a student. ... Input will be terminated by the end of the input file, or by a blank line when input is provided via the terminal.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  # parse the input
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first entry on that line will contain that student’s name. The rest of the line will contain that student’s scores on each assignment as an integer value, separated by commas.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  # parse the input
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first entry on that line will contain that student’s name. The rest of the line will contain that student’s scores on each assignment as an integer value, <mark>separated by commas.</mark></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  <mark>parts = line.split(",")</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first entry on that line will contain that student’s name. The rest of the line will contain that student’s scores on each assignment as an integer value, <mark>separated by commas.</mark></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  parts = line.split(",")
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first entry on that line will contain that student’s name. <mark>The rest of the line will contain that student’s scores on each assignment as an integer value</mark>, separated by commas.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  parts = line.split(",")
<br>
  <mark>for j in range(1, len(parts)):
    parts[j]</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first entry on that line will contain that student’s name. <mark>The rest of the line will contain that student’s scores on each assignment as an integer value</mark>, separated by commas.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  parts = line.split(",")
<br>
  for j in range(1, len(parts)):
    parts[j]
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first entry on that line will contain that student’s name. The rest of the line will contain that student’s scores on each assignment as an <mark>integer value</mark>, separated by commas.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  parts = line.split(",")
<br>
  for j in range(1, len(parts)):
    <mark>int(parts[j])</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first entry on that line will contain that student’s name. The rest of the line will contain that student’s scores on each assignment as an <mark>integer value</mark>, separated by commas.</p>
  </div>
</section>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  parts = line.split(",")
<br>
  for j in range(1, len(parts)):
    int(parts[j])
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">Write a program that will calculate weighted grades for students in a college course.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  parts = line.split(",")
<br>
  for j in range(1, len(parts)):
    int(parts[j])
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">Write a program that will calculate <mark>weighted grades</mark> for students in a college course.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  parts = line.split(",")
<br>
  for j in range(1, len(parts)):
    int(parts[j])
</code></pre>
  </div>
	<div style="width: 30%">
    <p style="font-size: .5em">Write a program that will calculate <mark>weighted grades</mark> for students in a college course.<p>
		<p style="font-size: .5em; font-family: monospace">Total =<br>Sum(Score[i] * Weight[i])</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  parts = line.split(",")
<br>
  for j in range(1, len(parts)):
    <mark>weights[j] * int(parts[j])</mark>
</code></pre>
  </div>
	<div style="width: 30%">
    <p style="font-size: .5em">Write a program that will calculate <mark>weighted grades</mark> for students in a college course.<p>
		<p style="font-size: .5em; font-family: monospace">Total =<br>Sum(Score[i] * Weight[i])</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  parts = line.split(",")
<br>
  <mark>totalScore = 0.0</mark>
  for j in range(1, len(parts)):
    <mark>totalScore += </mark>weights[j] * int(parts[j])
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">Write a program that will calculate <mark>weighted grades</mark> for students in a college course.<p>
		<p style="font-size: .5em; font-family: monospace">Total =<br>Sum(Score[i] * Weight[i])</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  parts = line.split(",")
<br>
  totalScore = 0.0
  for j in range(1, len(parts)):
    totalScore += weights[j] * int(parts[j])
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The program should output the student’s name, followed by a colon, and a space, and then the student’s score. The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  parts = line.split(",")
<br>
  totalScore = 0.0
  for j in range(1, len(parts)):
    totalScore += weights[j] * int(parts[j])
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em"><mark>The program should output</mark> the student’s name, followed by a colon, and a space, and then the student’s score. The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  parts = line.split(",")
<br>
  totalScore = 0.0
  for j in range(1, len(parts)):
    totalScore += weights[j] * int(parts[j])
<br>
  <mark>print()</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em"><mark>The program should output</mark> the student’s name, followed by a colon, and a space, and then the student’s score. The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</p>
  </div>
</section>
<br>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  parts = line.split(",")
<br>
  totalScore = 0.0
  for j in range(1, len(parts)):
    totalScore += weights[j] * int(parts[j])
<br>
  print()
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The program should output the student’s name, followed by a colon, and a space, and then the student’s score. The score should be <mark>formatted to be exactly 5 characters wide</mark>, with exactly two characters after the decimal point.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  parts = line.split(",")
<br>
  totalScore = 0.0
  for j in range(1, len(parts)):
    totalScore += weights[j] * int(parts[j])
<br>
  print(<mark>"".format()</mark>)
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The program should output the student’s name, followed by a colon, and a space, and then the student’s score. The score should be <mark>formatted to be exactly 5 characters wide</mark>, with exactly two characters after the decimal point.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  parts = line.split(",")
<br>
  totalScore = 0.0
  for j in range(1, len(parts)):
    totalScore += weights[j] * int(parts[j])
<br>
  print("".format())
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The program should output the <mark>student’s name, followed by a colon, and a space,</mark> and then the student’s score. The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  parts = line.split(",")
<br>
  totalScore = 0.0
  for j in range(1, len(parts)):
    totalScore += weights[j] * int(parts[j])
<br>
  print("<mark>{}: </mark>".format(<mark>parts[0]</mark>))
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The program should output the <mark>student’s name, followed by a colon, and a space,</mark> and then the student’s score. The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  parts = line.split(",")
<br>
  totalScore = 0.0
  for j in range(1, len(parts)):
    totalScore += weights[j] * int(parts[j])
<br>
  print("{}: ".format(parts[0]))
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The program should output the student’s name, followed by a colon, and a space, <mark>and then the student’s score.</mark> The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  parts = line.split(",")
<br>
  totalScore = 0.0
  for j in range(1, len(parts)):
    totalScore += weights[j] * int(parts[j])
<br>
  print("{}: <mark>{}</mark>".format(parts[0], <mark>totalScore</mark>))
<br>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The program should output the student’s name, followed by a colon, and a space, <mark>and then the student’s score.</mark> The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  parts = line.split(",")
<br>
  totalScore = 0.0
  for j in range(1, len(parts)):
    totalScore += weights[j] * int(parts[j])
<br>
  print("{}: {}".format(parts[0], totalScore))
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The program should output the student’s name, followed by a colon, and a space, and then the student’s score. <mark>The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</mark></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  parts = line.split(",")
<br>
  totalScore = 0.0
  for j in range(1, len(parts)):
    totalScore += weights[j] * int(parts[j])
<br>
  print("{}: <mark>{:5.2f}</mark>".format(parts[0], totalScore))
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The program should output the student’s name, followed by a colon, and a space, and then the student’s score. <mark>The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</mark></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  parts = line.split(",")
<br>
  totalScore = 0.0
  for j in range(1, len(parts)):
    totalScore += weights[j] * int(parts[j])
<br>
  print("{}: {:5.2f}".format(parts[0], totalScore))
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The program should output the student’s name, followed by a colon, and a space, and then the student’s score. The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</p>
  </div>
</section>
<br>
<section>
    <pre class="stretch" style="font-size: .54em"><code class="python">weightLine = reader.readline()
weightParts = weightLine.split(",")
<br>
weights = []
weights.append(0.0)
<br>
for i in range(1, len(weightParts)):
  weights.append(float(weightParts[i]))
<br>
for line in reader:
  if not line or len(line.strip()) == 0:
    break
<br>
  parts = line.split(",")
<br>
  totalScore = 0.0
  for j in range(1, len(parts)):
    totalScore += weights[j] * int(parts[j])
<br>
  print("{}: {:5.2f}".format(parts[0], totalScore))
</code></pre>
</section>
<br>