---
type: "reveal"
hidden: true
---
<section>
	<h2>Problem Statement</h2>
</section>
<section>
  <h3>Modified Blackjack</h3>
  <ol style="font-size: .5em">
    <li>The game consists of a single player playing against the dealer, played by our program in this example.</li>
    <li>Each player is initially dealt two cards from a standard 52 card deck. Each card's value is its face value, with face cards having a value of 10, and aces are valued 11.</li>
    <li>The object of the game is to get a higher total value than the other player, without going over 21.</li>
    <li>The game consists of several steps:<ol>
      <li>Both the player and the dealer review the two cards they are dealt. Both the player and the dealer can see the opponent's hand as well.</li>
      <li>The player is given the option to draw additional cards. The player may continue to draw cards until she or he chooses to stop, or their total value is greater than 21.</li>
      <li>If the player stops before going over 21, the dealer must draw cards to try and beat the player. The dealer stops drawing cards either when their total beats the player, or the dealer's total is greater than 21.</li>
      <li>At the end, the participant with the greatest card value that is less than or equal to 21 wins the game. If it is a tie, the dealer wins.</li>
    </ol></li>
  </ol>
</section>
<section>
  <h2>*~*sigh*~*</h2>
	<img class="stretch plain" src="https://media.giphy.com/media/Fjr6v88OPk7U4/source.gif">
  <p class="imagecredit">Image Credit: <a href="https://giphy.com/gifs/eye-roll-bitch-please-Fjr6v88OPk7U4">Giphy</a></p>
	<p>Let's break it down into smaller parts</p>
</section><br><br>
<section>
  <h2>Use Classes!</h2>
	<img class="stretch plain" src="https://media.giphy.com/media/3NtY188QaxDdC/source.gif">
  <p class="imagecredit">Image Credit: <a href="https://giphy.com/gifs/3NtY188QaxDdC">Giphy</a></p>
	<p>Let's break it down into <b style="color:#512888">classes</b></p>
</section><br><br>
<section>
  <img class="stretch plain" src="/cc210/images/12-class/11.6.j.10.blackjack.png">
</section><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.card.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Card{<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.card.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Card{
  //Attributes
  private String suit;
  private String name;
  private int value;<br>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.card.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Card{
  //Attributes
  private String suit;
  private String name;
  private int value;<br>
  //Getters
  public String getSuit(){ return suit; }
  public String getName(){ return name; }
  public int getValue(){ return value; }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.card.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Card{
  <mark>//Attributes & Getters ...</mark><br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.card.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Card{
  //Attributes & Getters ...<br>
  public Card(String a_suit, int a_number){<br>
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.card.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Card{
  //Attributes & Getters ...<br>
  public Card(String a_suit, int a_number){
    this.suit = a_suit;
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.card.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Card{
  //Attributes & Getters ...<br>
  public Card(String a_suit, int a_number){
    this.suit = a_suit;
    this.name = a_number + "";
    this.value = a_number;
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.card.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Card{
  //Attributes & Getters ...<br>
  public Card(String a_suit, int a_number){
    this.suit = a_suit;
    <mark>this.name = a_number + "";
    this.value = a_number;</mark>
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.card.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Card{
  //Attributes & Getters ...<br>
  public Card(String a_suit, int a_number){
    this.suit = a_suit;
    if(){<br>
    }else{
      <mark>this.name = a_number + "";
      this.value = a_number;</mark>
    }
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.card.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Card{
  //Attributes & Getters ...<br>
  public Card(String a_suit, int a_number){
    this.suit = a_suit;
    if(<mark>a_number == 1</mark>){<br>
    }else{
      this.name = a_number + "";
      this.value = a_number;
    }
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.card.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Card{
  //Attributes & Getters ...<br>
  public Card(String a_suit, int a_number){
    this.suit = a_suit;
    if(a_number == 1){
      <mark>this.name = "Ace";
      this.value = 11;</mark>
    }else{
      this.name = a_number + "";
      this.value = a_number;
    }
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.card.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Card{
  //Attributes & Getters ...<br>
  public Card(String a_suit, int a_number){
    this.suit = a_suit;
    if(a_number == 1){
      this.name = "Ace";
      this.value = 11;
    <mark>}else if (a_number == 11){
      this.name = "Jack";
      this.value = 10;
    }else if (a_number == 12){
      this.name = "Queen";
      this.value = 10;
    }else if (a_number == 13){
      this.name = "King";
      this.value = 10;</mark>
    }else{
      this.name = a_number + "";
      this.value = a_number;
    }
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.card.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Card{
  //Attributes & Getters ...<br>
  public Card(String a_suit, int a_number){
    this.suit = a_suit;
    if(a_number == 1){
      this.name = "Ace";
      this.value = 11;
    }else if (a_number == 11){
      this.name = "Jack";
      this.value = 10;
    }else if (a_number == 12){
      this.name = "Queen";
      this.value = 10;
    }else if (a_number == 13){
      this.name = "King";
      this.value = 10;
    }else{
      this.name = a_number + "";
      this.value = a_number;
    }
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.card.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java"><mark>import java.lang.IllegalArgumentException;</mark><br>
public class Card{
  //Attributes & Getters ...<br>
  public Card(String a_suit, int a_number){
    <mark>if(!(a_suit.equals("Spades") || a_suit.equals("Hearts") ||
        a_suit.equals("Clubs") || a_suit.equals("Diamonds"))){
      throw new IllegalArgumentException("The suit must...");
    }
    if(a_number &lt; 1 || a_number > 13){
      throw new IllegalArgumentException("The card...");
    }</mark><br>
    this.suit = a_suit;
    if(a_number == 1){
      this.name = "Ace";
      this.value = 11;
    }else if (a_number == 11){
      this.name = "Jack";
      this.value = 10;
    }else if (a_number == 12){
      this.name = "Queen";
      this.value = 10;
    }else if (a_number == 13){
      this.name = "King";
      this.value = 10;
    }else{
      this.name = a_number + "";
      this.value = a_number;
    }
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.card.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">import java.lang.IllegalArgumentException;<br>
public class Card{
  //Attributes & Getters ...<br>
  public Card(String a_suit, int a_number){
    if(!(a_suit.equals("Spades") || a_suit.equals("Hearts") ||
        a_suit.equals("Clubs") || a_suit.equals("Diamonds"))){
      throw new IllegalArgumentException("The suit must...");
    }
    if(a_number &lt; 1 || a_number > 13){
      throw new IllegalArgumentException("The card...");
    }<br>
    this.suit = a_suit;
    if(a_number == 1){
      this.name = "Ace";
      this.value = 11;
    }else if (a_number == 11){
      this.name = "Jack";
      this.value = 10;
    }else if (a_number == 12){
      this.name = "Queen";
      this.value = 10;
    }else if (a_number == 13){
      this.name = "King";
      this.value = 10;
    }else{
      this.name = a_number + "";
      this.value = a_number;
    }
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.card.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">import java.lang.IllegalArgumentException;<br>
public class Card{
  //Attributes & Getters ...<br>
  public Card(String a_suit, int a_number){
    <mark>...</mark>
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.card.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">import java.lang.IllegalArgumentException;<br>
public class Card{
  //Attributes & Getters ...<br>
  public Card(String a_suit, int a_number){
    ...
  }
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.card.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">import java.lang.IllegalArgumentException;<br>
public class Card{
  //Attributes & Getters ...<br>
  public Card(String a_suit, int a_number){
    ...
  }<br>
  public String toString(){
    return this.name + " of " + this.suit;
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.card.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">import java.lang.IllegalArgumentException;<br>
public class Card{
  //Attributes & Getters ...<br>
  public Card(String a_suit, int a_number){
    ...
  }<br>
  <mark>@Override</mark>
  public String toString(){
    return this.name + " of " + this.suit;
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.card.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">import java.lang.IllegalArgumentException;<br>
public class Card{
  //Attributes & Getters ...<br>
  public Card(String a_suit, int a_number){
    ...
  }<br>
  @Override
  public String toString(){
    return this.name + " of " + this.suit;
  }
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <img class="stretch plain" src="/cc210/images/12-class/11.6.j.10.blackjack.png">
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.deck.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Deck{<br><br>
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.deck.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Deck{<br>
  <mark>private Card[] card_deck;</mark><br>
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.deck.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Deck{<br>
  private Card[] card_deck;<br>
  <mark>public Deck(){<br>
  }</mark><br>
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.deck.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Deck{<br>
  private Card[] card_deck;<br>
  public Deck(){
    <mark>this.card_deck = new Card[52];</mark>
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.deck.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Deck{<br>
  private Card[] card_deck;<br>
  public Deck(){
    this.card_deck = new Card[52];
    <mark>String[] suits = {"Spades", "Hearts", "Diamonds", "Clubs"};</mark>
    <mark>for(String suit : suits){<br>
    }</mark>
  }<br>
}</code></pre>
  </div>
</section><br><br><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.deck.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Deck{<br>
  private Card[] card_deck;<br>
  public Deck(){
    this.card_deck = new Card[52];
    String[] suits = {"Spades", "Hearts", "Diamonds", "Clubs"};
    for(String suit : suits){
      <mark>for(int i = 1; i <= 13; i++){
        this.card_deck[??] = new Card(suit, i);
      }</mark>
    }
  }<br>
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.deck.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Deck{<br>
  private Card[] card_deck;<br>
  public Deck(){
    this.card_deck = new Card[52];
    String[] suits = {"Spades", "Hearts", "Diamonds", "Clubs"};
    <mark>int card_number = 0;</mark>
    for(String suit : suits){
      for(int i = 1; i <= 13; i++){
        this.card_deck[<mark>card_number</mark>] = new Card(suit, i);
        <mark>card_number++;</mark>
      }
    }
  }<br>
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.deck.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Deck{<br>
  private Card[] card_deck;<br>
  public Deck(){
    this.card_deck = new Card[52];
    String[] suits = {"Spades", "Hearts", "Diamonds", "Clubs"};
    int card_number = 0;
    for(String suit : suits){
      for(int i = 1; i <= 13; i++){
        this.card_deck[card_number] = new Card(suit, i);
        card_number++;
      }
    }
  }<br>
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.deck.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Deck{<br>
  private Card[] card_deck;<br>
  public Deck(){
    this.card_deck = new Card[52];
    String[] suits = {"Spades", "Hearts", "Diamonds", "Clubs"};
    int card_number = 0;
    for(String suit : suits){
      for(int i = 1; i <= 13; i++){
        this.card_deck[card_number] = new Card(suit, i);
        card_number++;
      }
    }
  }<br>
  @Override
  public String toString(){
    String output = "";
    for(Card a_card : this.card_deck){
      output += a_card.toString() + "\n";
    }
    return output;
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <img class="stretch plain" src="/cc210/images/12-class/stop.png">
  <h3>Let's Test It!</h3>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%; opacity: 0" src="/cc210/images/12-class/11.6.j.10.java_ordered.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Deck a_deck = new Deck();
    System.out.println(a_deck.toString());
  }
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.java_ordered.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Deck a_deck = new Deck();
    System.out.println(a_deck.toString());
  }
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.deck.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Deck{<br>
  private Card[] card_deck;<br>
  public Deck(){...}
  @Override
  public String toString(){...}<br>
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.deck.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Deck{<br>
  private Card[] card_deck;<br>
  public Deck(){...}
  @Override
  public String toString(){...}<br>
  <mark>public void shuffle(int times){<br>
  }</mark><br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.deck.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Deck{<br>
  private Card[] card_deck;<br>
  public Deck(){...}
  @Override
  public String toString(){...}<br>
  public void shuffle(int times){
    <mark>for(int i = 0; i &lt; times; i++){<br>
    }</mark>
  }<br>
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.deck.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java"><mark>import java.util.Random;</mark><br>
public class Deck{<br>
  private Card[] card_deck;<br>
  public Deck(){...}
  @Override
  public String toString(){...}<br>
  public void shuffle(int times){
    <mark>Random rando = new Random();</mark>
    for(int i = 0; i &lt; times; i++){
      <mark>int first = rando.nextInt(52);
      int second = rando.nextInt(52);</mark>
    }
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.deck.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">import java.util.Random;<br>
public class Deck{<br>
  private Card[] card_deck;<br>
  public Deck(){...}
  @Override
  public String toString(){...}<br>
  public void shuffle(int times){
    Random rando = new Random();
    for(int i = 0; i &lt; times; i++){
      int first = rando.nextInt(52);
      int second = rando.nextInt(52);
      <mark>if(first != second){
        Card temp = this.card_deck[first];
        this.card_deck[first] = this.card_deck[second];
        this.card_deck[second] = temp;
      }</mark>
    }
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.deck.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">import java.util.Random;
<mark>import java.lang.IllegalArgumentException;</mark><br>
public class Deck{<br>
  private Card[] card_deck;<br>
  public Deck(){...}
  @Override
  public String toString(){...}<br>
  public void shuffle(int times){
    <mark>if(times <= 0){
      throw new IllegalArgumentException("The deck must ...");
    }</mark>
    Random rando = new Random();
    for(int i = 0; i &lt; times; i++){
      int first = rando.nextInt(52);
      int second = rando.nextInt(52);
      if(first != second){
        Card temp = this.card_deck[first];
        this.card_deck[first] = this.card_deck[second];
        this.card_deck[second] = temp;
      }
    }
  }<br>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.deck.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">import java.util.Random;
import java.lang.IllegalArgumentException;<br>
public class Deck{<br>
  private Card[] card_deck;<br>
  public Deck(){...}
  @Override
  public String toString(){...}<br>
  public void shuffle(int times){
    if(times <= 0){
      throw new IllegalArgumentException("The deck must ...");
    }
    Random rando = new Random();
    for(int i = 0; i &lt; times; i++){
      int first = rando.nextInt(52);
      int second = rando.nextInt(52);
      if(first != second){
        Card temp = this.card_deck[first];
        this.card_deck[first] = this.card_deck[second];
        this.card_deck[second] = temp;
      }
    }
  }<br>
}</code></pre>
  </div>
</section><br><br><br><br>
<section>
  <img class="stretch plain" src="/cc210/images/12-class/stop.png">
  <h3>Let's Test It!</h3>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%; opacity: 0" src="/cc210/images/12-class/11.6.j.10.java_shuffle.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Deck a_deck = new Deck();
    a_deck.shuffle(1000);
    System.out.println(a_deck.toString());
  }
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%;" src="/cc210/images/12-class/11.6.j.10.java_shuffle.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Deck a_deck = new Deck();
    a_deck.shuffle(1000);
    System.out.println(a_deck.toString());
  }
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.deck.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">import java.util.Random;
import java.lang.IllegalArgumentException;<br>
public class Deck{<br>
  private Card[] card_deck;<br>
  public Deck(){...}
  @Override
  public String toString(){...}
  public void shuffle(int times){...}<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.deck.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">import java.util.Random;
import java.lang.IllegalArgumentException;<br>
public class Deck{<br>
  private Card[] card_deck;<br>
  public Deck(){...}
  @Override
  public String toString(){...}
  public void shuffle(int times){...}<br>
  <mark>public Card draw(){<br>
  }</mark><br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.deck.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">import java.util.Random;
import java.lang.IllegalArgumentException;<br>
public class Deck{<br>
  private Card[] card_deck;<br>
  public Deck(){...}
  @Override
  public String toString(){...}
  public void shuffle(int times){...}<br>
  public Card draw(){
    <mark>Card output = this.card_deck[this.card_position];
    this.card_position++;
    return output;</mark>
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.deck.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">import java.util.Random;
import java.lang.IllegalArgumentException;<br>
public class Deck{<br>
  private Card[] card_deck;
  <mark>private int card_position;</mark><br>
  public Deck(){
    <mark>this.card_position = 0;</mark>
    ...
  }<br>
  @Override
  public String toString(){...}
  public void shuffle(int times){...}<br>
  public Card draw(){
    Card output = this.card_deck[this.card_position];
    this.card_position++;
    return output;
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.deck.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">import java.util.Random;
import java.lang.IllegalArgumentException;<br>
public class Deck{<br>
  private Card[] card_deck;
  private int card_position;<br>
  public Deck(){
    this.card_position = 0;
    ...
  }<br>
  @Override
  public String toString(){...}
  public void shuffle(int times){...}<br>
  public Card draw(){
    Card output = this.card_deck[this.card_position];
    this.card_position++;
    return output;
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <img class="stretch plain" src="/cc210/images/12-class/11.6.j.10.blackjack.png">
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.hand.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Hand{<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.hand.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Hand{<br>
  private Card[] card_hand;
  private int hand_size;<br>
  public Hand(){
    this.card_hand = new Card[52];
    this.hand_size = 0;
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.hand.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Hand{<br>
  private Card[] card_hand;
  private int hand_size;<br>
  public Hand(){
    this.card_hand = new Card[52];
    this.hand_size = 0;
  }<br>
  public int getValue(){
    int value = 0;
    for(int i = 0; i &lt; this.hand_size; i++){
      value += this.card_hand[i].getValue();
    }
    return value;
  }<br>
  @Override
  public String toString(){
    String output = "";
    for(int i = 0; i &lt; this.hand_size; i++){
      output += this.card_hand[i].toString() + "\n";
    }
    return output;
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.hand.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Hand{<br>
  private Card[] card_hand;
  private int hand_size;<br>
  public Hand(){
    this.card_hand = new Card[52];
    this.hand_size = 0;
  }<br>
  public int getValue(){
    int value = 0;
    for(int i = 0; i &lt; this.hand_size; i++){
      value += this.card_hand[i].getValue();
    }
    return value;
  }<br>
  @Override
  public String toString(){
    String output = "";
    for(int i = 0; i &lt; this.hand_size; i++){
      output += this.card_hand[i].toString() + "\n";
    }
    return output;
  }<br>
  public void addCard(Card input){
    this.card_hand[this.hand_size] = input;
    this.hand_size++;
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <img class="stretch plain" src="/cc210/images/12-class/11.6.j.10.blackjack.png">
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.dealer.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Dealer{<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.dealer.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Dealer{<br>
  private Hand my_hand;<br>
  public Dealer(Hand a_hand){
    this.my_hand = a_hand;
  }<br>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.dealer.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Dealer{<br>
  private Hand my_hand;<br>
  public Dealer(Hand a_hand){
    this.my_hand = a_hand;
  }<br>
  @Override
  public String toString(){
    String output = "The dealer currently holds: \n";
    output += this.my_hand.toString();
    output += "for a total of " + this.my_hand.getValue();
    return output;
  }<br>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.dealer.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Dealer{<br>
  private Hand my_hand;<br>
  public Dealer(Hand a_hand){ ... }
  @Override
  public String toString(){ ... }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.dealer.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Dealer{<br>
  private Hand my_hand;<br>
  public Dealer(Hand a_hand){ ... }
  @Override
  public String toString(){ ... }<br>
  public void makeMoves(int player_value){<br>
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.dealer.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Dealer{<br>
  private Hand my_hand;<br>
  public Dealer(Hand a_hand){ ... }
  @Override
  public String toString(){ ... }<br>
  public void makeMoves(int player_value){
    while(my_hand.getValue() &lt; player_value &&
                    my_hand.getValue() &lt;= 21){
      // we need to draw a card here!
    }
  }<br>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.dealer.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Dealer{<br>
  private Hand my_hand;<br>
  public Dealer(Hand a_hand){ ... }
  @Override
  public String toString(){ ... }<br>
  public void makeMoves(int player_value){
    while(my_hand.getValue() &lt; player_value &&
                    my_hand.getValue() &lt;= 21){
      // <mark>we need to draw a card here!</mark>
    }
  }<br>
}</code></pre>
  </div>
</section><br>
<section>
  <h3>Option 1: Make Deck Static</h3>
  <p><b>Pros:</b></p>
  <ul>
    <li>Requires few code changes</li>
    <li>Can use deck from anywhere</li>
  </ul>
  <p><b>Cons:</b></p>
  <ul>
    <li>Can only have one deck</li>
    <li>Not standard</li>
  </ul>
</section><br><br>
<section>
  <h3>Option 2: Pass Deck to Dealer</h3>
  <p><b>Pros:</b></p>
  <ul>
    <li>No modification to deck</li>
    <li>More object-oriented</li>
  </ul>
  <p><b>Cons:</b></p>
  <ul>
    <li>Have to manage deck instance</li>
    <li>Easy to lose objects in code</li>
  </ul>
</section><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.dealer.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Dealer{<br>
  private Hand my_hand;<br>
  public Dealer(Hand a_hand){ ... }
  @Override
  public String toString(){ ... }<br>
  public void makeMoves(int player_value){
    while(my_hand.getValue() &lt; player_value &&
                    my_hand.getValue() &lt;= 21){
      // we need to draw a card here!
    }
  }<br>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.dealer.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Dealer{<br>
  private Hand my_hand;
  <mark>private Deck the_deck;</mark><br>
  public Dealer(Hand a_hand, <mark>Deck a_deck</mark>){
    this.my_hand = a_hand;
    <mark>this.the_deck = a_deck;</mark>
  }<br>
  @Override
  public String toString(){ ... }<br>
  public void makeMoves(int player_value){
    while(my_hand.getValue() &lt; player_value &&
                    my_hand.getValue() &lt;= 21){
      // we need to draw a card here!
    }
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.dealer.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .31em"><code class="java">public class Dealer{<br>
  private Hand my_hand;
  private Deck the_deck;<br>
  public Dealer(Hand a_hand, Deck a_deck){
    this.my_hand = a_hand;
    this.the_deck = a_deck;
  }<br>
  @Override
  public String toString(){ ... }<br>
  public void makeMoves(int player_value){
    while(my_hand.getValue() &lt; player_value &&
                    my_hand.getValue() &lt;= 21){
      <mark>Card new_card = this.the_deck.draw();
      System.out.println("The dealer draws a " + new_card.toString());
      this.my_hand.addCard(new_card);</mark>
    }
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.dealer.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .31em"><code class="java">public class Dealer{<br>
  private Hand my_hand;
  private Deck the_deck;<br>
  public Dealer(Hand a_hand, Deck a_deck){
    this.my_hand = a_hand;
    this.the_deck = a_deck;
  }<br>
  @Override
  public String toString(){ ... }<br>
  public void makeMoves(int player_value){
    while(my_hand.getValue() &lt; player_value &&
                    my_hand.getValue() &lt;= 21){
      Card new_card = this.the_deck.draw();
      System.out.println("The dealer draws a " + new_card.toString());
      this.my_hand.addCard(new_card);
    }
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <img class="stretch plain" src="/cc210/images/12-class/11.6.j.10.blackjack.png">
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.player.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .31em"><code class="java">public class Dealer{<br>
  private Hand my_hand;
  private Deck the_deck;<br>
  public Dealer(Hand a_hand, Deck a_deck){
    this.my_hand = a_hand;
    this.the_deck = a_deck;
  }<br>
  @Override
  public String toString(){
    String output = "The dealer currently holds: \n";
    output += this.my_hand.toString();
    output += "for a total of " + this.my_hand.getValue();
    return output;
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.player.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .31em"><code class="java">public class <mark>Dealer</mark>{<br>
  private Hand my_hand;
  private Deck the_deck;<br>
  public <mark>Dealer</mark>(Hand a_hand, Deck a_deck){
    this.my_hand = a_hand;
    this.the_deck = a_deck;
  }<br>
  @Override
  public String toString(){
    String output = "The <mark>dealer</mark> currently holds: \n";
    output += this.my_hand.toString();
    output += "for a total of " + this.my_hand.getValue();
    return output;
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.player.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .31em"><code class="java">public class <mark>Player</mark>{<br>
  private Hand my_hand;
  private Deck the_deck;<br>
  public <mark>Player</mark>(Hand a_hand, Deck a_deck){
    this.my_hand = a_hand;
    this.the_deck = a_deck;
  }<br>
  @Override
  public String toString(){
    String output = "The <mark>player</mark> currently holds: \n";
    output += this.my_hand.toString();
    output += "for a total of " + this.my_hand.getValue();
    return output;
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.player.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .31em"><code class="java">public class Player{<br>
  private Hand my_hand;
  private Deck the_deck;<br>
  public Player(Hand a_hand, Deck a_deck){
    this.my_hand = a_hand;
    this.the_deck = a_deck;
  }<br>
  @Override
  public String toString(){
    String output = "The player currently holds: \n";
    output += this.my_hand.toString();
    output += "for a total of " + this.my_hand.getValue();
    return output;
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.player.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .31em"><code class="java">public class Player{<br>
  private Hand my_hand;
  private Deck the_deck;<br>
  public Player(Hand a_hand, Deck a_deck){ ... }
  @Override
  public String toString(){ ... }<br><br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.player.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .31em"><code class="java">public class Player{<br>
  private Hand my_hand;
  private Deck the_deck;<br>
  public Player(Hand a_hand, Deck a_deck){ ... }
  @Override
  public String toString(){ ... }<br>
  <mark>public void makeMoves(){<br>
  }</mark><br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.player.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .31em"><code class="java"><mark>import java.util.Scanner;</mark><br>
public class Player{<br>
  private Hand my_hand;
  private Deck the_deck;<br>
  public Player(Hand a_hand, Deck a_deck){ ... }
  @Override
  public String toString(){ ... }<br>
  public void makeMoves(){
    <mark>try(Scanner reader = new Scanner(System.in)){<br>
    }</mark>
  }<br>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.player.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .31em"><code class="java">import java.util.Scanner;<br>
public class Player{<br>
  private Hand my_hand;
  private Deck the_deck;<br>
  public Player(Hand a_hand, Deck a_deck){ ... }
  @Override
  public String toString(){ ... }<br>
  public void makeMoves(){
    try(Scanner reader = new Scanner(System.in)){
      <mark>while(my_hand.getValue() <= 21){<br>
      }</mark>
    }
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.player.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .31em"><code class="java">import java.util.Scanner;<br>
public class Player{<br>
  private Hand my_hand;
  private Deck the_deck;<br>
  public Player(Hand a_hand, Deck a_deck){ ... }
  @Override
  public String toString(){ ... }<br>
  public void makeMoves(){
    try(Scanner reader = new Scanner(System.in)){
      while(my_hand.getValue() <= 21){
        <mark>System.out.println("You currently have a value of " +
              this.my_hand.getValue());
        System.out.print("Would you like to draw
              another card (y/n)?: ");
        String input = reader.nextLine().trim();</mark>
      }
    }
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.player.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .31em"><code class="java">import java.util.Scanner;<br>
public class Player{<br>
  private Hand my_hand;
  private Deck the_deck;<br>
  public Player(Hand a_hand, Deck a_deck){ ... }
  @Override
  public String toString(){ ... }<br>
  public void makeMoves(){
    try(Scanner reader = new Scanner(System.in)){
      while(my_hand.getValue() <= 21){
        System.out.println("You currently have a value of " +
              this.my_hand.getValue());
        System.out.print("Would you like to draw
              another card (y/n)?: ");
        String input = reader.nextLine().trim();
        <mark>if(input.equals("y") || input.equals("Y")){
          Card new_card = this.the_deck.draw();
          System.out.println("You draw a " + new_card.toString());
          this.my_hand.addCard(new_card);
        }else if (input.equals("n") || input.equals("N")){
          break;
        }else{
          System.out.println("Invalid input!");
        }</mark>
      }
    }
  }<br>
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.player.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .31em"><code class="java">import java.util.Scanner;<br>
public class Player{<br>
  private Hand my_hand;
  private Deck the_deck;<br>
  public Player(Hand a_hand, Deck a_deck){ ... }
  @Override
  public String toString(){ ... }<br>
  public void makeMoves(){
    try(Scanner reader = new Scanner(System.in)){
      while(my_hand.getValue() <= 21){
        System.out.println("You currently have a value of " +
              this.my_hand.getValue());
        System.out.print("Would you like to draw
              another card (y/n)?: ");
        String input = reader.nextLine().trim();
        if(input.equals("y") || input.equals("Y")){
          Card new_card = this.the_deck.draw();
          System.out.println("You draw a " + new_card.toString());
          this.my_hand.addCard(new_card);
        }else if (input.equals("n") || input.equals("N")){
          break;
        }else{
          System.out.println("Invalid input!");
        }
      }
      <mark>System.out.println("You end your turn with a value of " +
            this.my_hand.getValue());</mark>
    }
  }<br>
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.player.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .31em"><code class="java">import java.util.Scanner;<br>
public class Player{<br>
  private Hand my_hand;
  private Deck the_deck;<br>
  public Player(Hand a_hand, Deck a_deck){ ... }
  @Override
  public String toString(){ ... }<br>
  public void makeMoves(){
    try(Scanner reader = new Scanner(System.in)){
      while(my_hand.getValue() <= 21){
        System.out.println("You currently have a value of " +
              this.my_hand.getValue());
        System.out.print("Would you like to draw
              another card (y/n)?: ");
        String input = reader.nextLine().trim();
        if(input.equals("y") || input.equals("Y")){
          Card new_card = this.the_deck.draw();
          System.out.println("You draw a " + new_card.toString());
          this.my_hand.addCard(new_card);
        }else if (input.equals("n") || input.equals("N")){
          break;
        }else{
          System.out.println("Invalid input!");
        }
      }
      System.out.println("You end your turn with a value of " +
            this.my_hand.getValue());
    }<mark>catch(Exception e){
      System.out.println("An exception occurred!\n" + e);
      return;
    }</mark>
  }<br>
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.10.blackjack.player.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .31em"><code class="java">import java.util.Scanner;<br>
public class Player{<br>
  private Hand my_hand;
  private Deck the_deck;<br>
  public Player(Hand a_hand, Deck a_deck){ ... }
  @Override
  public String toString(){ ... }<br>
  public void makeMoves(){
    try(Scanner reader = new Scanner(System.in)){
      while(my_hand.getValue() <= 21){
        System.out.println("You currently have a value of " +
              this.my_hand.getValue());
        System.out.print("Would you like to draw
              another card (y/n)?: ");
        String input = reader.nextLine().trim();
        if(input.equals("y") || input.equals("Y")){
          Card new_card = this.the_deck.draw();
          System.out.println("You draw a " + new_card.toString());
          this.my_hand.addCard(new_card);
        }else if (input.equals("n") || input.equals("N")){
          break;
        }else{
          System.out.println("Invalid input!");
        }
      }
      System.out.println("You end your turn with a value of " +
            this.my_hand.getValue());
    }catch(Exception e){
      System.out.println("An exception occurred!\n" + e);
      return;
    }
  }<br>
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <img class="stretch plain" src="/cc210/images/12-class/11.6.j.10.blackjack.png">
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Main{<br>
  public static void main(String[] args){<br>
  }
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    <mark>Deck the_deck = new Deck();</mark>
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Deck the_deck = new Deck();
    <mark>the_deck.shuffle(1000);</mark>
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Deck the_deck = new Deck();
    the_deck.shuffle(1000);
    <mark>Hand player_hand = new Hand();
    player_hand.addCard(the_deck.draw());
    player_hand.addCard(the_deck.draw());
    Player a_player = new Player(player_hand, the_deck);</mark>
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Deck the_deck = new Deck();
    the_deck.shuffle(1000);
    Hand player_hand = new Hand();
    player_hand.addCard(the_deck.draw());
    player_hand.addCard(the_deck.draw());
    Player a_player = new Player(player_hand, the_deck);
    <mark>Hand dealer_hand = new Hand();
    dealer_hand.addCard(the_deck.draw());
    dealer_hand.addCard(the_deck.draw());
    Dealer a_dealer = new Dealer(dealer_hand, the_deck);</mark>
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Deck the_deck = new Deck();
    the_deck.shuffle(1000);
    Hand player_hand = new Hand();
    player_hand.addCard(the_deck.draw());
    player_hand.addCard(the_deck.draw());
    Player a_player = new Player(player_hand, the_deck);
    Hand dealer_hand = new Hand();
    dealer_hand.addCard(the_deck.draw());
    dealer_hand.addCard(the_deck.draw());
    Dealer a_dealer = new Dealer(dealer_hand, the_deck);
    <mark>a_player.makeMoves();</mark>
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Deck the_deck = new Deck();
    the_deck.shuffle(1000);
    Hand player_hand = new Hand();
    player_hand.addCard(the_deck.draw());
    player_hand.addCard(the_deck.draw());
    Player a_player = new Player(player_hand, the_deck);
    Hand dealer_hand = new Hand();
    dealer_hand.addCard(the_deck.draw());
    dealer_hand.addCard(the_deck.draw());
    Dealer a_dealer = new Dealer(dealer_hand, the_deck);
    a_player.makeMoves();
    <mark>a_dealer.makeMoves(player_hand.getValue());</mark>
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Deck the_deck = new Deck();
    the_deck.shuffle(1000);
    Hand player_hand = new Hand();
    player_hand.addCard(the_deck.draw());
    player_hand.addCard(the_deck.draw());
    Player a_player = new Player(player_hand, the_deck);
    Hand dealer_hand = new Hand();
    dealer_hand.addCard(the_deck.draw());
    dealer_hand.addCard(the_deck.draw());
    Dealer a_dealer = new Dealer(dealer_hand, the_deck);
    a_player.makeMoves();
    a_dealer.makeMoves(player_hand.getValue());<br>
    <mark>if(player_hand.getValue() <= 21 && dealer_hand.getValue() > 21){
      System.out.println("The player wins!");
    }else if(player_hand.getValue() <= 21 && player_hand.getValue() > dealer_hand.getValue()){
      System.out.println("The player wins!");
    }else if(dealer_hand.getValue() <= 21){
      System.out.println("The dealer wins!");
    }else{
      System.out.println("There is no winner");
    }</mark>
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="width: 100%">
    <pre class="stretch" style="font-size: .33em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Deck the_deck = new Deck();
    the_deck.shuffle(1000);
    Hand player_hand = new Hand();
    player_hand.addCard(the_deck.draw());
    player_hand.addCard(the_deck.draw());
    Player a_player = new Player(player_hand, the_deck);
    Hand dealer_hand = new Hand();
    dealer_hand.addCard(the_deck.draw());
    dealer_hand.addCard(the_deck.draw());
    Dealer a_dealer = new Dealer(dealer_hand, the_deck);
    a_player.makeMoves();
    a_dealer.makeMoves(player_hand.getValue());<br>
    if(player_hand.getValue() <= 21 && dealer_hand.getValue() > 21){
      System.out.println("The player wins!");
    }else if(player_hand.getValue() <= 21 && player_hand.getValue() > dealer_hand.getValue()){
      System.out.println("The player wins!");
    }else if(dealer_hand.getValue() <= 21){
      System.out.println("The dealer wins!");
    }else{
      System.out.println("There is no winner");
    }
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <img class="stretch plain" src="/cc210/images/12-class/11.6.j.10.java_output.png">
</section><br>