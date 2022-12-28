---
title: "Hello World"
pre: "6. "
weight: 60
---

Tradition dictates that the first program in any introduction course is Hello World.

Hello World simply prints "Hello World" to the screen.

An object-oriented version of this program might look like

```tex
1  CLASS HelloWorld{
2     FUNCTION main(args){
3         DISPLAY("Hello World!")
4     }
5   }
```

Here the "work" of the program is done by line 3.

## Pseudo Code

Pseudo code is typically used to outline the control-flow of a program.  Control-flow refers to the order in which individual statements are executed. The CC courses follow a modified version pseudo code introduced in the AP Computer Science Principles--Course Exam Description[^1].  Pseudo code is intended to be a near English representation of a program.

[^1]: College Board, 2020 available https://apcentral.collegeboard.org/pdf/ap-computer-science-principles-course-and-exam-description.pdf?course=ap-computer-science-principles

### DISPLAY()

The pseudo code statement `DISPLAY(description)` does a lot of heavy lifting.  In this context, DISPLAY means visually indicate to the user.  In this course we will run terminal based programs and DISPLAY will typically indicate "print to the terminal".

However, in other contexts `DISPLAY` could mean send a notification (smart phone), open a pop up (graphical user interface), or even change the speedometer (automotive display controller).

