---
title: "How a Computer Sees a Program"
pre: "2. "
weight: 20
---

<p style="color:purple; margin:20px"><em> This section introduces <b>Program State</b>, a concept key to understanding how the computer is processing your program. Being able to estimate program state allows us to fix bugs. </em></p>

{{% notice note "Programming Languages are Rosetta Stones" %}}

A programming language is a complete tool set to translate instructions written in one set of symbols to instructions written in machine binary code.  Both Java and Python do this by producing an intermediate representation (byte code) then translating that to machine code.  In Java's case this byte code is saved, in Python's it is not.

![Simplified View of Computer Execution](/images/01-oop/1.1.1.Translation.png)

Computer Central Processing Units (CPU) <b>exclusively</b> run machine code.

{{% /notice %}}
If you are going to learn to program, you need some idea of how a computer works.  The most basic view of the computer is a bank of memory connected to a Central Processing Unit (CPU). Each byte in memory has its own unique address and an 8-bit value (eight 0s or 1s : 01001101).  This memory is effectively split up into various regions, with  instructions in one region and  data in another.

![Simplified View of Computer Architecture](/images/01-oop/1.1.1_comp_architecture.png)

The CPU has a limited amount of memory (enough to hold a few dozen values) called registers.  It also contains all the circuity to interpret the instructions an perform mathematical and logical operations on the values stored in the registers.  

<p></p>

Consider the following program, <code>Z = 5 + 7</code>, which instructs the computer add the values of 5 and 7 and save the value into a variable (memory location).  In machine language this many more commands, a simplification might be:</p>
| Instruction            | Meaning         |
|------------------------|------------------| 
| LVal eax, 0x01A0      | Load the value found at memory loc 0x01A0 into reg eax <br>This is where “5” is stored|
| LVal ebx, 0x01A8      | Load the value found at memory loc 0x01A8 into reg ebx <br>This is where “7” is stored|
| Add eax, ebx | Add the values in registers eax and ebx together and store the result back into eax|
|Mov eax, 0x01B0 | Move the value in register eax to memory location 0x01B0 <br>This is where the variable Z is stored|

Pretty ugly, but this is how the CPU gets its instructions.

## Estimating Program State
But from this we can come up with a pretty powerful **abstraction**.  In programing, an abstraction is a simplified model of a complex system, keeping only the most important details to make using the model easy.

![Elements of Program State](/images/01-oop/1.1.1_program_state.png)

Our abstraction will be that a program consists of an ordered list of instructions, a bunch of labeled cubbyholes for data and some pointer that keeps track of which instruction the computer is currently executing.  These things, the list of  instructions, the current instruction and all the values of all the variables are referred to as a program's state.