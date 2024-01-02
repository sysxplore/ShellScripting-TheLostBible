# Shell script

A shell Script can be defiend as a file that contains commands; in a laymen language a shell script is a collection of commands, logic, declarations/directives (like shabang), variables, statements, comments, quotations etc which is executable by the shell (the command line interpreter);

# Creating Your First Bash Script

So far we have been running Bash commands directly on the command line. However, for longer or more complex scripts, it is better to create standalone Bash script files.

To create a Bash script:

1. Open a text editor such as Vim, Nano, or Visual Studio Code and create a new file and name it mhscript.sh. Take note of the the .sh extension, this indicates this is a Bash shell script. Too keep it simple I will use nano which comes pre-installed on most Linux distros.

```bash
nano myscript.sh
```

You can also use the touch command to create your script and then open with nano as shown below:
```bash
touch myscript.sh
nano myscript.sh
```

2. Now Start you script with a special line called a shebang. The shebang tells the operating system which interpreter to use to execute the script. The sheband starts with #! followed by the path to the desired interpreter. For Bash scripts, we would use:
```bash
#!/bin/bash
```

3. Write your Bash code below the shebang line. This can include variable declarations, functions, loops, commands like echo, etc. For now we will keep it simple and just write a line that prints "Hello World!":

```bash
#!/bin/bash

echo "Hello World!"
```

When finished, save the file by pressing Ctrl+O. Press Enter to confirm the filename. Exit Nano by pressing Ctrl+X.

Before we can run our first bash script, we need to make it executable first. To do so, use the chmod command as follows:

```bash
chmod +x myscript.sh
```

Once you have given executable permisions to the file, execute the script by running:
  
  ```bash
  ./myscript.sh

  Hello World
  ```
  
  This will run the code in myscript.sh and print "Hello World!" as show above.
  

Congrats you have managed to run your first bash script. Now let's move to the next section.
