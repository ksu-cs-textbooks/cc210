---
type: "reveal"
hidden: true
---
<section>
	<h2>Problem Statement</h2>
</section>
<section>
  <ol style="font-size: .45em">
    <li>When the program is executed, a single command-line argument should be provided. That argument will be the path to a file containing descriptions for each tool in the toolbox. If the argument is not provided, or the input file cannot be successfully read or parsed, the program should print "Invalid Input" and terminate.</li>
    <li>The input file will contain at least two lines of input. The first line will give the number of tools included in the input file as an integer. Each subsequent line will identify a particular tool using the name of the class representing the tool, followed by values for each attribute of the tool. The values will be separated by spaces, and listed in the same order as those attributes are accepted in the tool's constructor.</li>
    <li>Once the input is read, the program will then accept a query as input via the terminal. That input should consist of multiple parts on a single line, separated by a space. The first part will be the name of an action that needs to be performed, and then following that will be one or more values to be provided to that action as arguments, separated by spaces.</li>
    <li>The program will review its list of available tools, finding any tool that supports that action. It will then call the method in that tool that corresponds with the action (the method and action names will be the same), providing the values as an arguments. If the tool responds with true to that method call, then that tool is able to perform that action. The program should print the description of the appropriate tool to the terminal and terminate. In this example, each query will only result in one matching tool, if any.</li>
    <li>If a matching tool cannot be found, or there is any errors reading the input from the terminal, the program should print "Invalid Tool" and terminate.</li>
  </ol>
</section>
<section>
  <h2>Head &rarr; Desk</h2>
	<img class="stretch plain" src="https://media.giphy.com/media/HlqvH9JrahLZ6/source.gif">
  <p class="imagecredit">Image Credit: <a href="https://media.giphy.com/media/HlqvH9JrahLZ6">Giphy</a></p>
	<p>Let's break it down into classes</p>
</section><br>
<section>
  <img class="stretch plain" src="/cc210/images/13-inherit/12.7.p.8.uml.png">
</section><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.p.8.tool.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">from abc import ABC, abstractmethod<br>
class Tool(ABC):<br>
  def __init__(self):
    pass<br>
  @abstractmethod
  def describe(self):
    pass</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.p.8.wrench.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">from Tool import *
from abc import ABC, abstractmethod<br>
class Wrench(Tool, ABC):<br>
  def __init__(self, length):
    self.__length = length<br>
  @property
  def length(self):
    return self.__length<br>
  @abstractmethod
  def tighten(self, clearance, size):
    pass</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.p.8.saw.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">from Tool import *
from abc import ABC, abstractmethod<br>
class Saw(Tool, ABC):<br>
  def __init__(self, length):
    self.__length = length<br>
  @property
  def length(self):
    return self.__length<br>
  @abstractmethod
  def cut(self, length, material):
    pass </code></pre>
  </div>
</section><br><br>
<section>
  <img class="stretch plain" src="/cc210/images/13-inherit/stop.png">
  <h3>Check Structure!</h3>
</section><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.p.8.aj.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Wrench import *<br>
class AdjustableWrench(Wrench):<br>
  def __init__(self, length, min_size, max_size):
    super().__init__(length)
    self.__min_size = min_size
    self.__max_size = max_size<br>
  @property
  def min_size(self):
    return self.__min_size<br>
  @property
  def max_size(self):
    return self.__max_size<br>
  # other methods go here</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.p.8.aj.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Wrench import *<br>
class AdjustableWrench(Wrench):<br>
  def __init__(self, length, min_size, max_size):
    super().__init__(length)
    self.__min_size = min_size
    self.__max_size = max_size<br>
  @property
  def min_size(self):
    return self.__min_size<br>
  @property
  def max_size(self):
    return self.__max_size<br>
  def describe(self):
    return "AdjustableWrench: Length: {} MinSize: {}
            MaxSize: {}".format(self.__length,
            self.__min_size, self.__max_size)<br>
  # other methods go here</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.p.8.aj.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Wrench import *<br>
class AdjustableWrench(Wrench):<br>
  def __init__(self, length, min_size, max_size):
    super().__init__(length)
    self.__min_size = min_size
    self.__max_size = max_size<br>
  @property
  def min_size(self):
    return self.__min_size<br>
  @property
  def max_size(self):
    return self.__max_size<br>
  def describe(self):
    return "AdjustableWrench: Length: {} MinSize: {}
            MaxSize: {}".format(<mark>self.__length</mark>,
            self.__min_size, self.__max_size)<br>
  # other methods go here</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.p.8.aj.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Wrench import *<br>
class AdjustableWrench(Wrench):<br>
  def __init__(self, length, min_size, max_size):
    super().__init__(length)
    self.__min_size = min_size
    self.__max_size = max_size<br>
  @property
  def min_size(self):
    return self.__min_size<br>
  @property
  def max_size(self):
    return self.__max_size<br>
  def describe(self):
    return "AdjustableWrench: Length: {} MinSize: {}
            MaxSize: {}".format(<mark style="background-color: red">self.__length</mark>,
            self.__min_size, self.__max_size)<br>
  # other methods go here</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.p.8.aj.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Wrench import *<br>
class AdjustableWrench(Wrench):<br>
  def __init__(self, length, min_size, max_size):
    super().__init__(length)
    self.__min_size = min_size
    self.__max_size = max_size<br>
  @property
  def min_size(self):
    return self.__min_size<br>
  @property
  def max_size(self):
    return self.__max_size<br>
  def describe(self):
    return "AdjustableWrench: Length: {} MinSize: {}
            MaxSize: {}".format(<mark>self.length</mark>,
            self.__min_size, self.__max_size)<br>
  # other methods go here</code></pre>
  </div>
</section><br>
<section>
  <h3>Adjustable Wrench</h3>
  <img class="stretch plain" src="/cc210/images/13-inherit/12.7.x.8.adjustable_wiki.png">
</section><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.p.8.aj.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Wrench import *<br>
class AdjustableWrench(Wrench):<br>
  def __init__(self, length, min_size, max_size):
    super().__init__(length)
    self.__min_size = min_size
    self.__max_size = max_size<br>
  @property
  def min_size(self):
    return self.__min_size<br>
  @property
  def max_size(self):
    return self.__max_size<br>
  def describe(self):
    return "AdjustableWrench: Length: {} MinSize: {}
            MaxSize: {}".format(self.length,
            self.min_size, self.max_size)<br>
  def tighten(self, clearance, size):
    return clearance >= self.length and
          size >= self.min_size and
          size <= self.max_size</code></pre>
  </div>
</section><br>
<section>
  <h3>Combination Wrench</h3>
  <img class="stretch plain" src="/cc210/images/13-inherit/12.7.x.8.combination_wiki.jpg">
</section><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.p.8.co.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Wrench import *<br>
class CombinationWrench(Wrench):<br>
  def __init__(self, length, size):
    super().__init__(length)
    self.__size = size<br>
  @property
  def size(self):
    return self.__size<br>
  def describe(self):
    return "CombinationWrench Length: {} Size: {}"
            .format(self.length, self.size)<br>
  def tighten(self, clearance, size):
    return clearance >= self.length and
            size == self.size</code></pre>
  </div>
</section><br>
<section>
  <h3>Open End Wrench</h3>
  <img class="stretch plain" src="/cc210/images/13-inherit/12.7.x.8.openend_wiki.jpg">
</section><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.p.8.oe.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Wrench import *<br>
class OpenEndWrench(Wrench):<br>
  def __init__(self, length, size_one, size_two):
    super().__init__(length)
    self.__size_one = size_one
    self.__size_two = size_two<br>
  @property
  def size_one(self):
    return self.__size_one<br>
  @property
  def size_two(self):
    return self.__size_two<br>
  def describe(self):
    return "CombinationWrench Length: {} SizeOne: {}
            SizeTwo: {}".format(self.length,
            self.size_one, self.size_two)<br>
  def tighten(self, clearance, size):
    return clearance >= self.length and
            (size == self.size_one or
             size == self.size_two)</code></pre>
  </div>
</section><br><br>
<section>
  <img class="stretch plain" src="/cc210/images/13-inherit/stop.png">
  <h3>Check Structure!</h3>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.p.8.cc.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Saw import *<br>
class CrossCutSaw(Saw):<br>
  def __init__(self, length, materials):
    super().__init__(length)
    self.__materials = materials.split(":")<br>
  @property
  def materials(self):
    return ", ".join(self.__materials)<br>
  def describe(self):
    "CrossCutSaw Length: {} Materials: {}".format(
          self.length, self.materials)<br>
  # additional methods here</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.p.8.cc.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Saw import *<br>
class CrossCutSaw(Saw):<br>
  def __init__(self, length, materials):
    super().__init__(length)
    self.__materials = <mark>materials.split(":")</mark><br>
  @property
  def materials(self):
    return <mark>", ".join(self.__materials)</mark><br>
  def describe(self):
    "CrossCutSaw Length: {} Materials: {}".format(
          self.length, self.materials)<br>
  # additional methods here</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.p.8.cc.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Saw import *<br>
class CrossCutSaw(Saw):<br>
  def __init__(self, length, materials):
    super().__init__(length)
    self.__materials = materials.split(":")<br>
  @property
  def materials(self):
    return ", ".join(self.__materials)<br>
  def describe(self):
    "CrossCutSaw Length: {} Materials: {}".format(
          self.length, self.materials)<br>
  def __find_material(self, material):
    for m in self.__materials:
      if m == material:
        return True
    return False<br>
  # additional methods here</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.p.8.cc.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Saw import *<br>
class CrossCutSaw(Saw):<br>
  def __init__(self, length, materials):
    super().__init__(length)
    self.__materials = materials.split(":")<br>
  @property
  def materials(self):
    return ", ".join(self.__materials)<br>
  def describe(self):
    "CrossCutSaw Length: {} Materials: {}".format(
          self.length, self.materials)<br>
  def __find_material(self, material):
    for m in self.__materials:
      if m == material:
        return True
    return False<br>
  def cut(self, length, material):
    return length &lt; self.length
        and self.__find_material(material)</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.p.8.hs.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Saw import *<br>
class HackSaw(Saw):<br>
  def __init__(self, length):
    super().__init__(length)<br>
  def describe(self):
    return "HackSaw Length: {} Material: metal".
        format(self.length)<br>
  def cut(self, length, material):
    return length &lt; self.length and
        material == "metal"</code></pre>
  </div>
</section><br><br>
<section>
  <img class="stretch plain" src="/cc210/images/13-inherit/stop.png">
  <h3>Check Structure!</h3>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.p.8.m.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Wrench import *
from AdjustableWrench import *
from CombinationWrench import *
from OpenEndWrench import *
from Saw import *
from HackSaw import *
from CrossCutSaw import *<br>
import sys<br>
class Main:<br>
  # methods go here<br>
# main guard
if __name__ == "__main__":
  Main.main(sys.argv)</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.p.8.m.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Wrench import *
from AdjustableWrench import *
from CombinationWrench import *
from OpenEndWrench import *
from Saw import *
from HackSaw import *
from CrossCutSaw import *<br>
import sys<br>
class Main:<br>
  <mark># methods go here</mark><br>
# main guard
if __name__ == "__main__":
  Main.main(sys.argv)</code></pre>
  </div>
</section><br><br>
<section>
  <pre class="stretch" style="font-size: .37em"><code class="python">@staticmethod
def read_input(filename):
  try:
    with open(filename) as reader:
      num_tools = int(reader.readline())
      tools = []<br><br><br>
      return tools
  except Exception:
    print("Invalid Input")
    return []</code></pre>
</section><br><br>
<section>
  <pre class="stretch" style="font-size: .37em"><code class="python">@staticmethod
def read_input(filename):
  try:
    with open(filename) as reader:
      num_tools = int(reader.readline())
      tools = []
      for i in range(0, num_tools):<br><br>
      return tools
  except Exception:
    print("Invalid Input")
    return []</code></pre>
</section><br><br>
<section>
  <pre class="stretch" style="font-size: .37em"><code class="python">@staticmethod
def read_input(filename):
  try:
    with open(filename) as reader:
      num_tools = int(reader.readline())
      tools = []
      for i in range(0, num_tools):
        line = reader.readline().split(" ")<br><br><br>
      return tools
  except Exception:
    print("Invalid Input")
    return []</code></pre>
</section><br><br>
<section>
  <pre class="stretch" style="font-size: .37em"><code class="python">@staticmethod
def read_input(filename):
  try:
    with open(filename) as reader:
      num_tools = int(reader.readline())
      tools = []
      for i in range(0, num_tools):
        line = reader.readline().split(" ")<br>
        if line[0] == "AdjustableWrench":<br>
        elif line[0] == "OpenEndWrench":<br>
        elif line[0] == "CombinationWrench":<br>
        elif line[0] == "CrossCutSaw":<br>
        elif line[0] == "HackSaw":<br>
        else:
          raise Exception("Unknown Tool: " + line[0])
      return tools
  except Exception:
    print("Invalid Input")
    return []</code></pre>
</section><br>
<section>
  <pre class="stretch" style="font-size: .37em"><code class="python">@staticmethod
def read_input(filename):
  try:
    with open(filename) as reader:
      num_tools = int(reader.readline())
      tools = []
      for i in range(0, num_tools):
        line = reader.readline().split(" ")
        length = int(line[1])
        if line[0] == "AdjustableWrench":
          min_size = int(line[2])
          max_size = int(line[3])
          tools.append(AdjustableWrench(length, min_size, max_size))
        elif line[0] == "OpenEndWrench":
          size_one = int(line[2])
          size_two = int(line[3])
          tools.append(OpenEndWrench(length, size_one, size_two))
        elif line[0] == "CombinationWrench":
          size = int(line[2])
          tools.append(CombinationWrench(length, size))
        elif line[0] == "CrossCutSaw":
          tools.append(CrossCutSaw(length, line[2]))
        elif line[0] == "HackSaw":
          tools.append(HackSaw(length))
        else:
          raise Exception("Unknown Tool: " + line[0])
      return tools
  except Exception:
    print("Invalid Input")
    return []</code></pre>
</section><br><br>
<section>
  <pre class="stretch" style="font-size: .5em"><code class="python">@staticmethod
def find_tool(tools, query):
  query_parts = query.split(" ")
  </code></pre>
</section><br>
<section>
  <pre class="stretch" style="font-size: .5em"><code class="python">@staticmethod
def find_tool(tools, query):
  query_parts = query.split(" ")
  if query_parts[0] == "tighten":<br><br><br><br><br><br><br>
  elif query_parts[0] == "cut":<br><br><br><br><br><br>
  else:
    </code></pre>
</section><br>
<section>
  <pre class="stretch" style="font-size: .5em"><code class="python">@staticmethod
def find_tool(tools, query):
  query_parts = query.split(" ")
  if query_parts[0] == "tighten":
    clearance = int(query_parts[1])
    size = int(query_parts[2])<br><br><br><br><br>
  elif query_parts[0] == "cut":
    length = int(query_parts[1])<br><br><br><br><br>
  else:
    </code></pre>
</section><br><br><br>
<section>
  <pre class="stretch" style="font-size: .5em"><code class="python">@staticmethod
def find_tool(tools, query):
  query_parts = query.split(" ")
  if query_parts[0] == "tighten":
    clearance = int(query_parts[1])
    size = int(query_parts[2])
    for t in tools:
      if isinstance(t, Wrench):<br><br><br>
  elif query_parts[0] == "cut":
    length = int(query_parts[1])
    for t in tools:
      if isinstance(t, Saw):<br><br><br>
  else:
    </code></pre>
</section><br><br>
<section>
  <pre class="stretch" style="font-size: .5em"><code class="python">@staticmethod
def find_tool(tools, query):
  query_parts = query.split(" ")
  if query_parts[0] == "tighten":
    clearance = int(query_parts[1])
    size = int(query_parts[2])
    for t in tools:
      if isinstance(t, Wrench):
        if t.tighten(clearance, size):
          return t<br>
  elif query_parts[0] == "cut":
    length = int(query_parts[1])
    for t in tools:
      if isinstance(t, Saw):
        if t.cut(length, query_parts[2]):
          return t<br>
  else:
    </code></pre>
</section><br>
<section>
  <pre class="stretch" style="font-size: .5em"><code class="python">@staticmethod
def find_tool(tools, query):
  query_parts = query.split(" ")
  if query_parts[0] == "tighten":
    clearance = int(query_parts[1])
    size = int(query_parts[2])
    for t in tools:
      if isinstance(t, Wrench):
        if t.tighten(clearance, size):
          return t
    <mark>return ??</mark>
  elif query_parts[0] == "cut":
    length = int(query_parts[1])
    for t in tools:
      if isinstance(t, Saw):
        if t.cut(length, query_parts[2]):
          return t
    <mark>return ??</mark>
  else:
    <mark>return ??</mark></code></pre>
</section><br><br>
<section>
  <pre class="stretch" style="font-size: .5em"><code class="python">@staticmethod
def find_tool(tools, query):
  query_parts = query.split(" ")
  if query_parts[0] == "tighten":
    clearance = int(query_parts[1])
    size = int(query_parts[2])
    for t in tools:
      if isinstance(t, Wrench):
        if t.tighten(clearance, size):
          return t
    <mark>return None</mark>
  elif query_parts[0] == "cut":
    length = int(query_parts[1])
    for t in tools:
      if isinstance(t, Saw):
        if t.cut(length, query_parts[2]):
          return t
    <mark>return None</mark>
  else:
    <mark>return None</mark></code></pre>
</section><br><br>
<section>
  <pre class="stretch" style="font-size: .5em"><code class="python">@staticmethod
def find_tool(tools, query):
  query_parts = query.split(" ")
  if query_parts[0] == "tighten":
    clearance = int(query_parts[1])
    size = int(query_parts[2])
    for t in tools:
      if isinstance(t, Wrench):
        if t.tighten(clearance, size):
          return t
    return None
  elif query_parts[0] == "cut":
    length = int(query_parts[1])
    for t in tools:
      if isinstance(t, Saw):
        if t.cut(length, query_parts[2]):
          return t
    return None
  else:
    return None</code></pre>
</section><br><br>
<section>
  <pre class="stretch" style="font-size: .5em"><code class="python">@staticmethod
def main(args):
  if len(args) != 2:
    print("Invalid Input")
    return
</code></pre>
</section><br><br>
<section>
  <pre class="stretch" style="font-size: .5em"><code class="python">@staticmethod
def main(args):
  if len(args) != 2:
    print("Invalid Input")
    return<br>
  tools = Main.read_input(args[1])
</code></pre>
</section><br><br>
<section>
  <pre class="stretch" style="font-size: .5em"><code class="python">@staticmethod
def main(args):
  if len(args) != 2:
    print("Invalid Input")
    return<br>
  tools = Main.read_input(args[1])<br>
  if len(tools) == 0:
    return
</code></pre>
</section><br><br>
<section>
  <pre class="stretch" style="font-size: .5em"><code class="python">@staticmethod
def main(args):
  if len(args) != 2:
    print("Invalid Input")
    return<br>
  tools = Main.read_input(args[1])<br>
  if len(tools) == 0:
    return<br>
  try:
    with sys.stdin as reader:<br><br><br><br><br><br>
  except Exception:
    print("Invalid Tool")
    return</code></pre>
</section><br>
<section>
  <pre class="stretch" style="font-size: .5em"><code class="python">@staticmethod
def main(args):
  if len(args) != 2:
    print("Invalid Input")
    return<br>
  tools = Main.read_input(args[1])<br>
  if len(tools) == 0:
    return<br>
  try:
    with sys.stdin as reader:
      query = reader.readline()
      t = Main.find_tool(tools, query)<br><br><br><br>
  except Exception:
    print("Invalid Tool")
    return</code></pre>
</section><br>
<section>
  <pre class="stretch" style="font-size: .5em"><code class="python">@staticmethod
def main(args):
  if len(args) != 2:
    print("Invalid Input")
    return<br>
  tools = Main.read_input(args[1])<br>
  if len(tools) == 0:
    return<br>
  try:
    with sys.stdin as reader:
      query = reader.readline()
      t = Main.find_tool(tools, query)
      if t is not None:
        print(t.describe())
      else:
        print("Invalid Tool")
  except Exception:
    print("Invalid Tool")
    return</code></pre>
</section><br>