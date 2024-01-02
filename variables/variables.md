# Bash Variables

Variables are an essential part of any programming language, allowing you to store data and reference it later. Bash shell scripts are no exception, providing several types of variables that serve different purposes.

## User Defined Variables

These are variables defined by the user in a Bash script.

### Declaring Variables

When declaring a variable in Bash, it is important to follow these naming rules:

- Variable names can contain letters, numbers, and underscores.
- The first character must be a letter or underscore.
- Names are case-sensitive - MYVAR and myvar would be different variables.
- Avoid using Bash reserved keywords as variable names.

To assign a value to a variable, use the equals sign (=):

```bash
myvar="Hello World" 
```

When declaring variables there should be no spaces between the variable

name and equal sign and between the equal sign and the variable value.

This will throw and error

```bash
myvar = "Hello World"
```

Access the value of a variable by prefixing it with a dollar sign ($):

```bash
echo $myvar 
```

This would print "Hello World" to the terminal.

It is crucial to keep in mind that when referencing a variable value, the dollar sign is used, but when referencing the variable to assign a value, the dollar sign is not used.

### Unsetting Variables

To unset a variable, use the unset command:

```
unset myvar
```

The variable is deleted and cannot be recovered.

## Bash Built-in Variables

Bash provides special variables that are predefined and used to reference specific values. The table below shows a list of these special variables

| Parameter | Description |
| --- | --- |
| \$1…\$9 | Parameters 1 to 9. |
| $0  | Stores the name of the script file or the current shell name. |
| $1  | represents the first argument. |
| ${10} | Positional parameter 10. |
| $#  | Number of positional parameters |
| $*  | stores all the arguments. |
| $$  | Process id of the current shell. |
| $@  | All arguments, starting from first. |
| $-  | Current options. |
| $_  | Last argument of the previous command |
| $!  | The process ID (PID) of the most recently executed background pipeline (like started with command &) |
| $?  | Status of the most recently executed foreground-pipeline (exit/return code) |

## Environment Variables

These variables are part of the shell environment and they store data about the current session and working environment (thus the name).

There are two types of environment variables in bash:

- Global variables - Visible from the shell session and any child subshells
- Local variables - Only visible within the shell that defines them.

### Global Variables

Global variables are useful for apps that spawn child subshells needing parent shell infomation.

The env and printenv commands can be used to print global variables.

Some examples:

- $HOME - Home directory of the user
- $PATH - List of directories searched for commands
- $SHELL - Current shell being used

Environment variables are usually defined in upper-case and are useful to customize the environment for users and processes. They can be defined at login or using the export command:

```bash
export MYVAR="value"
```

Like user defined variables you can also unset global variables using the unset command:

```bash
unset MYVAR
```

> Making changes or unsetting the a global variable doesn't affect the parent gloabal variable.

## Looking at Local Variables

Local variables are only visible within the shell that defines them. The Linux system sets default local variables, but you can also define your own. Local variables typically use lowercase letters.

To see local variables, use the set command, which shows local, global, and user-defined variables:

```bash
set
```