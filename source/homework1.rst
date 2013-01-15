Homework 1
==========

Summary
-------
The purpose of this assignment is to learn to work with Linux / Minix and familiarize yourself with basic data structures, string manipulation/parsing, etc. We will be writing a program that takes the output of the "ps" command and presents the list of processes as a proper tree. It will be left to your imagination to decide how to best present the tree of processes, but a simple indentation scheme should be sufficient.

The first part of this assignment will be to get this program working on Minix. This means:
 #. You will need to get a Minix virtual machine running. See lecture #1 notes!
 #. Make sure you know how to edit, compile, and run C programs on this platform. This will require you learn a simple editor (e.g. nano), the C/C++ compiler (gcc/g++), and a debugger (gdb)
 #. Make sure you know how to setup version control for this and all future assignments.


Details
-------
Your job in this assignment will be:
 #. Use the popen() call to establish a pipe to the "ps" command. We'll use this to capture a snapshot of the list of currently running processes on your system. You will need to figure out how the options of the PID and PPID in Minix. For example, on Linux ps, ps -ef shows the PID and PPID. On Minix, it's slightly different (of course), so you'll want to read the Minix man page for ps.
 #. A big part of the job is to learn how "ps" works (read man page!) and figure out what all of the columns represent.
 #. Write a program that builds a process tree.
     - Read one line of input at a time but exclude the header line. You will need to use strtok() or write your own parser to extract data from the input
     - Extract the PID (process ID) and PPID (parent process ID) from each line
     - Create a process info "node" and insert it into the tree, such that the new "node" is linked to the strtok()'d parent "node".
     - Once all of the lines of "ps" have been consumed, print the tree. To keep this simple, you may use indentation to indicate that a process is the parent of another process.
 #. You may submit your assignment using Google Code, BitBucket, or GitHub. It is ok to use a public repository.

Notes
-----
You are allowed to talk to others as you work on this. Keep in mind, however, that you will need to be able to answer questions about what you learned in this assignment -- and all future assignments -- on the quizzes. So please make sure you spend time thinking about and doing the assignment on your own.

