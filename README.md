 project - this project is adopted from William Stalling simple projects Designed by Dr Ian Graham.The Shell or Command Line Interpreter is the fundamental User interface to an Operating System. The project is to write a simple command-line shell.
1. The shell must support the following internal commands:
i. cd <directory> - Change the current default directory to
 2.
<directory>. If the <directory> argument is not present, report the current directory. If the directory does not exist an appropriate error should be reported. This command should also change the PWD environment variable.
ii. clr - Clear the screen.
iii. dir <directory> - List the contents of directory <directory>. iv. environ - List all the environment strings.
v. echo <comment> - Display <comment> on the display followed by a new line .
vi. help - Display the user manual using the more filter.
vii. pause - Pause operation of the shell until 'Enter' is pressed. viii.
quit - Quit the shell.
ix. The shell environment should contain shell=<pathname>/myshell where
<pathname>/myshell is the full path for the shell executable.
