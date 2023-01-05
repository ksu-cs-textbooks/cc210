---
type: "reveal"
hidden: true
---
<section>
  <h3>Lists</h3>
  <ul>
    <li>Store Any Number of Elements</li>
    <li>Searchable</li>
    <li>Remove Elements</li>
    <li>Sortable</li>
  </ul>
</section>
<section>
  <p style="font-size: .7em">Using the integer provided as input, the program should generate a list of numbers representing the <b>Fibonacci sequence</b> containing that many entries.</p>
  <p style="font-size: .7em">Before printing the list, the program should perform two additional operations on the list. First, if the <b>integer provided as input</b> is contained in the list, it <b>should be removed</b>. Secondly, the list should be presented in <b>descending order</b>, with the largest value first.</p>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="python">@staticmethod
def make_list(x):<br>
</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="python">@staticmethod
def make_list(x):
  list = [0, 1]
</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="python">@staticmethod
def make_list(x):
  list = [0, 1]
  for i in range(2, x):<br><br>
</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="python">@staticmethod
def make_list(x):
  list = [0, 1]
  for i in range(2, x):
    new_number = list[i-1] + list[i-2]<br>
</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="python">@staticmethod
def make_list(x):
  list = [0, 1]
  for i in range(2, x):
    new_number = list[i-1] + list[i-2]
    list.append(new_number)
</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="python">@staticmethod
def make_list(x):
  list = [0, 1]
  for i in range(2, x):
    new_number = list[i-1] + list[i-2]
    list.append(new_number)
  if x in list:<br>
</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="python">@staticmethod
def make_list(x):
  list = [0, 1]
  for i in range(2, x):
    new_number = list[i-1] + list[i-2]
    list.append(new_number)
  if x in list:
    list.remove(x)
</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="python">@staticmethod
def make_list(x):
  list = [0, 1]
  for i in range(2, x):
    new_number = list[i-1] + list[i-2]
    list.append(new_number)
  if x in list:
    list.remove(x)
  list.sort(reverse=True)
</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .58em"><code class="python">@staticmethod
def make_list(x):
  list = [0, 1]
  for i in range(2, x):
    new_number = list[i-1] + list[i-2]
    list.append(new_number)
  if x in list:
    list.remove(x)
  list.sort(reverse=True)
  return list
</code></pre>
  </div>
</section><br>