simple_shell
Table of Contents

    Description
    File Structure
    Requirements
    Installation
    Example of Use
    Authors

Description

Shell is often confused with as a terminal window and I was a victim of this false thinking too. I got to find out that a shell is just a middleman between the typed commands entered by the users and the computer system that performs an action based on the commands(command line interpreter). The first Unix shell was written by Ken Thompson in 1971. The picture below best describes the shell.

Image of Shell

This project deals with creating a shell with minimal functionalities and the standard functions that were employed were:- access, execve, exit, fork, free, fstat, getline, malloc, perror, signal, stat, wait, write.
File Structure

    AUTHORS - This file lists the people that contributed the project
    man_1_simple_shell - Custom manual page for the simple shell.
    shell.h - This is the header file that contains the library dependencies and structures required for compilation of the program.
    builtins.c - Contains the major builtin functions. Down below lists the functions names and their use:
        check_for_builtins - This helps to check if the command is a builtin
        new_exit - This exits the shell with an option for specified status
        _env - This prints the environment shell variables to stdout.
        new_setenv - initializes a new environment variable, or modifies an existing one
        new_unsetenv - removes an environment variable
    builtins2.c - helper functions for the builtins
        add_key - creates a new environment variable
        find_key - finds an environment variable in the environment array
        add_value - creates a new environment variable string
        _atoi - converts a string into a non-negative integer
    environment.c - These are functions that deals with the environment.
        make_env - creates the shell's environment from the parent process
        free_env - frees the shell's environment
    errors.c - functions related to printing errors
        print_error - prints an error message to the standard error
        _puts2 - prints a string to the standard error
    memory_allocation.c - Functions related to memory allocation
        _realloc - a custom realloc function for arrays of pointers
    new_strtok.c - Custom strtok and helper functions
        check_match - checks if a character matches any in a string
        new_strtok - a custom strtok for the shell
    path.c - functions related to executing commands
        path_execute - executes a command in the PATH
        find_path - finds the PATH environment variable
        check_for_path - checks if the command is in the PATH
        execute_cwd - executes a command with an absolute path
        check_for_dir - checks if the command contains an absolute path
    simple_shell.c - These is the main shell functions for the shell
        main - the main function of the program
        sig_handler - handles SIGINT( this is what is sent when ^C is sent as a command by the user)
    strfunc.c - Functions concerned with manipulating the string
        _puts.c - This writes to the standard output.
        _strdup - duplicates a string
        _strcmpr - compares two strings
        _strcat - concatenates two strings with a / in the middle
        _strlen - calculates the length of a string
    tokenize.c
        tokenize - creates an array of tokens from a buffer with a specified delimiter

Requirements

simple_shell should be compiled on Ubuntu 20.04 LTS using gcc, using the options -Wall -Werror -Wextra -pedantic -std=gnu89.
Installation

    Clone this repository.
    Change directories into the repository: cd simple_shell
    Compile: gcc -Wall -Werror -Wextra -pedantic *.c -o hsh
    Run the shell in interactive mode: ./hsh
    Or run the shell in non-interactive mode: example echo "pwd" | ./hsh

Example of Use

$ ./hsh
$ # This is our rendition of the shell
$ ls -al
total 100
drwxrwxr-x 3 vagrant vagrant  4096 May 18 20:23 .
drwxr-xr-x 9 vagrant vagrant  4096 May 18 17:41 ..
drwxrwxr-x 8 vagrant vagrant  4096 May 18 20:23 .git
-rw-rw-r-- 1 vagrant vagrant   146 May 18 16:14 AUTHORS
-rw-rw-r-- 1 vagrant vagrant  5522 May 18 20:22 README.md
-rw-rw-r-- 1 vagrant vagrant  2863 May 18 16:14 builtins.c
-rw-rw-r-- 1 vagrant vagrant  2391 May 18 16:14 builtins2.c
-rw-rw-r-- 1 vagrant vagrant   710 May 18 16:14 environment.c
-rw-rw-r-- 1 vagrant vagrant  1217 May 18 16:14 errors.c
-rwxrwxr-x 1 vagrant vagrant 26984 May 18 20:23 hsh
-rw-rw-r-- 1 vagrant vagrant  2512 May 18 16:14 man_1_simple_shell
-rw-rw-r-- 1 vagrant vagrant   485 May 18 16:25 memory_allocation.c
-rw-rw-r-- 1 vagrant vagrant  1276 May 18 16:29 new_strtok.c
-rw-rw-r-- 1 vagrant vagrant  3432 May 18 16:30 path.c
-rw-rw-r-- 1 vagrant vagrant  1821 May 18 16:31 shell.h
-rw-rw-r-- 1 vagrant vagrant  1510 May 18 16:33 simple_shell.c
-rw-rw-r-- 1 vagrant vagrant  2116 May 18 17:12 strfunc.c
-rw-rw-r-- 1 vagrant vagrant   720 May 18 17:13 tokenize.c

Authors

Abanum Oliseyenum

Nnadi Chigozie
