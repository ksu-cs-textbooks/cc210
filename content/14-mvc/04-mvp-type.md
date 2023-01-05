---
title: "MVP - A Type of MVC"
pre: "4. "
weight: 40
---

Technically, what we are going to implement is Model-View-Presenter, MVP.  MVP is a specialization of the MVC design pattern which enforces strict architectural separation between the elements and makes the View solely responsible for handling all the user interface (input and output).

![Model-View-Presenter Architecture](/images/14-mvc/13.MVP_arch.png)

Under strict layering, architectural layers can only interact with adjacent layers.  This can make the initial coding a little cumbersome. 

The advantage of this strict layering is it allows you to "swap parts".  You may have Views written for PC-terminal users, mobile app users and even other computer programs.  Change one import statement and the program is good to go.  

Say you have a an MVP program written for a game played on a square grid, like checkers.  The Model contains all the checker details--swap  it out for a "chess" model and you can probably still run.  The Presenter (which is basically middle-ware alternating the turns and checking for wins) should be able to handle the change and the only difference to the View is the "picture" it uses for the various pieces.

Some authors, including us, as well as many internet posters, will not differentiate between MVC and MVP.  After all, MVP "is a " MVC implementation. However, in the original and still authoritative text[^1], the View is just a display and having it handle inputs is non-standard.  

[^1]: <u>Design Patterns: Elements of Reusable Object Oriented Software</u>, Erich Gamma et al, 1994