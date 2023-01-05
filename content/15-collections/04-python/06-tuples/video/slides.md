---
type: "reveal"
hidden: true
---
<section>
  <h3>Tuples</h3>
  <ul>
    <li>Finite ordered list of values</li>
    <li>Multiple values in a single object</li>
    <li>Similar to a simple class or list</li>
    <li><i>Included in Python by default</i></li>
  </ul>
</section><br>
<section>
  <p style="font-size: .6em">When a player makes a guess, the program should respond with one of the four cardinal directions: "North", "South", "East", "West", indicating the direction of the hidden item from the guess. For simplicity, the program will only respond "North" or "South" if the player's guess is not on the same row, or x coordinate, as the location, and "East" or "West" only if the player's guess is on the same row as the location. If the player guesses correctly, simply print "Found!" and terminate the program. If the player repeats a guess, the program should print "Repeat!" instead of a cardinal direction.</p>
  <p style="font-size: .6em">The hidden location should be randomly generated and stored in an instance of the IntTuple class defined above as a global variable, and the program should maintain a global list of IntTuples representing the locations already guessed.</p>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .43em"><code class="python">import sys
import random<br>
class TupleExample:<br>
  guesses = []
  location = None<br>
  @staticmethod
  def make_guess(x, y):<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
  </code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .43em"><code class="python">import sys
import random<br>
class TupleExample:<br>
  guesses = []
  location = None<br>
  @staticmethod
  def make_guess(x, y):
    if TupleExample.location is None:
      TupleExample.location = random.randint(0, 9), random.randint(0, 9)<br><br><br><br><br><br><br><br><br><br><br><br><br>
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .43em"><code class="python">import sys
import random<br>
class TupleExample:<br>
  guesses = []
  location = None<br>
  @staticmethod
  def make_guess(x, y):
    if TupleExample.location is None:
      TupleExample.location = random.randint(0, 9), random.randint(0, 9)
    guess = x, y<br><br><br><br><br><br><br><br><br><br><br><br>
  </code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .43em"><code class="python">import sys
import random<br>
class TupleExample:<br>
  guesses = []
  location = None<br>
  @staticmethod
  def make_guess(x, y):
    if TupleExample.location is None:
      TupleExample.location = random.randint(0, 9), random.randint(0, 9)
    guess = x, y
    if guess == TupleExample.location:
      return "Found!"<br><br><br><br><br><br><br><br><br><br><br>
</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .43em"><code class="python">import sys
import random<br>
class TupleExample:<br>
  guesses = []
  location = None<br>
  @staticmethod
  def make_guess(x, y):
    if TupleExample.location is None:
      TupleExample.location = random.randint(0, 9), random.randint(0, 9)
    guess = x, y
    if guess == TupleExample.location:
      return "Found!"
    if guess in TupleExample.guesses:
      return "Repeat!"<br><br><br><br><br><br><br><br><br>
</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .43em"><code class="python">import sys
import random<br>
class TupleExample:<br>
  guesses = []
  location = None<br>
  @staticmethod
  def make_guess(x, y):
    if TupleExample.location is None:
      TupleExample.location = random.randint(0, 9), random.randint(0, 9)
    guess = x, y
    if guess == TupleExample.location:
      return "Found!"
    if guess in TupleExample.guesses:
      return "Repeat!"
    TupleExample.guesses.append(guess)<br><br><br><br><br><br><br><br>
</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .43em"><code class="python">import sys
import random<br>
class TupleExample:<br>
  guesses = []
  location = None<br>
  @staticmethod
  def make_guess(x, y):
    if TupleExample.location is None:
      TupleExample.location = random.randint(0, 9), random.randint(0, 9)
    guess = x, y
    if guess == TupleExample.location:
      return "Found!"
    if guess in TupleExample.guesses:
      return "Repeat!"
    TupleExample.guesses.append(guess)
    if guess[0] > TupleExample.location[0]:
      return "North"
    if guess[0] &lt; TupleExample.location[0]:
      return "South"<br><br><br><br>
</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .43em"><code class="python">import sys
import random<br>
class TupleExample:<br>
  guesses = []
  location = None<br>
  @staticmethod
  def make_guess(x, y):
    if TupleExample.location is None:
      TupleExample.location = random.randint(0, 9), random.randint(0, 9)
    guess = x, y
    if guess == TupleExample.location:
      return "Found!"
    if guess in TupleExample.guesses:
      return "Repeat!"
    TupleExample.guesses.append(guess)
    if guess[0] > TupleExample.location[0]:
      return "North"
    if guess[0] &lt; TupleExample.location[0]:
      return "South"
    if guess[1] > TupleExample.location[1]:
      return "West"
    else:
      return "East"</code></pre>
  </div>
</section><br>