---
type: "reveal"
hidden: true
---
<br>
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
<mark># -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- </mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p>Skeleton</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">numAssignments = int(reader.readline())
</code></pre>
  </div>
  <div style="width: 30%">
    <p>Handle Input</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">numAssignments = int(reader.readline())
<br>
<mark>if numAssignments > 0:
<br>
else:
  print("Invalid Input!")</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p>Handle Input</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">numAssignments = int(reader.readline())
<br>
if numAssignments > 0:
<br>
  <mark>scores = []
  weights = []</mark>
<br>
else:
  print("Invalid Input!")
</code></pre>
  </div>
  <div style="width: 30%">
    <p>Create Lists</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">numAssignments = int(reader.readline())
<br>
if numAssignments > 0:
<br>
  scores = []
  weights = []
<br>
  <mark>for i in range(0, numAssignments):
    scores.append(int(reader.readline()))
    weights.append(float(reader.readline()))</mark>
<br>
else:
  print("Invalid Input!")
</code></pre>
  </div>
  <div style="width: 30%">
    <p>Fill Lists</p>
  </div>
</section>
<br>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">numAssignments = int(reader.readline())
<br>
if numAssignments > 0:
<br>
  scores = []
  weights = []
<br>
  for i in range(0, numAssignments):
    scores.append(int(reader.readline()))
    weights.append(float(reader.readline()))
<br>
  <mark>sum = 0.0
  for d in weights:
    sum += d
<br>
  if sum == 1.0:
<br>
  else:
    print("Error! Weights do not add to 1.0!")</mark>
<br>
else:
  print("Invalid Input!")
</code></pre>
  </div>
  <div style="width: 30%">
    <p>Check Weights</p>
  </div>
</section>
<br>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">numAssignments = int(reader.readline())
<br>
if numAssignments > 0:
<br>
  scores = []
  weights = []
<br>
  for i in range(0, numAssignments):
    scores.append(int(reader.readline()))
    weights.append(float(reader.readline()))
<br>
  sum = 0.0
  for d in weights:
    sum += d
<br>
  if sum == 1.0:
<br>
    <mark>totalScore = 0.0
    for j in range(0, numAssignments):
      totalScore += scores[j] * weights[j]
    print(totalScore)</mark>
<br>
  else:
    print("Error! Weights do not add to 1.0!")
<br>
else:
  print("Invalid Input!")
</code></pre>
  </div>
  <div style="width: 30%">
    <p>Calculate Score</p>
  </div>
</section>
<br>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="python">numAssignments = int(reader.readline())
<br>
if numAssignments > 0:
<br>
  scores = []
  weights = []
<br>
  for i in range(0, numAssignments):
    scores.append(int(reader.readline()))
    weights.append(float(reader.readline()))
<br>
  sum = 0.0
  for d in weights:
    sum += d
<br>
  if sum == 1.0:
<br>
    totalScore = 0.0
    for j in range(0, numAssignments):
      totalScore += scores[j] * weights[j]
    print(totalScore)
<br>
  else:
    print("Error! Weights do not add to 1.0!")
<br>
else:
  print("Invalid Input!")
</code></pre>
  </div>
  <div style="width: 30%">
    <p>Done!</p>
  </div>
</section>
<br>