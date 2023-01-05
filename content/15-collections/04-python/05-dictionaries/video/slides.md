---
type: "reveal"
hidden: true
---
<section>
  <h3>Dictionaries (Maps)</h3>
  <ul>
    <li>Associate <b>key</b> with <b>value</b></li>
    <li>Key & value can be any data type</li>
    <li>Easily searchable by key</li>
    <li>Store and retrieve data quickly</li>
  </ul>
</section>
<section>
  <p style="font-size: .7em">The program will store a dictionary that associates lines of input with random integers. When a line of input is read, the program will check to see if that line has already been used as a key in the dictionary. If so, it will return the value associated with that key.</p>
  <p style="font-size: .7em">If the dictionary does not contain an entry for that key, the program should generate a new random integer and store it in the dictionary, using the input line as the key.</p>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="python">import sys
import random<br>
class DictExample:<br>
  dictionary = {}<br>
  @staticmethod
  def get_output(line):
</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="python">import sys
import random<br>
class DictExample:<br>
  dictionary = {}<br>
  @staticmethod
  def get_output(line):
    if line in DictExample.dictionary:<br>
</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="python">import sys
import random<br>
class DictExample:<br>
  dictionary = {}<br>
  @staticmethod
  def get_output(line):
    if line in DictExample.dictionary:
      return DictExample.dictionary[line]
</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="python">import sys
import random<br>
class DictExample:<br>
  dictionary = {}<br>
  @staticmethod
  def get_output(line):
    if line in DictExample.dictionary:
      return DictExample.dictionary[line]
    else:<br><br><br>
</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="python">import sys
import random<br>
class DictExample:<br>
  dictionary = {}<br>
  @staticmethod
  def get_output(line):
    if line in DictExample.dictionary:
      return DictExample.dictionary[line]
    else:
      new_number = random.randint(-1000000, 1000000)<br><br>
</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="python">import sys
import random<br>
class DictExample:<br>
  dictionary = {}<br>
  @staticmethod
  def get_output(line):
    if line in DictExample.dictionary:
      return DictExample.dictionary[line]
    else:
      new_number = random.randint(-1000000, 1000000)
      DictExample.dictionary[line] = new_number<br>
</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .44em"><code class="python">import sys
import random<br>
class DictExample:<br>
  dictionary = {}<br>
  @staticmethod
  def get_output(line):
    if line in DictExample.dictionary:
      return DictExample.dictionary[line]
    else:
      new_number = random.randint(-1000000, 1000000)
      DictExample.dictionary[line] = new_number
      return new_number
</code></pre>
  </div>
</section><br>