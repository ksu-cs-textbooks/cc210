---
title: "Python Example"
pre: "10.P. "
weight: 101
hidden: true
date: 2019-09-24T00:00:26-05:00
---

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

{{< youtube 1BvB6WXtsPs >}}

Now that we've learned all about creating our own classes in our programs, let's work through an example program together to see how we can build a much more complex program using multiple classes.

As always, we'll start with a problem statement. Here it is!

As you might expect, it's pretty complex. We're basically going to write a version of the traditional card game Blackjack, also known as 21. Sounds like it could be quite a bit of work, right?

However, in this chapter, we learned how to develop our own classes! So, we can take this large and complex problem statement, and break it down into a number of individual classes, each with their own methods and attributes. That should make this much simpler to follow.

As a helpful guide, we are provided with this UML class diagram that gives the structure for each class we'll need to create. Since we are just learning how to program, building examples based on diagrams we are given is a great way to learn some good design habits first, before we start trying to build our own structures. In addition, by following this diagram, we are able to use the automated grading system built into these Codio lessons to automatically check the structure and functionality of our code.

So, looking at this UML diagram, we have to decide where to start. Typically, we want to start in a class that doesn't require any other classes as data types. That means that classes such as Deck, Hand, and Dealer aren't good choices to start, since each of them require another class to exist first. However, we might notice that the Card class just uses primitive data types as attributes, so it is probably the best place to start.

So, let's start by building the Card class. First, we notice that it contains 3 private attributes, `suit`, `name` and `value`. It also has getters for each one, so we can add those pretty easily as properties first. We'll define the attributes in the constructor itself, which we'll write shortly.

We'll hide those properties for now, just to give us a bit more room to work. Next, let's address the constructor. It accepts a suit as a string, and a card number as an integer. So, a simple constructor might just store the suit, and use the card number to fill in both the name and the value, right? However, we want our program to be a bit more robust and deal with cards such as the ace, king, queen, and jack as well. So, we can add some If-Then statements to determine if the card number represents one of those cards, and update the name to match. Likewise, the value of each of the face cards is only 10, so we'll update those values too.

Finally, we should probably add some code to our constructor to make sure we aren't accepting any invalid values. So, we'll insert a couple of If-Then statements that check each parameter, and throw a ValueError if they aren't valid. We'll also need to remember to import that library at the top of the file, too.

There we go! That is all we need for the constructor. Finally, we can address one other special method in this class, the `__str__()` method. Every object in Python includes a `__str__()` method, which is meant to print a string representation of this class. By default, it will just print the structure of the object, but we can override it with some different code. So, let's create a method named `__str__()` that returns the name and the suit of this card as a string.

That's it for the Card class. We'll look at the other classes in later videos.

---

{{< youtube HNScQCCW95I >}}

Now that we have written the Card class, we can look at our UML diagram to find the class that only references the Card class in its attributes. It looks like the Deck and Hand classes both fit. But, since we know that a deck is made up of all of the cards in the game, it probably makes sense to start there next.

So, let's build our Deck class. We'll start with the class declaration, and above that we'll need to import the items from our Card class.

In the constructor, all we have to do is generate all possible cards in the deck, and store them in the `card_deck` private attribute. So, we'll start by initializing an empty list. Next, we'll build a small list of the 4 different suits, Spades, Hearts, Diamonds, and Clubs, and then use a for each loop to iterate over each of the suits.

Inside of that for each loop, we'll need to create 13 cards in each suit. So, we'll use another for loop to do that, iterating from 1 through 13 instead of 0 through 12. Inside of that loop, we'll append the card created to the list of cards that make up the deck.

There we go! That should be everything we need to build the constructor for the Deck class. Next, we'll add a `__str__()` method to return a string representation of all of the cards in the deck. That method is pretty simple - we'll just iterate across each of the cards in the deck, adding each of them to the string on a separate line.

Ok, at this point, we should have enough code written that we can stop and test our code to see how it runs. So, let's do that now.

In the `main()` method inside of the Main class, we'll add a few lines of code to create a deck object, and then print the string representation of the deck to the terminal. Let's run this code and see what we get.

It looks like we are getting the correct output, since we see every card in every suit listed. However, we should notice that these cards are all printed in order. That makes sense, since we are adding them to the deck in that order. In most games, however, we need to have a shuffled deck. So, let's go back to our deck class and add a method to shuffle the cards.

There are many ways to shuffle a deck of cards. However, one of the simplest ways is to simply swap the position of two randomly chosen cards in the deck, and repeat that process many times. So, our `shuffle()` method will accept a number of times to swap cards as a parameter. Inside of the method, we'll use a for loop to repeat the process the given number of times.

Inside of that loop, we'll need to choose 2 random cards. The easiest way to do that in Python is using the random library. So, we'll need to import it at the top of the file. Then, in the for loop, we can use the `random.randint()` method to get an integer starting at the first parameter provided, and up to but not including the number provided as the second parameter. So, this function call will return a random number between 0 and 51, inclusive, which will exactly match the list indices of our list of cards.

Then, once we have two indices selected, we simply must swap them. We'll add a simple If-Then statement to make sure they aren't the same. As long as they aren't, we'll do the standard three-line swap process, using a temporary variable as well. This should be pretty straight forward.

Finally, we want to make sure the deck is shuffled a positive number of times. So, we can add an If-Then statement to the top of the method that makes sure the parameter is greater than 0. If not, it will throw an ValueError. As always, we'll need to import that library as well.

Once again, we're at a good point to stop and test our code. So, let's go back to the Main class and update the `main()` method to shuffle the deck.

That can be done by adding a call to the `shuffle()` method before printing the deck. We'll tell our method to perform 1000 swaps, which should be enough to get a pretty randomly shuffled deck. When we run this program, we'll see that the deck is indeed shuffled, just like we want. That's great!

Finally, we need to add one more method to our Deck class which will allow a user to draw a card from the deck. So, we'll create a method called `draw()` that returns a single card. To make it simple, we can just return a card from the deck, but we'll need to keep track of the card that should be returned. That is where the `card_position` attribute comes in. In this draw method, we'll just return the card at that position, and then increment the position by 1.

Of course, now we'll need to add the `card_position` attribute to the class by initializing it to a value of 0 in the constructor. So, we'll need to add that line of code to the appropriate place.

That's all there is to it! However, if we look closely at this method, we might notice that it could cause an error when we run out of cards. For now, we won't worry about this, since a single game of Blackjack cannot possibly use all of the cards in the deck. However, if we choose to reuse this code for another program, we'll have to update this method to deal with that scenario.

Next, we'll look at how we can deal cards to a single player's hand.

---

{{< youtube 0LhqgPjLWfY >}}

Now that we've built the code to handle a deck of cards, we need to look at how we can represent a hand of cards for each player. A "hand" refers to the cards dealt to a particular player. So, let's look at how we can build the Hand class in our application.

Once again, we'll need to remember to import from the Card class. Looking at the UML diagram, we see that there is a single private attribute, a list of cards. So, we'll create an empty list in the constructor for this class.

We can also add two simple methods. The first is the `value()` method, which simply iterates through all of the cards in the hand and adds up the values of each card. Notice that we are declaring this method as a property, since it makes sense to think of the total value of a hand as a property instead of a method.

Similarly, we can create a `__str__()` method that creates a string representation of the cards in the hand. This is very similar to what we did in the Deck class.

The last method we need to create is the `addCard()` method. This method will simply accept a card as input, and then add it to the array of cards. We'll need to make sure that the object we are given is a card, otherwise we can raise a ValueError. If it is a card, we can just append it to our list of cards.

That's it! The hand class is actually pretty simple, and is a great example of a "data structure" class that stores data and provides useful information about that data. If you continue to study programming, you'll learn all about how to write your own data structures like this one.

---

{{< youtube Wbh038JMM4M >}}

Now that we've written the code for the classes that deal with cards, the last two classes we need to focus on are the Player and Dealer classes. Let's look at the dealer first.

We'll start by adding the code to handle the dealer's hand of cards. So, we'll create a private attribute, and in the constructor we'll accept a Hand as input and store it in that attribute. We should also carefully check to make sure the parameter provided is indeed a Hand object, and throw a ValueError if not.

We can also easily create a `__str__()` method, outputting the cards in the dealer's hand as well as the total value as an easy to read string that we can use later in our program.

Now, we need to deal with the most important part of the Dealer class - the actual AI algorithm that determines how the dealer should play the game. We'll do this in the `make_moves()` method.

First, since the dealer is able to know how many points the player has, we'll accept that value as a single parameter on this method.

Inside of the method, we can follow the rules of the program to determine how the dealer plays. In this If statement, the dealer will continue to draw cards until they have either beat the player's value, or they have a hand value that is greater than 21.

Uh oh! At this point we hit a snag, because we need to be able to draw a card here. However, we don't have a variable for the Deck class in our Dealer class, so we'll have to change something to make it happen.

There are a couple of ways that we could do this. One option would be to convert the Deck class to primarily contain static methods and attributes. In this case, we don't have to make many changes to our code to make it work, and once we do make those changes, we'll be able to use the Deck class anywhere, even without instantiating an object from it.

However, if we do this, we can only have one deck of cards in our program. While that isn't a problem for this program, it may be a problem if we want to adapt this code for another use. In addition, making a class like that completely static is not the standard, object-oriented way of handling this issue. As it turns out, there is a better way.

The other way would be to instantiate a Deck object in the `main()` method, and then pass that object to the Dealer class. Since objects are passed using call by reference, they'll refer to the same deck of cards, even though the class isn't static. Of course, we'll have to be careful about how we manage that deck, since it can be easily lost in our code. This is a much more object-oriented way of solving this problem. So, let's do this and see how our code in the Dealer class would change.

First, we'll need to need to update the constructor to accept a second parameter that contains the deck, and we'll store that parameter in a private attribute named `the_deck`. As always, we'll also need to check and make sure that the object provided is the correct type, and raise a ValueError if not.

Now, once we've done that, we can simply use the `draw()` method of that deck object to draw a new card where we need it. Once we do, we can add that card to our hand, and continue the program until we've either beaten the player or gone over 21. In either case, the While loop will end.

There we go! That completes the Dealer class. Just 2 more to go!

---

{{< youtube T5vEsLUytec >}}

Now we can work on the Player class. If we look at the Player and Dealer classes, we'll see that they are actually very similar. So similar in fact, that we can just copy the code from the Dealer class and just make a few changes to it.

First, we'll need to change the references to the Dealer class to Player instead. Then, we'll need to rewrite the `make_moves()` method to make sense for the player, since it should accept input from the player.

So, we'll need to create a reader object to read input inside of a with statement like we always do.

Then, inside of that statement, we can write a While loop that will repeat until the user's hand value is greater than 21.

Inside of the loop, we'll display the user's current hand value, and then ask the user if they'd like to draw a card.

If the user responds yes, we'll use the `draw()` method to add a card to the hand.

If not, we'll just break out of the loop.

Also, if the user inputs something we don't recognize, we'll just print an error and repeat the prompt.

Finally, outside the loop, we can print a message telling the user what their final hand value is.

Overall, this is a very simple method that allows the user to interact with the program and make moves, drawing cards until they are satisfied or their hand value becomes too large.

There we go! That's all we need to complete the classes used by this program. The last class to write is the Main class, which simply includes a main method that runs the program. We'll cover that in the final video in this series.

---

{{< youtube jrze2n2etRY >}}

The last part of this program is to build the `main()` method itself. As we saw earlier in this chapter, if we've done our work creating each class correctly, the `main()` method should really just look like an outline of the entire program itself, instantiating objects and calling methods as needed to get the work done.

At the top of the file, we'll need to add import statements for each of the items we need to use in this program.

So, we'll start by creating a Deck object, and shuffling the deck.

Then, we'll create a hand of cards for the Player, and deal 2 cards into the player's hand. Once the player has a hand, we can instantiate the Player object, giving it both the Hand object for the player, as well as a reference to the Deck object so they player can draw cards later.

After that, we'll do the same for the Dealer, creating a hand first, adding 2 cards, and then creating a Dealer object.

Once both objects are created, we allow the player to make moves, drawing cards until they choose to stop or until they have a value greater than 21.

Then, we'll allow the Dealer to do the same, but in this case the dealer is also given the value of the player's hand. It allows the dealer to have a slight advantage.

Finally, in the `main()` method, we have a few If statements to determine who wins the game.

There we go! That's all it takes to play a simplified game of Blackjack. The version of the Main class in the textbook includes some helpful outputs to give a bit more information about what is going on when we play the game. So, when we run that program, we should be output similar this.

This program is definitely the largest and most complex program we've written thus far. However, each class only contains a couple of attributes and methods, and they all work together pretty seamlessly to make our Blackjack program a success. See if you can complete every part of this program here on this page. As you do, don't forget to run the structure tests first, before trying to run the functionality tests. Good luck!
