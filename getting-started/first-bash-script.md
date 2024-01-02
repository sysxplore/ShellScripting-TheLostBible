# Creating Your First Bash Script

So far we have been running Bash commands directly on the command line. However, for longer or more complex scripts, it is better to create standalone Bash script files.

To create a Bash script:

1. Open a text editor such as Vim, Nano, or Visual Studio Code and create a new file and name it mhscript.sh. Take note of the the .sh extension, this indicates this is a Bash shell script. Too keep it simple I will use nano which comes pre-installed on most Linux distros.
  
  ```bash
  nano myscript.sh
  ```
  
2. Start you script with a special line called a shebang. The shebang tells the operating system which interpreter to use to execute the script. For Bash scripts, we would use:
  
  ```bash
  #!/bin/bash
  ```
  
3. Write your Bash code below the shebang line. This can include variable declarations, functions, loops, commands like echo, etc. For now we will keep it simple and just write a line that prints "Hello World!".
  
  ```bash
  #!/bin/bash
  
  echo "Hello World!"
  ```
  
4. When finished, save the file by pressing Ctrl+O. Press Enter to confirm the filename. Exit Nano by pressing Ctrl+X.
  
5. Before we can run our first bash script, we need to make it executable first. To do so, use the chmod command as follows:
  
  ```bash
  chmod +x myscript.sh
  ```
  
  To execute the script type:
  
  ```bash
  ./myscript.sh
  ```
  
  This will run the code in myscript.sh and print "Hello World!".
  

Congrats you have managed to run your first bash script. Now let's move to the next section.