# OS-Assignment
## Questions
[Q 2.24](https://github.com/ayushbaghel-007/OS-Assignment/tree/main/Q%202.24)

In Section 2.3, we described a program that copies the contents of one file to a destination file. This program works by first prompting the user for the name of the source and destination files. Write this program using either the POSIX or Windows API. Be sure to include all necessary error checking, including ensuring that the source file exists.

Once you have correctly designed and tested the program, if you used a system that supports it, run the program using a utility that traces system calls. Linux systems provide the strace utility, and macOS systems use the dtruss command. (The dtruss command, which actually is a front end to dtrace, requires admin privileges, so it must be run using sudo.) These tools can be used as follows (assume that the name of the executable file is FileCopy:

**Linux: strace ./FileCopy**

**macOS: sudo dtruss ./FileCopy**

Since Windows systems do not provide such a tool, you will have to trace through the Windows version of this program using a debugger.

[Q 3.21](https://github.com/ayushbaghel-007/OS-Assignment/tree/main/Q%203.21)

The Collatz conjecture concerns what happens when we take any positive integer n and apply the following algorithm:

*n = n∕2, if n is even*

*n = 3 × n + 1, if n is odd*
    
The conjecture states that when this algorithm is continually applied,
all positive integers will eventually reach 1. For example, if n = 35, the
sequence is

   35, 106, 53, 160, 80, 40, 20, 10, 5, 16, 8, 4, 2, 1

Write a C program using the fork() system call that generates this
sequence in the child process. The starting number will be provided
from the command line. For example, if 8 is passed as a parameter on
the command line, the child process will output 8, 4, 2, 1. Because the
parent and child processes have their own copies of the data, it will be
necessary for the child to output the sequence. Have the parent invoke
the wait() call to wait for the child process to complete before exiting
the program. Perform necessary error checking to ensure that a positive
integer is passed on the command line.

## Requirements
1. Windows Subsystem for Linux (WSL)
2. GCC
3. VS Code

## Results
**Q 2.24 :**

+ The [C program](https://github.com/ayushbaghel-007/OS-Assignment/blob/main/Q%202.24/answer.c) copies the contents from an existing file and paste the contents into a new file (which does not exist before executing the program).
+ The input file is sample.txt from which the contents were copied.
+ The output file is output.txt to which the copied content was pasted.
+ A [strace_log](https://github.com/ayushbaghel-007/OS-Assignment/blob/main/Q%202.24/strace_log) file was also created in which all the system calls were logged.

![ss1](https://user-images.githubusercontent.com/76652351/202928209-3769de60-95c5-4b64-b641-36770c48bd23.jpg)

![ss2](https://user-images.githubusercontent.com/76652351/202928237-d7e1c0b2-e80c-466b-8d13-fa460335b440.jpg)

**Q 3.21 :**

+ The [C program](https://github.com/ayushbaghel-007/OS-Assignment/blob/main/Q%203.21/sequence.c) creates child process and this child process is responsible for printing the Collatz Conjecture sequence .
+ fork() system call is used to create child process.
+ Once the parent process calls fork() system call then parents wait for child process to complete the work assigned by calling wait(NULL) system call.
+ This code is applicable only for non negative integers as input.

![ss1](https://user-images.githubusercontent.com/76652351/202928282-d406e4ff-48d1-4bc8-9ec7-585182bbd1e2.jpg)

## References
1. https://github.com/mattlevan/copy.c (Q 2.24)
2. https://github.com/PRASANNA-416/CS252-OS-Project-2022 (Q 3.21)

## Author
Ayush Baghel (201EE113)
