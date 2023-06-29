---
title: "Running a Program"
pre: "2. "
weight: 20
---

Modern computers share many theoretical similarities with the Turing Machine, but in practice they are much more advanced. In this section, we'll discuss how a modern computer is able to run programs we've written in a high-level programming language like Java or Python.

{{% notice note "Programming Languages are Rosetta Stones" %}}

A programming language, along with the associated compiler or interpreter, is a complete set of tools to write and translate instructions written in that language into the binary code that a computer's central processing unit (CPU) can natively execute.

Both Java and Python do this by producing an intermediate representation (byte code) then translating that to machine code. In Java's case this byte code is saved as a `class` file, but usually the Python interpreter does not store the byte code.

![Simplified View of Computer Execution](/images/01-oop/1.1.1.Translation.png)

Computer central processing units (CPU) <b>exclusively</b> run machine code.

{{% /notice %}}

Learning to program requires some basic understanding of how a computer works. In the most basic sense, a computer has a large amount of memory connected to a central processing unit (CPU). The memory consists of many bytes of data, each containing eight binary values (e.g. 01001101). 

The memory itself is split into various regions, with different regions storing the machine code instructions that make up a program and the data that the program is operating on.

![Simplified View of Computer Architecture](/images/01-oop/1.1.1_comp_architecture.png)

The CPU contains enough circuitry to interpret the instructions it is given and perform the requested mathematical and logical operations on the data provided. 

Consider a single line of code in a program:

```tex
z = 5 + 7
```

In most languages, a line similar to this will instruct the computer add the values of 5 and 7 and save the value into a variable named `z`, which will be stored in some location in memory. In a machine language, this single line of code may be actually require different instructions to complete. The table below shows one possible interpretation of that line of code into machine language.

| Instruction            | Meaning         |
|------------------------|------------------| 
| `LVal eax, 0x01A0`      | Load the value found at memory loc `0x01A0` into CPU register `eax` <br>This is where `5` is stored|
| `LVal ebx, 0x01A8`      | Load the value found at memory loc `0x01A8` into CPU register `ebx` <br>This is where `7` is stored|
| `Add eax, ebx` | Add the values in CPU registers `eax` and `ebx` together and store the result back into `eax` |
| `Mov eax, 0x01B0` | Move the value in CPU register `eax` to memory location `0x01B0` <br>This is where the variable `z` is stored|

Machine language is pretty ugly, but this is really how a CPU functions. Thankfully, we have many higher-level programming languages available, such as Java and Python, so we usually don't have to write code directly in machine language. 

## Estimating Program State

From this, we can come up with a pretty powerful **abstraction** that represents how a computer works.  In programming, an abstraction is a simplified model of a complex system, keeping only the most important details to make using the model easy.

![Elements of Program State](/images/01-oop/1.1.1_program_state.png)

In our abstract model of a computer, we see that a program consists of an ordered list of instructions to be executed, and memory is a set of labelled boxes that can store any data our program requires. We also have a pointer that keeps track of which instruction the computer is currently executing. The list of instructions, the instruction pointer, and the memory combined all make up a **program's state** when it is running on a computer. Tools such as [Python Tutor](https://pythontutor.com/) or [Java Tutor](https://pythontutor.com/java.html) use a model very similar to this to help us understand how our programs actually work.