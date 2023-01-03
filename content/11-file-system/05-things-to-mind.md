---
title: "Things to Keep in Mind"
pre: "5. "
weight: 50
---

##  Operating System and File Access

Linux systems connect programs to the files by use of **file descriptors**.  Linux must keep track of and de-conflict access to all file descriptors used by all processes at all times.  There are a lot of processes in a modern computer, as I am typing this section, my Windows 10 machine has 5-applications and 92-background programs--each of which may be accessing 0 or more file descriptors.

There are three things to realize about file descriptors.  First there is a limit to their number, but that limit is pretty big. Each process in a standard Linux installation can have up to 1024 file descriptors allocated to it.  Each minimally has three:  stdin (the keyboard); stdout (the terminal) and stderr (a separate "stream" for error messages).  In this class, we display stderr to the terminal, but in production applications this may be re-routed to a log file or even a real-time monitoring center in the case of security errors.

Next, depending on how we access a file from our programs, Linux has to check every other file descriptor for potential conflicts.  For example many programs can read from the same file at the same time without issues; but allowing many files to write to the the same file at the same time is VERY complex if done correctly--often it is not allowed.  Allowing one writer with many readers is also a complex task for the operating system to figure out.  This leads to the third thing about file descriptors.

The time it takes Linux to manage the file access grows exponentially with each new file descriptor.  The time added to the task for the system's 1000th file descriptor is more than the time that was added for the 999th file descriptor.

Closing a file tells the operating system to delete the file descriptor.

## Generally Good Ideas About File Access

1.  Keep files open for as short a time as practical.  Opening a file, reading it into memory, and then closing it is often better than keeping the file open and reading pieces of it in bits. If the file is huge, there are random access methods (not covered in this class), which allow you to "fast forward" to the part you need. 
2.  If you know you are only going to read the file, open it for read only access. It is easier for the operating system to manage read only file descriptors.
3. Make sure that you close files.  Either explicitly do it, using some `myfile.close()` method or ensure you open it in a managed context (`with` in Python and C#, `try (with resource)` in Java).


