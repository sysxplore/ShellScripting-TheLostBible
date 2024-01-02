# Terminologies
Its necessary to know the correct terminlogies before moving on further since they are mentioned from time to time in the book lack of these can led to confusions, also some myths too.

## Terminologies
* `Terminal` - A terminal is a program that provides an interface for users to interact with the shell, acting as an intermediary between the user and the shell. <br>
* `Console` -  The term "console" was historically used to describe a physical terminal. It is adviced to avoid using console in place of terminal. They are similar but not same.<br>
* `CLI and terminal emulator` - The true cli corresponds to the system's multiuser.target, while in scenarios involving a graphical user interface (GUI) represented
by graphical.target, terminal emulators facilitate access to the terminal and the shell for user interaction. Additionally, modern systems often include a virtual terminal environment, where users can interact with the system through text-based interfaces presented on various virtual terminals.<br>
* `Prompt and command` - Prompt can be defined as sequence of character that can be provided to shell, command is the prompt that is executeable and acceptable by the shell. <br>
* `Shell` - Shell is the command inerpreter which executes the command, the interaction with the shell is provided via terminal. <br>
* `Session` - Session can be defined as the period user interact with the shell, includes login, WORK, logout (simplified)

## Myths 
* `YOU ARE NOT USING LINUX OS` - Its true you are not running Linux OS infact you are running distro based on linux, Linux is a kernel which act as intermediate between user and hardware. Running Linux is same as saying Running transmission rather than car. you can grab kernel information with command `uname -a` not by `/etc/*release*` which related to distro. <br>
* `YOU ARE NOT INTERACTING WITH THE SHELL` - Its true you are not interacting with the shell `directly` rather you are using terminal to interact with the shell, as mention above terminal facilates the interaction with the shell.<br>

Well these might be breking for you but its the truth, it's highly adviced to visit `gnu.org` for more clarification. 