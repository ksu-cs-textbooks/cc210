---
title: "A Worked Example"
pre: "10. "
weight: 100
---

Now that we've learned all about how to make our own classes and objects, we can practice our skills by building an example program together. This will be a larger program than many of the programs we've worked with so far, but hopefully it will actually be easier to follow since the code is separated into several classes. 

## Problem Statement

For this example, we'll build a program to play a version of the game of Blackjack, also known as Twenty-One. The rules of this simplified game are fairly straightforward:

1. The game consists of a single player playing against the dealer, played by our program in this example.
2. Each player is initially dealt two cards from a standard 52 card deck. Each card's value is its face value, with face cards valued 10 and aces valued 11. 
3. The object of the game is to get a higher total value than the other player, without going over 21. 
4. The game consists of several steps:
   1. Both the player and the dealer review the two cards they are dealt. Both the player and the dealer can see the opponent's hand as well.
   2. The player is given the option to draw additional cards. The player may continue to draw cards until she or he chooses to stop, or their total value is greater than 21.
   3. If the player stops before going over 21, the dealer must draw cards to try to beat the player. The dealer stops drawing cards when the dealer's total beats the player's or exceeds 21.
   4. At the end, the participant with the greatest card value that is less than or equal to 21 wins the game. If it is a tie, the dealer wins. 
As you may be able to tell, this game differs a bit from the rules of traditional Blackjack. Those changes mainly help to simplify the program a bit, so we can focus on the structure of the classes we need to build instead of on the rules. 

You can find the full rules to Blackjack on [Wikipedia](https://en.wikipedia.org/wiki/Blackjack).

## Program Structure

In order to build this program, we'll need to implement several classes to represent the objects needed for the game. For now, we'll follow this UML diagram to help guide the design of this program. In later chapters, you'll learn the skills needed to design your own program structures from scratch, but when learning to program it is sometimes easier first to read different program structures before writing your own. 

![Blackjack UML Diagram](/images/12-class/11.6.p.10.blackjack.png)

This program will contain several classes:
* Card—This class represents a single card in a deck, containing a suit and a value. 
* Deck—This class represents the entire deck of cards, consisting of 52 cards. 
* Hand—This class represents a single player's hand of cards from the deck. 
* Dealer—This class implements the dealer's actions.
* Player—This class implements the player's actions.
* Main—This class controls the program and contains the `main()` function.

To build this program, we'll address each class individually, allowing us to build the program one piece at a time and test it at each step to make sure it works correctly. 

## `Card` Class

{{% youtube 1BvB6WXtsPs %}}

[Video Materials]({{<relref "./video">}})

The first and simplest class we can build is the `Card` class. This class represents a single card from a deck of cards, and contains the `suit`, `name`, and `value` attributes. Since we don't want those values to be edited outside of this class, we can use private attributes paired with getter methods for them. For the value, we'll use an integer to make the rest of the program simpler. We'll also need to create a simple constructor for this class. It can accept a suit and a card number as input, and then populate the attributes as needed:

```python
class Card:
  
  def __init__(self, a_suit, a_number):
    self.__suit = a_suit
    if a_number == 1:
      self.__name = "Ace"
      self.__value = 11
    elif a_number == 11:
      self.__name = "Jack"
      self.__value = 10
    elif a_number == 12:
      self.__name = "Queen"
      self.__value = 10
    elif a_number == 13:
      self.__name = "King"
      self.__value = 10
    else:
      self.__name = str(a_number)
      self.__value = a_number

  @property
  def suit(self):
    return self.__suit
    
  @property
  def name(self):
    return self.__name
    
  @property
  def value(self):
    return self.__value

```

Finally, we can add some additional code to our constructor to validate the supplied parameter arguments, just to avoid any unforeseen errors. In this case, we'll make sure that the suits and numbers provided are all valid values:

```python
class Card:
  
  def __init__(self, a_suit, a_number):
    if not (a_suit == "Spades" or a_suit == "Hearts" or a_suit == "Clubs" or a_suit == "Diamonds"):
     raise ValueError("The suit must be one of Spades, Hearts, Clubs, or Diamonds")
    if a_number < 1 or a_number > 13:
      raise ValueError("The card number must be an integer between 1 and 13, inclusive")
    self.__suit = a_suit
    if a_number == 1:
      self.__name = "Ace"
      self.__value = 11
    elif a_number == 11:
      self.__name = "Jack"
      self.__value = 10
    elif a_number == 12:
      self.__name = "Queen"
      self.__value = 10
    elif a_number == 13:
      self.__name = "King"
      self.__value = 10
    else:
      self.__name = str(a_number)
      self.__value = a_number

  @property
  def suit(self):
    return self.__suit
    
  @property
  def name(self):
    return self.__name
    
  @property
  def value(self):
    return self.__value

```

To do this, we've added a couple of **If-Then** statements to the constructor that can raise Exceptions if the inputs are invalid. 

Finally, to make debugging our programs very simple, we'll add a special method, `__str__()` to this class. The `__str__()` method is actually a part of every class in Python because of _inheritance_, something we'll learn more about in a later chapter. For now, we can add that method as shown below:

```python
class Card:
  
  # other code omitted here #
  
  def __str__(self):
    return "{} of {}".format(self.__name, self.__suit)
```

Later, when we try to print a `Card` class, Python will automatically call the `__str__()` method behind the scenes to convert the `Card` class to a String that can be easily understood by our users. 

That should complete the `Card` class! The assessments below will confirm that the code structure and functionality is correct before moving on.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

## `Deck` Class

{{% youtube HNScQCCW95I %}}

[Video Materials]({{<relref "./video">}})

Next, we'll need a class that can represent an entire deck of cards. This class will contain a list of cards, as well as some helpful methods we can use to shuffle the deck and deal individual cards. 

In this class, we won't include any getters or setters for the deck of cards itself because our program shouldn't be able to change the deck in any way. In the constructor, however, we'll include the code to create our deck of cards:

```python
from Card import *

class Deck:
  
  def __init__(self):
    self.__card_deck = []
    suits = ["Spades", "Hearts", "Diamonds", "Clubs"]
    for suit in suits:
      for i in range(1, 14):
        self.__card_deck.append(Card(suit, i))
```

Hopefully that code is pretty straightforward. It creates an empty list that will later contain the cards, then a list of strings representing the suits. Finally, we have two **For** loops to go through each suit and each card number from 1 to 13, creating the full deck of 52 cards. 

Next, we can add a method to print out the entire deck of cards. Once again, we'll just use the `__str__()` method:

```python
from Card import *

class Deck:
  
  def __init__(self):
    self.__card_deck = []
    suits = ["Spades", "Hearts", "Diamonds", "Clubs"]
    for suit in suits:
      for i in range(1, 14):
        self.__card_deck.append(Card(suit, i))

  def __str__(self):
    output = ""
    for a_card in self.__card_deck:
      output += str(a_card) + "\n"
    return output
```

At this point, let's test it out! That's one of the most important steps in writing programs like this one—we'll want to test each little bit of the program and see how it works. 

So, we can add the following code to our `Main` class for testing:

```python
from Deck import *

class Main:

  @staticmethod
  def main():
    a_deck = Deck()
    print(a_deck)
    
if __name__ == "__main__":
  Main.main()
```

Then, we can run that code using these commands in [Terminal](open_terminal):

```sh
cd 11p-classes/example
python3 Main.py
```

When we run those commands, we should see output similar to this:

![Terminal Output with Ordered List of Cards](/images/12-class/11.6.p.10.python_ordered.png)

As we can see, we are creating a full deck of cards, but they aren't in a random order. While we could just implement a method to draw cards randomly from the deck, it might be just as useful to implement a method to shuffle the deck. So, let's do that now!

```python
import random
from Card import *

class Deck:
  
  # other methods omitted here #
  
  def shuffle(self, times):
    if times <= 0:
      raise ValueError("The deck must be shuffled a positive number of times")
    for i in range(0, times):
      first = random.randint(0, 51)   # get a number [0...51]
      second = random.randint(0, 51)  # get a number [0...51]
      if first != second:  # swap first and second cards
        temp = self.__card_deck[first]
        self.__card_deck[first] = self.__card_deck[second]
        self.__card_deck[second] = temp
```

This is a very simple shuffle method, which simply gets two random numbers using the [`random`](https://docs.python.org/3/library/random.html) library. Then, it will swap the cards in the deck at those two locations. It is slow and simple, but thankfully a computer can do thousands of those operations in a few milliseconds, so it works just fine for our needs. 

Now, we can update the code in our `main()` function to see that it is working correctly:

```python
from Deck import *

class Main:

  @staticmethod
  def main():
    a_deck = Deck()
    a_deck.shuffle(1000)
    print(a_deck)
    
if __name__ == "__main__":
  Main.main()
```

That should produce a random deck, as shown in this screenshot:

![Terminal Output with Shuffled List of Cards](/images/12-class/11.6.p.10.python_shuffle.png)

Finally, we can add a method to deal a card from the deck to a player. To do this, we'll add another private attribute to keep track of the position we are dealing from in the deck. Then, we can return the appropriate card from our method.

```python
import random
from Card import *

class Deck:
  
  # other methods omitted here #
  
  def __init__(self):
    self.__card_position = 0
    # other constructor code omitted here #
    
  def draw(self):
    output = self.__card_deck[self.__card_position]
    self.__card_position += 1
    return output

```

There we go! This method will simply return the front-most card from the deck that hasn't already been used. We aren't actually removing the cards from the list, but rather just incrementing a variable keeping track of the position in the list to remember which cards we've already dealt. 

That should complete the `Deck` class! The assessments below will confirm that the code structure and functionality is correct before moving on.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

## `Hand` Class

{{% youtube 0LhqgPjLWfY %}}

[Video Materials]({{<relref "./video">}})

Next, we can create a simple class that represents a hand of cards. So, it will need a list of Card objects just like the `Deck` class. 

To start, we can create our list of cards in the constructor, as well as an integer to keep track of how many cards we have in our hand:

```python
from Card import *

class Hand:
  
  def __init__(self):
    self.__card_hand = []
```

Then, we can also create a `value()` method to return the value in our hand, as well as a `__str__()` method to print out the contents of our hand:

```python
from Card import *

class Hand:
  
  def __init__(self):
    self.__card_hand = []
    
  @property
  def value(self):
    value = 0
    for card in self.__card_hand:
      value += card.value
    return value
  
  def __str__(self):
    output = ""
    for card in self.__card_hand:
      output += str(card) + "\n"
    return output
```

These methods are very similar to each other. In essence, we use a **For Each** loop to loop through the cards in our hand, and then either sum up the values or get the string representation of each card. 

Lastly, we need to create a method that allows us to add a card to our hand. So, we can implement the `addCard()` method as well:

```python
from Card import *

class Hand:
  
  # other methods omitted here #
  
  def add_card(self, input):
    if not isinstance(input, Card):
      raise ValueError("Input must be a Card object")
    self.__card_hand.append(input)
```

That should do it for the `Hand` class. The assessments below will confirm that the code structure and functionality is correct before moving on.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

## `Dealer` Class

{{% youtube Wbh038JMM4M %}}

[Video Materials]({{<relref "./video">}})

Now that we have implemented the classes needed to keep track of the cards, we can create the classes that will actually perform the actions for each player. First, we can implement the code for the `Dealer` class. This class is actually pretty simple, since it will only consist of a couple of methods: `make_moves()`, which will perform all the actions needed for the dealer, and a `__str__()` method to print the contents of the dealer's hand. In addition, the dealer will need an attribute to store a hand, which can be populated in the constructor by a parameter:

```python
from Hand import *

class Dealer:
  
  def __init__(self, a_hand):
    if not isinstance(a_hand, Hand):
      raise ValueError("A_hand must be a Hand object")
    self.__my_hand = a_hand
    
  def make_moves(self, player_value):
    while self.__my_hand.value < player_value and self.__my_hand.value <= 21:
      # we need to draw a card here!
  
  def __str__(self):
    output = "The dealer currently holds: \n"
    output += str(self.__my_hand)
    output += "for a total of {}".format(self.__my_hand.value)
    return output
```

At this point, we notice a flaw in our design! The `Dealer` class needs to be able to draw a card from the deck, but we've provided no way for it to do so. In addition, we'll need to do the same thing for our `Player` class as well. So, how can we accomplish this?

### Option 1: Make `Deck` Static

One way we can accomplish this is to make the methods in our Deck class `static`. In this way, we can access them from anywhere in the program, even without having access to a `Deck` object. For this, we'd modify our `Deck` class to look similar to this:

```python
import random
from Card import *

class Deck:
  __card_deck = []
  __card_position = 0
  
  # __init__ changed to init
  @staticmethod
  def init():
    suits = ["Spades", "Hearts", "Diamonds", "Clubs"]
    for suit in suits:
      for i in range(1, 14):
        Deck.__card_deck.append(Card(suit, i))
  
  @staticmethod
  def draw():
    output = Deck.__card_deck[Deck.__card_position]
    Deck.__card_position += 1
    return output

  @staticmethod
  def shuffle(times):
    if times <= 0:
      raise ValueError("The deck must be shuffled a positive number o times")
    for i in range(0, times):
      first = random.randint(0, 51)   # get a number [0...51]
      second = random.randint(0, 51)  # get a number [0...51]
      if first != second:  # swap first and second cards
        temp = Deck.__card_deck[first]
        Deck.__card_deck[first] = Deck.__card_deck[second]
        Deck.__card_deck[second] = temp
  
  # __str__ changed to str
  @staticmethod
  def str():
    output = ""
    for a_card in Deck.__card_deck:
      output += str(a_card) + "\n"
    return output
```

In the code above, all of the methods and instance attributes are now static. In addition, the constructor was renamed to `init()` since we won't actually be using the constructor to build an object. Finally, we also have to rename the `__str__()` method to `str()` since the `__str__()` method cannot be static. We'll see why that would be a problem in a later chapter as we learn about method inheritance. 

Then, once we've made that choice, we can draw a new card from the deck in our code anywhere simply by using the `Deck.draw()` method. 

This approach has several advantages and disadvantages. It requires very few changes in our code, and once the `Deck` class is modified, we can use the methods from that class anywhere in our code, which can be very helpful. 

Unfortunately, the major downside of this approach is that we can now only have a single deck of cards in our entire game. For most games, that won't be an issue, but it could be a limitation in other programs. In addition, as we may learn in a later class, there are some standard ways to accomplish this, such as the _singleton design pattern_, that are more familiar to developers. 

So, for this example, we won't be using a `Deck` class that contains entirely static methods and attributes. 

### Option 2: Pass `Deck` Object to `Dealer` Class

The second way this could be handled is to create an object from the `Deck` class in our `Main` class, then pass that object as a parameter to the constructor for the `Dealer` object. In that way, the dealer has a _reference_ to the deck that is stored in our main class (recall that all objects are handled in a _call by reference_ manner). 

<!--- Well, not really…the dealer has a reference to a deck stored somewhere in memory,
      and the main class also has a reference thereto…and, as I understand it, the address
      of that deck is passed (by value) from the main class to the constructor of Dealer,
      which is how they have a reference to the same thing. --->

So, we can update the constructor for our `Dealer` class to accept a `Deck` object, and then we'll store it as a private variable in the class:

```python
from Hand import *
from Deck import *

class Dealer:
  
  def __init__(self, a_hand, a_deck):
    if not isinstance(a_hand, Hand):
      raise ValueError("A_hand must be a Hand object")
    if not isinstance(a_deck, Deck):
      raise ValueError("A_deck must be a Hand object")
    self.__my_hand = a_hand
    self.__the_deck = a_deck
    
  def make_moves(self, player_value):
    while self.__my_hand.value < player_value and self.__my_hand.value <= 21:
      new_card = self.__the_deck.draw()
      print("The dealer draws a {}".format(str(new_card)))
      self.__my_hand.add_card(new_card)
  
  def __str__(self):
    output = "The dealer currently holds: \n"
    output += str(self.__my_hand)
    output += "for a total of {}".format(self.__my_hand.value)
    return output
```

Then we can place this code in our `Main` class:

```python
from Deck import *
from Hand import *
from Dealer import *

class Main:

  @staticmethod
  def main():
    the_deck = Deck()
    the_deck.shuffle(1000)
    dealer_hand = Hand()
    dealer_hand.add_card(the_deck.draw())
    dealer_hand.add_card(the_deck.draw())
    a_dealer = Dealer(dealer_hand, the_deck)
    
if __name__ == "__main__":
  Main.main()
```

With this code, we are instantiating a single `Deck` object in our `Main` class, then passing it as a reference to the `Dealer` class when we instantiate it. This gives the `Dealer` class a reference to the deck that we are using, allowing it to draw cards as needed. 

This approach also has several pros and cons. First, we don't have to modify our Deck class at all, meaning that it can remain a simple object. Instead, we are modifying how we use it by including a reference to it in our other classes. This is a more standard approach for programs written in an object-oriented style, in Python and other languages. 

As a downside, this does mean that we'll have to make sure our other classes all are given a reference to a `Deck` object. In larger programs, handling all of these object references can become very cumbersome and time-consuming. Again, in a future course we can learn about _design patterns_ that help simplify this process, too. 

We'll use this approach in our example program here. 

That should complete the `Dealer` class! The assessments below will confirm that the code structure and functionality is correct before moving on.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

## `Player` Class

{{% youtube T5vEsLUytec %}}

[Video Materials]({{<relref "./video">}})

The player class is nearly identical to the `Dealer` class. The only difference is that the player class will ask the player to decide whether to draw more cards. In addition, the player may draw until their value is greater than 21, without regard to the score from the dealer. This is the one interactive part of the entire program:

```python
import sys
from Hand import *
from Deck import *

class Player:
  
  def __init__(self, a_hand, a_deck):
    if not isinstance(a_hand, Hand):
      raise ValueError("A_hand must be a Hand object")
    if not isinstance(a_deck, Deck):
      raise ValueError("A_deck must be a Hand object")
    self.__my_hand = a_hand
    self.__the_deck = a_deck
    
  def make_moves(self):
    with sys.stdin as reader:
      while self.__my_hand.value <= 21:
        print("You currently have a value of {}".format(self.__my_hand.value))
        print("Would you like to draw another card (y/n)?: ")
        input = reader.readline().strip()
        if input == "y" or input == "Y":
          new_card = self.__the_deck.draw()
          print("The dealer draws a {}".format(str(new_card)))
          self.__my_hand.add_card(new_card)
        elif input == "n" or input == "N":
          break;
        else:
          print("Invalid input!")
      print("You end your turn with a value of {}".format(self.__my_hand.value))
  
  def __str__(self):
    output = "The player currently holds: \n"
    output += str(self.__my_hand)
    output += "for a total of {}".format(self.__my_hand.value)
    return output
```

As we can see in the `make_moves()` method, we've simply added the code to create a `reader` object to handle user input. Then, we can ask the user at each step whether they would like to draw another card. 

That should complete the `Player` class! The assessments below will confirm that the code structure is correct before moving on. We won't worry about testing the functionality here, since that is really best done by a live player!

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

## `Main` Class

{{% youtube jrze2n2etRY %}}

[Video Materials]({{<relref "./video">}})

Finally, we can work on implementing our `Main` class. This class is very simple, only containing the `main()` method for the program. The `main` method will set up the deck and deal a hand for each player, then allow both the player and the dealer to make moves before finally getting the result to see who wins:

```python
from Deck import *
from Hand import *
from Dealer import *
from Player import *

class Main:

  @staticmethod
  def main():
    the_deck = Deck()
    
    print("Shuffling the deck...")
    the_deck.shuffle(1000)
    
    print("Dealing the player's hand...")
    player_hand = Hand()
    player_hand.add_card(the_deck.draw())
    player_hand.add_card(the_deck.draw())
    a_player = Player(player_hand, the_deck)
    print(a_player)
    
    print("Dealing the dealer's hand...")
    dealer_hand = Hand()
    dealer_hand.add_card(the_deck.draw())
    dealer_hand.add_card(the_deck.draw())
    a_dealer = Dealer(dealer_hand, the_deck)
    print(a_dealer)
    
    print("Starting player's turn...")
    a_player.make_moves()
    print(a_player)
    
    print("Starting dealer's turn...")
    a_dealer.make_moves(player_hand.value)
    print(a_dealer)
    
    if player_hand.value <= 21 and dealer_hand.value > 21:
      print("The player wins!")
    elif player_hand.value <= 21 and player_hand.value > dealer_hand.value:
      print("The player wins!")
    elif dealer_hand.value <= 21:
      print("The dealer wins!")
    else:
      print("There is no winner")
    
if __name__ == "__main__":
  Main.main()
```

Looking at this code, we see that the main method consists of several steps:
1. First, the deck is initialized and shuffled.
2. Then, the player's hand is dealt, and the `Player` object is initialized. Once that is done, it prints the contents of the player's hand.
3. Similarly, the `Dealer` is initialized and given a hand, the contents of which are printed. 
4. Then, it proceeds to the player's turn, on which the player can draw cards until he chooses to stop or go over the value of 21.
5. Next, the dealer is given a turn. The dealer is also given the value of the player's hand, so the dealer only has to match or beat the player's value to win.
6. Finally, the game determines the winner. 

Here is a sample of this program's output when run in the terminal:

![Python Program Output](/images/12-class/11.6.p.10.python_output.png)

There we go! We were able to build a program that plays a simple version of Blackjack. While it took a bit of work to get all of the required classes developed, each one was pretty straightforward and easy to use. Then, in our `main()` method, we simply had to pull all those resources together into a working program. 

That's one of the major benefits of the object-oriented programming paradigm. Once the program can be expressed by the objects and interactions required, the bulk of the actual logic code is simply the process of building and manipulating those objects in a way that feels very similar to how it would be done in the real world. 

The assessments below will verify that the entire example program works as intended, except for the `Main` and `Player` classes. This is because it can be very difficult to complete those classes in a way that is easy to test automatically. They exist mainly to allow us to interact with the objects we've created. 

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}
