# Shell script
A shell Script can be defiend as a file that contains commands (GNU language) ; A shell script is a collection of commands, logic, declarations/directives (like shabang), variables, statements, comments, quotations etc which is executable by the shell (the command line interpreter);

## How shell script executes 
On invoking a shell script a new non interactive child shell session is spawned in this session the commands are executed in the sequence they are defined in the shell script. During the execution all the input is taken form parent shell session and the output is also redirected to parent shell session.
when the script execution is complete the child session gets completed.

## Creating Your First Bash Script
As we know a shell script is file that contains commands (GNU) lets create a shell script.

Step 1: create a file which will be our shell script: 
```bash
touch script
```

Step 2: Input the file in any desired code editor you like 

Step 3: Before writing the set of commands input a shebang (A sheband is a directive which defines which shell is going to executing the current script its syntax is #!PATH-TO-DESIRED-SHELL ) 
```bash
#!/bin/bash
```

Step 4: Now we have our script and have described which shell is going to execute it now we can focus on heavy-lifting and start writing all the commands we want to be executed.

```bash
#!/bin/bash
echo "This script is cool God dammmm" 
# This is a comment 
whoami 
```

step 5: We have prepeared our script lets execute and enjoy for execution we can can provide the absolute path if we are in a different location or provide the script name if we are in the current working directory

Invoking the script 
```
bash PATH-TO-SCRIPT
```

Output of the script
```bash
This script is cool God dammmm
myselfakashagarwal
```

<hr> 

Thats it .. with this you have completed the basic needs to learn writing God level shell scripts you can move onto to the core concepts, best of luck and keep nuking.




