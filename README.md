<h1>ALX Simple Shell Team Project<h1>

This is an ALX collaboration project on Shell. We were tasked to create a simple shell that mimics the Bash shell. Our shell shall be called hsh

<h2>Project was completed using<h2>
<hr>
<ul>C language<ul>
<ul>shell<ul>
<ul>Betty linter<ul>

<h1>General Requirement for project<h1>
<hr>

<ul>All files will be compiled on Ubuntu 20.04 LTS using gcc, using the options -Wall -Werror -Wextra -pedantic -std=gnu89<ul>
<ul>All files should end with a new line<ul>
<ul>A README.md file, at the root of the folder of the project is mandatory<ul>
<ul>Use the Betty style. It will be checked using betty-style.pl and betty-doc.pl<ul>
<ul>Shell should not have any memory leaks<ul>
<ul>No more than 5 functions per file<ul>
<ul>All header files should be include guarded<ul>
<ul>Write a README with the description of the project<ul>

<h2>Description<h2>
<hr>

hsh is a simple UNIX command language interpreter that reads commands from either a file or standard input and executes them.

<h2>How hsh work<h2>
<ul>Prints a prompt and waits for a command from the user<ul>
<ul>Creates a child process in which the command is checked<ul>
<ul>Checks for built-ins, aliases in the PATH, and local executable programs<ul>
<ul>The child process is replaced by the command, which accepts arguments<ul>
<ul>When the command is done, the program returns to the parent process and prints the prompt<ul>
<ul>The program is ready to receive a new command<ul>
<ul>To exit: press Ctrl-D or enter "exit" (with or without a status)<ul>
<ul>Works also in non interactive mode<ul>

<h1>Compilation<h1>

gcc -Wall -Werror -Wextra -pedantic -std=gnu89 *.c -o hsh


<h2>Invocation<h2>

Usage: hsh [filename]

To invoke hsh, compile all .c files in the repository and run the resulting executable.



hsh can be invoked both interactively and non-interactively. If hsh is invoked with standard input not connected to a terminal, it reads and executes received commands in order.



Example:

$ echo "echo 'hello'" | ./hsh

'hello'

$

If hsh is invoked with standard input connected to a terminal (determined by isatty(3)), an interactive shell is opened. When executing interactively, hsh displays the prompt $ when it is ready to read a command.



Example:



$./hsh

$

Alternatively, if command line arguments are supplied upon invocation, hsh treats the first argument as a file from which to read commands. The supplied file should contain one command per line. hsh runs each of the commands contained in the file in order before exiting.



Example:



$ cat test

echo 'hello'

$ ./hsh test

'hello'

$

<h2>Environment<h2>

Upon invocation, hsh receives and copies the environment of the parent process in which it was executed. This environment is an array of name-value strings describing variables in the format NAME=VALUE. A few key environmental variables are:

<h2>HOME<h2>
The home directory of the current user and the default directory argument for the cd builtin command.
