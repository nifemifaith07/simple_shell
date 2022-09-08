# 0x16. C - Simple Shell
**C
Group project
Syscall**
## Background Context

Write a simple UNIX command interpreter.

![Gates of Shell](https://github.com/nifemifaith07/pshell/blob/main/shellA/shell.png)

^ “The Gates of Shell”, by [Spencer Cheng](https://alx-intranet.hbtn.io/rltoken/AtYRSM03vJDrko9xHodxFQ), featuring [Julien Barbier](https://alx-intranet.hbtn.io/rltoken/-ezXgcyfhc8qU1DeUInLUA)
## Resources
[Unix shell](https://alx-intranet.hbtn.io/rltoken/f0YU9TAhniMXWlSXtb64Yw)

[Thompson shell](https://alx-intranet.hbtn.io/rltoken/7LJOp2qP7qHUcsOK2-F3qA3)

[Ken Thompson](https://alx-intranet.hbtn.io/rltoken/wTSu31ZP1f7fFTJFgRQC7w)

[Everything you need to know to start coding your own shell](https://alx-intranet.hbtn.io/concepts/64)

man or help:
sh (Run sh as well)

## Learning Objectives
* At the end of this project, you are expected to be able to [explain to anyone](https://alx-intranet.hbtn.io/rltoken/9LNz86CtOTos9oL3zxIO3A), without the help of Google:
* Who designed and implemented the original Unix operating system
* Who wrote the first version of the UNIX shell
* Who invented the B programming language (the direct predecessor to the C programming language)
* Who is Ken Thompson
* How does a shell work
* What is a pid and a ppid
* How to manipulate the environment of the current process
* What is the difference between a function and a system call
* How to create processes
* What are the three prototypes of main
* How does the shell use the PATH to find the programs
* How to execute another program with the execve system call
* How to suspend the execution of a process until one of its children terminates
* What is EOF / “end-of-file”?
## Requirements
### General
* A README.md file, at the root of the folder of the project with the description of your project
* Code should use the Betty style. It will be checked using betty-style.pl and betty-doc.pl
* Shell should not have any memory leaks
* No more than 5 functions per file
* Use system calls only when you need to (why?)
* You should have an AUTHORS file at the root of your repository
### GitHub
*There should be one project repository per group. Add your partner as a collaborator.
## Output
Unless specified otherwise, your program must have the exact same output as sh (/bin/sh) as well as the exact same error output.

The only difference is when you print an error, the name of the program must be equivalent to your argv[0] (See below)

Example of error with sh:

    $ echo "qwerty" | /bin/sh
    /bin/sh: 1: qwerty: not found
    $ echo "qwerty" | /bin/../bin/sh
    /bin/../bin/sh: 1: qwerty: not found
    $

Same error with your program hsh:

    $ echo "qwerty" | ./hsh
    ./hsh: 1: qwerty: not found
    $ echo "qwerty" | ./././hsh
    ./././hsh: 1: qwerty: not found
    $
## List of allowed functions and system calls
* access (man 2 access)
* chdir (man 2 chdir)
* close (man 2 close)
* closedir (man 3 closedir)
* execve (man 2 execve)
* exit (man 3 exit)
* _exit (man 2 _exit)
* fflush (man 3 fflush)
* fork (man 2 fork)
* free (man 3 free)
* getcwd (man 3 getcwd)
* getline (man 3 getline)
* getpid (man 2 getpid)
* isatty (man 3 isatty)
* kill (man 2 kill)
* malloc (man 3 malloc)
* open (man 2 open)
* opendir (man 3 opendir)
* perror (man 3 perror)
* read (man 2 read)
* readdir (man 3 readdir)
* signal (man 2 signal)
* stat (__xstat) (man 2 stat)
* lstat (__lxstat) (man 2 lstat)
* fstat (__fxstat) (man 2 fstat)
* strtok (man 3 strtok)
* wait (man 2 wait)
* waitpid (man 2 waitpid)
* wait3 (man 2 wait3)
* wait4 (man 2 wait4)
* write (man 2 write)
## Compilation
Your shell will be compiled this way:
**gcc -Wall -Werror -Wextra -pedantic -std=gnu89 *.c -o hsh**
## Testing
Your shell should work like this in interactive mode:

    $ ./hsh
    ($) /bin/ls
    hsh main.c shell.c
    ($)
    ($) exit
    $
But also in non-interactive mode:

    $ echo "/bin/ls" | ./hsh
    hsh main.c shell.c test_ls_2
    $
    $ cat test_ls_2
    /bin/ls
    /bin/ls
    $
    $ cat test_ls_2 | ./hsh
    hsh main.c shell.c test_ls_2
    hsh main.c shell.c test_ls_2
    $
## TASKS
0. betty would be proud
* Write a beautiful code that passes the Betty checks
1. Simple shell 0.1
* Write a UNIX command line interpreter
2. Simple shell 0.2
* Handle command lines with arguments   
3. Simple shell 0.3
* Handle the PATH
* fork must not be called if the command doesn’t exist
4. Simple shell 0.4
* Implement the exit built-in, that exits the shell
* Usage: exit
* You don’t have to handle any argument to the built-in exit
5. Simple shell 1.0
* Implement the env built-in, that prints the current environment
6. Simple shell 0.1.1
* Write your own getline function
* Use a buffer to read many chars at once and call the least possible the read system call
* You will need to use static variables
* You are not allowed to use getline
7. Simple shell 0.2.1
* You are not allowed to use strtok
8. Simple shell 0.4.1
* handle arguments for the built-in exit
* Usage: exit status, where status is an integer used to exit the shell
9. setenv, unsetenv
* Implement the setenv and unsetenv builtin commands

*setenv*
* Command syntax: setenv VARIABLE VALUE

*unsetenv*
* Command syntax: unsetenv VARIABLE
10. cd
* Implement the builtin command cd
* Command syntax: cd [DIRECTORY]
* If no argument is given to cd the command must be interpreted like cd $HOME
11. ;
* Handle the commands separator ;
12. && and ||
* Handle the && and || shell logical operators
13. alias
* Implement the alias builtin command
* Usage: alias [name[='value'] ...]
14. Variables
* Handle variables replacement
* Handle the $? variable
* Handle the $$ variable
15. Comments
* Handle comments (#)
16. File as input
* Usage: simple_shell [filename]

## AUTHORS
**GitHub: [Amuda Faith](https://github.com/nifemifaith07)**
**GitHub: [Prince Edeh](https://github.com/Mekino05)**
