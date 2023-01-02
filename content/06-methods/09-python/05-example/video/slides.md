---
type: "reveal"
hidden: true
---
<br>
<section>
	<h2>Problem Statement</h2>
</section>
<section>
	<p style="font-size: 0.5em">Write a program that calculates the minimum, maximum, sum, and average of a list of numbers. The numbers should be read from a file provided as a command-line argument. The file should contain a single number on each line.</p>
	<p style="font-size: 0.5em">The program should handle all reasonable exceptions. If the input file is not provided or cannot be read, it should print "Error opening file." If the input file contains a value that cannot be converted to a number, it should print "Error parsing input." Any other errors should cause the program to print "Unknown error."</p>
	<p style="font-size: 0.5em">When printing, all decimal values should be rounded to the nearest tenth (one decimal place). The final output of the program should look similar to the following:</p>
	<pre style="font-size: 0.5em">Minimum: 24.0
Maximum: 183.0
Sum: 1236.4
Average: 102.3</pre>
</section>
<section>
  <h2>Uhhhhh...</h2>
	<img class="stretch plain" src="https://media.giphy.com/media/3og0INyCmHlNylks9O/source.gif">
  <p class="imagecredit">Image Credit: <a href="https://giphy.com/gifs/reactionseditor-classic-facepalm-3og0INyCmHlNylks9O">Giphy</a></p>
	<p>Let's break it down into smaller parts</p>
</section>
<br>
<br>
<section>
  <h2>Use Functions!</h2>
	<img class="stretch plain" src="https://media.giphy.com/media/Cv2CCge3AtbCE/source.gif">
  <p class="imagecredit">Image Credit: <a href="https://giphy.com/gifs/star-trek-Cv2CCge3AtbCE">Giphy</a></p>
	<p>Let's break it down into <b style="color:#512888">functions</b></p>
</section>
<br>
<section>
  <h4>Read Input File</h4>
    <pre class="stretch" style="font-size: .55em"><code class="python">def read_input(filename):
  try:
    with(open(filename) as reader):
<br>
      # read input file here
<br>
  except FileNotFoundError as e:
    print("Error opening file.")
    return []
  except IOError as e:
    print("Unknown error.")
    return []
  except ValueError as e:
    print("Error parsing input.")
    return []</code></pre>
</section>
<br>
<br>
<section>
  <h4>Read Input File</h4>
    <pre class="stretch" style="font-size: .55em"><code class="python">def read_input(filename):
  try:
    with(open(filename) as reader):
<br>
      # read input file here
<br>
  except FileNotFoundError as e:
    print("Error opening file.")
    <mark>return []</mark>
  except IOError as e:
    print("Unknown error.")
    <mark>return []</mark>
  except ValueError as e:
    print("Error parsing input.")
    <mark>return []</mark></code></pre>
</section>
<br>
<br>
<section>
  <h4>Read Input File</h4>
    <pre class="stretch" style="font-size: .55em"><code class="python">def read_input(filename):
  try:
    with(open(filename) as reader):
<br>
      <mark># read input file here</mark>
<br>
  except FileNotFoundError as e:
    print("Error opening file.")
    return []
  except IOError as e:
    print("Unknown error.")
    return []
  except ValueError as e:
    print("Error parsing input.")
    return []</code></pre>
</section>
<br>
<br>
<br>
<section>
  <h4>Read Input File</h4>
    <pre class="stretch" style="font-size: .55em"><code class="python">def read_input(filename):
  try:
    with(open(filename) as reader):
<br>
      list = []
      for line in reader:
        list.append(float(line))
      return list
<br>
  except FileNotFoundError as e:
    print("Error opening file.")
    return []
  except IOError as e:
    print("Unknown error.")
    return []
  except ValueError as e:
    print("Error parsing input.")
    return []</code></pre>
</section>
<br>
<br>
<br>
<section>
  <h4>Max & Min</h4>
    <pre class="stretch" style="font-size: .55em"><code class="python">def min(numbers):
  minimum = 0
  if len(numbers) > 0:
    minimum = numbers[0]
  for n in numbers:
    if n < minimum:
      minimum = n
  return minimum
<br>
def max(numbers):
  maximum = 0
  if len(numbers) > 0:
    maximum = numbers[0]
  for n in numbers:
    if n > maximum:
      maximum = n
  return maximum</code></pre>
</section>
<br>
<br>
<section>
  <h4>Sum & Average</h4>
    <pre class="stretch" style="font-size: .8em"><code class="python">def sum(numbers):
  asum = 0
  for n in numbers:
    asum += n
  return asum
<br>
def avg(numbers):
  asum = 0
  for n in numbers:
    asum += n
  return asum / len(numbers)</code></pre>
</section>
<br>
<section>
  <h4>Sum & Average</h4>
    <pre class="stretch" style="font-size: .8em"><code class="python">def sum(numbers):
  <mark>asum = 0
  for n in numbers:
    asum += n
  return asum</mark>
<br>
def avg(numbers):
  <mark>asum = 0
  for n in numbers:
    asum += n
  return asum</mark> / len(numbers)</code></pre>
</section>
<br>
<br>
<section>
  <h4>Sum & Average</h4>
    <pre class="stretch" style="font-size: .8em"><code class="python">def sum(numbers):
  asum = 0
  for n in numbers:
    asum += n
  return asum
<br>
def avg(numbers):
  <mark>asum = sum(numbers)</mark>
  return asum / len(numbers)</code></pre>
</section>
<br>
<br>
<section>
  <h4>Output</h4>
    <pre class="stretch" style="font-size: .7em"><code class="python">def print_output(minimum, maximum, asum, avg):
  print("Minimum: {:.1f}".format(minimum))
  print("Maximum: {:.1f}".format(maximum))
  print("Sum: {:.1f}".format(asum))
  print("Average: {:.1f}".format(avg))
</code></pre>
</section>
<br>
<br>
<section>
  <h4>Main</h4>
    <pre class="stretch" style="font-size: .4em"><code class="python">import sys
<br>
def main(args):
<br>
def read_input(filename): ...
def min(numbers): ...
def max(numbers): ...
def sum(numbers): ...
def avg(numbers): ...
def print_output(minimum, maximum, asum, avg): ...
<br>
# main guard
if __name__ == "__main__":
  main(sys.argv)
</code></pre>
</section>
<br>
<br>
<section>
  <h4>Main</h4>
    <pre class="stretch" style="font-size: .4em"><code class="python">import sys
<br>
def main(args):
  <mark>if len(args) != 2:
    print("Error opening file.")
    return</mark>
<br>
def read_input(filename): ...
def min(numbers): ...
def max(numbers): ...
def sum(numbers): ...
def avg(numbers): ...
def print_output(minimum, maximum, asum, avg): ...
<br>
# main guard
if __name__ == "__main__":
  main(sys.argv)
</code></pre>
</section>
<br>
<br>
<section>
  <h4>Main</h4>
    <pre class="stretch" style="font-size: .4em"><code class="python">import sys
<br>
def main(args):
  if len(args) != 2:
    print("Error opening file.")
    return
  <mark>numbers = read_input(args[1])</mark>
<br>
def read_input(filename): ...
def min(numbers): ...
def max(numbers): ...
def sum(numbers): ...
def avg(numbers): ...
def print_output(minimum, maximum, asum, avg): ...
<br>
# main guard
if __name__ == "__main__":
  main(sys.argv)
</code></pre>
</section>
<br>
<br>
<section>
  <h4>Main</h4>
    <pre class="stretch" style="font-size: .4em"><code class="python">import sys
<br>
def main(args):
  if len(args) != 2:
    print("Error opening file.")
    return
  numbers = read_input(args[1])
  if len(numbers) == 0:
    return
  <mark>minimum = min(numbers)
  maximum = max(numbers)
  asum = sum(numbers)
  average = avg(numbers)</mark>
<br>
def read_input(filename): ...
def min(numbers): ...
def max(numbers): ...
def sum(numbers): ...
def avg(numbers): ...
def print_output(minimum, maximum, asum, avg): ...
<br>
# main guard
if __name__ == "__main__":
  main(sys.argv)
</code></pre>
</section>
<br>
<br>
<section>
  <h4>Main</h4>
    <pre class="stretch" style="font-size: .4em"><code class="python">import sys
<br>
def main(args):
  if len(args) != 2:
    print("Error opening file.")
    return
  numbers = read_input(args[1])
  if len(numbers) == 0:
    return
  minimum = min(numbers)
  maximum = max(numbers)
  asum = sum(numbers)
  average = avg(numbers)
  <mark>print_output(minimum, maximum, asum, average)</mark>
<br>
def read_input(filename): ...
def min(numbers): ...
def max(numbers): ...
def sum(numbers): ...
def avg(numbers): ...
def print_output(minimum, maximum, asum, avg): ...
<br>
# main guard
if __name__ == "__main__":
  main(sys.argv)
</code></pre>
</section>
<br>
<br>
<br>
<section>
  <h4>Main</h4>
    <pre class="stretch" style="font-size: .4em"><code class="python">import sys
<br>
def main(args):
  if len(args) != 2:
    print("Error opening file.")
    return
  numbers = read_input(args[1])
  if len(numbers) == 0:
    return
  minimum = min(numbers)
  maximum = max(numbers)
  asum = sum(numbers)
  average = avg(numbers)
  print_output(minimum, maximum, asum, average)
  <mark>return</mark>
<br>
def read_input(filename): ...
def min(numbers): ...
def max(numbers): ...
def sum(numbers): ...
def avg(numbers): ...
def print_output(minimum, maximum, asum, avg): ...
<br>
# main guard
if __name__ == "__main__":
  main(sys.argv)
</code></pre>
</section>
<br>
<br>
<br>
<section>
  <h4>Main</h4>
    <pre class="stretch" style="font-size: .4em"><code class="python">import sys
<br>
def main(args):
  if len(args) != 2:
    print("Error opening file.")
    return
  numbers = read_input(args[1])
  if len(numbers) == 0:
    return
  minimum = min(numbers)
  maximum = max(numbers)
  asum = sum(numbers)
  average = avg(numbers)
  print_output(minimum, maximum, asum, average)
  return
<br>
def read_input(filename): ...
def min(numbers): ...
def max(numbers): ...
def sum(numbers): ...
def avg(numbers): ...
def print_output(minimum, maximum, asum, avg): ...
<br>
# main guard
if __name__ == "__main__":
  main(sys.argv)
</code></pre>
</section>
<br>