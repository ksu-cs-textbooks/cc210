---
title: "Object-Oriented Programming"
pre: "2. "
weight: 20
---

## Data Centric

At its heart, object-oriented programming is about the data. We may talk about how a class stands for a blueprint or outline of a real world item, but what we mean is the data that describes and defines that real world object. It is how we choose to model this data, how we allow access to it and manipulate it, that drives the object-oriented paradigm.

There are four pillars to object-oriented programming, all having to do with data and how it can be accessed and changed.

### Encapsulation

Encapsulation refers to data and method hiding.  The idea is things outside of the object should not directly access the object's data.  This ensures the data remains consistent with object we are modeling.  A `Car` class might have a `speed` attribute, and there might maximum values for changing the speed--a max braking or acceleration.  Additionally there might be a maximum speed.

Encapsulation says, when you ask the `Car` object how fast it is going, the object does not give you access to its data, but instead provides you a copy.  When you want it to speed up, you don't change the object's speed directly; instead you use the object's `accelerate` method, and the object changes its own speed. 

### Inheritance 

Inheritance is the idea that like objects share traits, and can go from the generic to the specific.  We might have `Bird` class, with generic `sing` and `move` methods, and a `wingspan` attribute.  But then we might have a `Parrot` class, which is a kind of bird, so it too can `sing` and has a `wingspan`;  but in this case a `Parrot` might also have a `talk` method, and an additional `colorScheme` variable.  Inheritance is a way to link classes so that the the subclass is a super set of the base class -- it has all the superclass's stuff and more.

### Abstraction

Abstraction deals with leaving things un-defined.  In our `Bird` class, maybe there is no body (no code) to the `move` method, just the fact that such a method should exist. The concept that birds move is independent of a particular kind of bird.  This would allow a `Penguin` class to code `move` as swimming, `Ostrich` to code it as running, and `Parrot` as riding on pirate shoulders.

### Polymorphism

Polymorphism is the idea that the same method can give you different behaviors.  Say we code the `Bird` class with the beautiful song of the musician wren.  But the `Eagle` class, also a kind of `Bird`, might **override** this with a loud screech.  Overriding is when a subclass replaces a superclass method.  A `Parrot` and `Eagle` are both instances of the `Bird` superclass, but you get different behaviors (sounds) when you invoke their `sing` method.

##  That Seems Complicated

It is a lot, but it can be learned a little at a time.  This later modules will deal with some basics of encapsulation, and introduce inheritance.  Abstraction and polymorphism will be taught more deeply in later courses.

