The shell must support the following internal commands:
1.cd <directory> - Change the current default directory to
2.<directory>. If the <directory> argument is not present, report the
3.current directory. If the directory does not exist an appropriate error
4.should be reported. This command should also change the PWD
5.environment variable.
6.cls - Clear the screen.
7.dir <directory> - List the contents of directory <directory>.
8.copy <source> <destination> - Copy the <source> folder to
9.<destination>.
10.v. print <comment> - Display <comment> on the display followed by a new
11.line (multiple spaces/tabs may be reduced to a single space).
12.md <directory> - Create the folder <directory>.
13.rd <directory> - Remove the folder <directory> if the folder is
empty, should display error message if it is not.
15.quit - Quit the shell.

Description of the Code : 
(1)We assumed maximum length of a command can be of 256 characters(MAX_LINE), count denotes total number of commands executed until now and maximum no of arguments in a command can be 129 (MAX_LINE/2 + 1). 
(2)main(void) function initializes inputBuffer to store the current command and args[] array for parsing the current command into arguments.
(3)We use different size of buffers to execute he commands properly.
Some of the important Library functions used are as follows ¨C 
(a)For executing 
cd command :: chdir(directory)---Library/Header file(unistd.h)
char* getcwd(char* buffer,size_t size)---Library/Header file(unistd.h)
(b) For executing all types of rd commands :: First,file is opened using DIR* opendir(const char *name) function, then read using struct dirent readdir(DIR* dir) function and removed files/directories according to the given command using int remove(const char *filename) function and finally closed the file using int closedir(DIR* dir) function.Libraries/Header files (dirent.h,sys/types.h) are included for using the builtin library functions. 
(c) For Creating a child process to run and supporting the redirection operators > and < to redirect the input and ouput of the program to indicated files.

Output Redirection:
The output from a command normally intended for standard output can be easily diverted to a file instead. This capability is known as output redirection.
If the notation > file is appended to any command that normally writes its output to standard output, the output of that command will be written to file instead of your terminal.
Eg: who, cat, etc

Input Redirection:
Just as the output of a command can be redirected to a file, so can the input of a command be redirected from a file. As the?greater-than character >?is used for output redirection, the?less-than character <?is used to redirect the input of a command.
Eg: wc, etc

Process:
When you start a process (run a command), there are two ways you can run it ?
1.Foreground Processes
2.Background Processes
Foreground Processes:
By default, every process that you start runs in the foreground. It gets its input from the keyboard and sends its output to the screen.
You can see this happen with the?ls?command. If you wish to list all the files in your current directory, you can use the following command ?
$ls ch*.doc
This would display all the files, the names of which start with?ch?and end with?.doc??
ch01-1.doc   ch010.doc  ch02.doc    ch03-2.doc 
ch04-1.doc   ch040.doc  ch05.doc    ch06-2.doc
ch01-2.doc   ch02-1.doc
The process runs in the foreground, the output is directed to my screen, and if the?ls?command wants any input (which it does not), it waits for it from the keyboard.
While a program is running in the foreground and is time-consuming, no other commands can be run (start any other processes) because the prompt would not be available until the program finishes processing and comes out.
Background Processes
A background process runs without being connected to your keyboard. If the background process requires any keyboard input, it waits.
The advantage of running a process in the background is that you can run other commands; you do not have to wait until it completes to start another!
The simplest way to start a background process is to add an ampersand (&) at the end of the command.
$ls ch*.doc &
This displays all those files the names of which start with?ch?and end with?.doc??
ch01-1.doc   ch010.doc  ch02.doc    ch03-2.doc 
ch04-1.doc   ch040.doc  ch05.doc    ch06-2.doc
ch01-2.doc   ch02-1.doc
Here, if the?ls?command wants any input (which it does not), it goes into a stop state until we move it into the foreground and give it the data from the keyboard.
That first line contains information about the background process - the job number and the process ID. You need to know the job number to manipulate it between the background and the foreground.
Press the Enter key and you will see the following ?
[1]   +   Done                 ls ch*.doc &
$
The first line tells you that the?ls?command background process finishes successfully. The second is a prompt for another command.



