---
title: "What is Programming?"
pre: "1. "
weight: 10
---

As with any learning adventure, we must begin somewhere. When learning how to write computer programs, one of the best questions to tackle first is "what is programming?" As it turns out, the answer to that question is key to understanding exactly what it is we are trying to learn. 

## A Simple Computer

{{% youtube En7FDq5XrsA %}}

[Video Materials]({{<relref "./video">}})

At its core, a computer is simply an electronic device that is capable of following instructions to perform calculations. In computer science theory, there is a special kind of theoretical computer called a _Turing Machine_ that represents the simplest version of a modern computer. It might look something like this, as imagined by an artist:

![Turing Machine](/images/01-oop/1.1.turing.wikimedia.png)[^1]

[^1]: File:Maquina.png. (2014, March 4). Wikimedia Commons, the free media repository. Retrieved 15:31, December 10, 2018 from https://commons.wikimedia.org/w/index.php?title=File:Maquina.png&oldid=118120539

A Turing Machine consists of an infinitely long tape that can be used to store data, and a small control box that manipulates the tape. The control box knows how to perform a few simple instructions, such as "Move Left" or "Write 0." So, to program a Turing Machine, we must simply tell the control box which instructions to follow, and it can do it. For example, if we want the Turing Machine to write "101" on the tape, we could write the following program:

1. Write 1
1. Move Right
1. Write 0
1. Move Right
1. Write 1
1. Stop

Seems simple enough. We won't go into the details here, but computer scientists have been able to prove that _any_ computer program that can run on a real computer could also be performed on a Turing Machine, as long as the Turing Machine has infinite time and an infinitely long tape. 

This video shows an example of what a Turing Machine might look like in real life.

{{% youtube "E3keLeMwfHY?start=200" %}}

So, all we really need to learn is how to write programs for a Turing Machine, right?

## A Modern Computer

![Desktop Computer](/images/01-oop/1.1.desktopcomputer.wikimedia.svg)[^2]

[^2]: File:Desktop computer clipart - Yellow theme.svg. (2018, July 11). Wikimedia Commons, the free media repository. Retrieved 15:44, December 10, 2018 from https://commons.wikimedia.org/w/index.php?title=File:Desktop_computer_clipart_-_Yellow_theme.svg&oldid=310624404

Well, it's unfortunately not that simple. There are two major differences between a Turing Machine and a modern computer that we must deal with. First, a modern computer knows many more instructions than a Turing Machine. To learn how to write programs that a modern computer can understand, we'd have to learn an entirely different vocabulary of commands. At the same time, modern computers are very complex systems, so any program we write might not be very efficient at doing what we want. 

So, to learn how to write computer programs quickly and easily, we really want to be able to do two things:

1. Use a vocabulary of commands that are familiar to us
1. Have those commands turn into programs that run efficiently on a modern computer

## Compilers & Interpreters to the Rescue!

![Rear Admiral Grace M. Hopper, USN](/images/01-oop/1.1.gracehopper.wikimedia.jpg)[^3]

[^3]: File:Commodore Grace M. Hopper, USN (covered).jpg. (2018, July 21). Wikimedia Commons, the free media repository. Retrieved 15:51, December 10, 2018 from https://commons.wikimedia.org/w/index.php?title=File:Commodore_Grace_M._Hopper,_USN_(covered).jpg&oldid=311956355

Developing computer programs was very difficult work in the 1950s, and many of those early programmers were looking for a better way to solve that exact problem. One of these was Rear Admiral Grace Hopper, shown above. Her team was one of the first to develop the idea of writing computer programs using English words, and then using a second program, which they called a _compiler_, to convert those English words into instructions a computer could understand.

Their compiler made developing computer programs much simpler, since programmers didn't have to learn an entirely new vocabulary to tell the computer what to do. Instead programmers simply had to learn the rules of what a computer could and couldn't understand, and the _syntax_, or grammar rules, of how the compiler expected the program to be written. These new programming languages that use English words are referred to as _high-level languages_.

Programmers would now write the _source code_ for the program in a high-level language, and then use a compiler to generate the _machine code_ that the computer would actually run. In addition, since the compiler was a program itself, it could make sure the machine code it generated was as fast and efficient as possible, eliminating lots of hard work programmers would have to perform to tailor each program to fit the hardware it was going to run on.  

Today, programming languages such as _C_, _C++_, and _Java_ use compilers to convert source code into machine code. 

![Steve Russell](/images/01-oop/1.1.steverussell.wikimedia.jpg)[^4]

[^4]: File:Steve Russell.jpg. (2017, December 28). Wikimedia Commons, the free media repository. Retrieved 16:05, December 10, 2018 from https://commons.wikimedia.org/w/index.php?title=File:Steve_Russell.jpg&oldid=274743269

At the same time, other developers such as Steve Russell, shown above, were working on another type of program, called an _interpreter_, to solve the same problem. An interpreter can read source code and immediately tell the computer what steps to perform, without needing to generate the whole machine code first. This makes it much easier to write and edit programs on the fly, as the interpreter reads the source code directly each time the program runs. Today, programming languages such as _PHP_, _JavaScript_, and _Python_ use interpreters to run the source code on a computer.

## Programming

So, _programming_ is simply the act of writing computer code in a way that a computer can run it. In most cases today, that means developing the _source code_ for a program in a _high-level language_, then using either a _compiler_ to generate the _machine code_ for that program, or an _interpreter_ to run the program directly on the computer from the source code. Of course, we can always write machine code by hand, but that is quite a bit more difficult.  

In this class, we'll learn how to write source code in one of two common languages, Java and Python. They both have their own unique features, especially since Java is a compiled language and Python is an interpreted language. However, as we saw above with the Turing Machine example, each language can be used to write _any_ computer program. So, the choice of language is really more about personal preference and the unique features of each language than anything else. 

This makes sense, because in general we can use both English and Spanish, as well as most other languages today, to express the same thoughts and ideas, even if we may not always have a word with the same meaning in both languages.