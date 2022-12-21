---
title: "Turing Machines"
pre: "1. "
weight: 10
hidden: true
---

{{< youtube En7FDq5XrsA >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

Alan Turing was an early computing pioneer who remained largely unknown outside of the field until recently with the release of _The Imitation Game_ in 2014. That movie centered around his work to decode German codes created by the Enigma Machine during World War II. However, long before his time at Bletchley Park, he was already making an impact in the world of computer science.

In 1936, Turing proposed an imaginary computer, which we now refer to as a Turing Machine, that could help us determine what problems could be solved using a computer. It was designed to be as simple as possible, able to only read or write a single binary bit at a time and follow very simple instructions.

However, Turing was able to demonstrate that his imaginary computer, given infinite time, infinite storage space, and a sufficiently complex program made of those simple instructions, could solve any problem that any other real-world computer could solve. Yup, in theory, it could be programmed to do everything from solve complex linear equations to play _Angry Birds_ (or, at least, perform the underlying calculations required to play _Angry Birds_)!

Modern computers are similar to Turing Machines, but a modern computer may have several hundred instructions that it knows how to follow. Those instructions may not make much sense to us, especially if we don't have a deep understanding of how a computer works internally. So, we need some way we can tell our computer what we'd like it to do without having to learn everything there is to know about it. In effect, this is very similar to learning how to drive a modern car - we don't need to know every detail of how it works to be able to use it efficiently.

Thanks to the work of several computing pioneers such as Rear Admiral Grace Hopper and Steve Russell, we can use a _high-level programming language_ such as Java or Python to tell our computer exactly what we'd like it to do, using words and symbols we can easily understand. Then, we can use special programs on our computer, such as a _compiler_ for Java and an _interpreter_ for Python, to convert that program written in a _high-level language_ into _machine code_, which is something our computer can understand.

In this chapter, we'll go through the steps needed to write our very first computer program. Make sure you read the material below before moving on, since the next page contains a short quiz. Good luck!