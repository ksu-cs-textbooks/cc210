---
type: "reveal"
hidden: true
---

<section>
	<h1>Not</h1>
	<h1>&not;</h1>
</section>
<section>
	<table class="reveal">
		<tr>
			<th>A</th>
			<th>B</th>
			<th>&not;A</th>
			<th>&not;B</th>
		</tr>
		<tr>
			<td>F</td>
			<td>F</td>
			<td>T</td>
			<td>T</td>
		</tr>
		<tr>
			<td>F</td>
			<td>T</td>
			<td>T</td>
			<td>F</td>
		</tr>
		<tr>
			<td>T</td>
			<td>F</td>
			<td>F</td>
			<td>T</td>
		</tr>
		<tr>
			<td>T</td>
			<td>T</td>
			<td>F</td>
			<td>F</td>
		</tr>
  </table>
</section>
<section>
	<h3>&not;A</h3>
	<img class="stretch plain" src="/cc210/images/03-bool/3.2.nota.png">
</section>
<section>
	<h3>&not;C</h3>
	<img class="stretch plain" src="/cc210/images/03-bool/3.2.notc.png">
</section>
<section>
	<h1>And</h1>
	<h1>&#8896;</h1>
</section>
<section>
	<table class="reveal">
		<tr>
			<th>A</th>
			<th>B</th>
			<th>A &#8896; B</th>
		</tr>
		<tr>
			<td>F</td>
			<td>F</td>
			<td>F</td>
		</tr>
		<tr>
			<td>F</td>
			<td>T</td>
			<td>F</td>
		</tr>
		<tr>
			<td>T</td>
			<td>F</td>
			<td>F</td>
		</tr>
		<tr>
			<td>T</td>
			<td>T</td>
			<td>T</td>
		</tr>
  </table>
</section>
<section>
	<h3>A &#8896; B</h3>
	<img class="stretch plain" src="/cc210/images/03-bool/3.2.aandb.png">
</section>
<section>
	<h3>A &#8896; B &#8896; C</h3>
	<img class="stretch plain" src="/cc210/images/03-bool/3.2.aandbandc.png">
</section>
<section>
	<h1>Or</h1>
	<h1>&#8897;</h1>
</section>
<section>
	<table class="reveal">
		<tr>
			<th>A</th>
			<th>B</th>
			<th>A &#8897; B</th>
		</tr>
		<tr>
			<td>F</td>
			<td>F</td>
			<td>F</td>
		</tr>
		<tr>
			<td>F</td>
			<td>T</td>
			<td>T</td>
		</tr>
		<tr>
			<td>T</td>
			<td>F</td>
			<td>T</td>
		</tr>
		<tr>
			<td>T</td>
			<td>T</td>
			<td>T</td>
		</tr>
  </table>
</section>
<section>
	<h3>A &#8897; B</h3>
	<img class="stretch plain" src="/cc210/images/03-bool/3.2.aorb.png">
</section>
<section>
	<h3>A &#8897; B &#8897; C</h3>
	<img class="stretch plain" src="/cc210/images/03-bool/3.2.aorborc.png">
</section>
<section>
	<h1>Exclusive Or (Xor)</h1>
	<h1>&oplus;</h1>
</section>
<section>
	<table class="reveal">
		<tr>
			<th>A</th>
			<th>B</th>
			<th>A &oplus; B</th>
		</tr>
		<tr>
			<td>F</td>
			<td>F</td>
			<td>F</td>
		</tr>
		<tr>
			<td>F</td>
			<td>T</td>
			<td>T</td>
		</tr>
		<tr>
			<td>T</td>
			<td>F</td>
			<td>T</td>
		</tr>
		<tr>
			<td>T</td>
			<td>T</td>
			<td>F</td>
		</tr>
  </table>
</section>
<section>
	<h3>A &oplus; B</h3>
	<img class="stretch plain" src="/cc210/images/03-bool/3.2.axorb.png">
</section>
<section>
	<h3>A &oplus; B</h3>
	<img class="stretch plain" src="/cc210/images/03-bool/3.2.axorb3.png">
</section>
<section>
	<h3>A &oplus; B &oplus; C</h3>
	<img class="stretch plain" src="/cc210/images/03-bool/3.2.axorbxorc.png">
</section>
