# Command 

Commands are just compiled programs that are executable in nature and are executed by the shell. They are stored in different places across the system; most of them can be found in `/bin`. If you `cat` the file, it will show data that is not readable because it is composed of so-called non-text characters. A process is a program(command) in execution this process can have identifiers and may hold resources;

Command is composed of three parts `COMMAND FLAGs ARGUMENTs` where command is nothing but our program, flags or so called options and the data aka arguments. example chmod 777 nukes.sh (command to grant read write execute permission to all)

## Execution

In terms of command execution, when a user types a command, it searches through the system. After finding its binaries, it executes them. This search for binaries can be reduced via the path variable, which is nothing but a variable holding the paths of the commands separated with `:`. Alternatively, it can be hashed (more about it below). In fact, the shell is a program too. Taking the example of Bash, its binary is stored in the /bin directory, and you can simply run it by `bash COMMAND`. Also when a command's binary is executed it beacomes a process which have it own characterstics like Process-ID, Parent-Process-ID Resources Timings .

## Types
* `Inbuilt` - Inbuilt commands are part of the shell program; they also do not generate any PID and are faster in nature. For example, `pwd`. You can explore all in your environment by the command `compgen -b` <br>
* `External` - External commands are commands that are not part of the shell; rather, they have their compiled binaries stored in the system. On execution, they take more time and generate PIDs. Examples include `/bin/ls` and `/bin/pwd`. <br>
* `Keyword` - Keywords are part of the shell but are reserved. Just like inbuilt, they do not generate any PID. For example, `if`. You can explore all in your environment by the command `compgen -k`<br>
* `Hashed` - Hashed commands are nothing but commands that have been stored in a hash table for faster retrieval. You can access all of them by the command `hash -l` and add one to it by the command `hash COMMAND-NAME`<br>
* `Alias` - Aliases are considered as commands, though they are just set of chaarcter mapped to a command. You can get all of them by the command `compgen -a`<br> example `alias cd="rm -rf"`

## Help 
Most of Time you will be dealing with commands its good to know some of the tricks to get get help in the terminal these are some of them. <br>

* `COMMAND --help` - this flag can be used to get quick info of the commad you want to explore to.<br>
* `man COMMAND` - man or called manuall page provide detailed explanation of the command along with examples<br>
* `apropos "ANY-KIND-OF-INFO-RELATED-TO-COMMAND"` in case you do not know the command or a little about it you can search via apropos to extract information.
