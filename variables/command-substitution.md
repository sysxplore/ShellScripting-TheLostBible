# Command Substitution in Bash

Command substitution allows you to use the output of a command as an argument to another command or variable assignment. This is useful when you need to dynamically set values based on system information or external commands.

There are two ways of doing command substitution:

- $( )
  
- Using backticks ``.
  

For example:

```bash
today=$(date +%F)

echo "Today's date is $today"
```

This runs the date command, captures its output, and assigns it to the \$today variable. The $today variable is then printed using the echo command.

Without command substitution:

```bash
today=date +%F
echo "Today's date is $today"
```

This would print the literal string "date +%F" rather than running date and capturing its output.

Some examples of using command substitution:

- Set variables dynamically based on system info:

```bash
count=$(ls | wc -l) 

dirsize=$(du -sh /home)
```

- Use command output as arguments to other commands:

```bash
grep "foo" $(find . -name '*.txt')

tar -cvzf $(date +%F).tar.gz /mydir 
```

Command substitution allows you to integrate the output of multiple commands together in your Bash scripts. This leads to more dynamic and flexible scripts that can query the system and react to external commands. It is an essential technique for intermediate to advanced Bash scripting.