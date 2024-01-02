# Shell script

A shell Script can be defiend as a file that contains commands; in a laymen language a shell script is a collection of commands, logic, declarations/directives (like shabang), variables, statements, comments, quotations etc which is executable by the shell (the command line interpreter);

# First Shell Script 

1.Create a new file: This new file will be our shell script which will contain commands, make sure it ends with ` .sh ` extension 

```bash
touch script.sh
```
2.Make it executeable by chmod command for precaution we are allowing executeable permissions to both user and group

```bash
chmod u+x,g+x script.sh
```

3.Open file and write: you can use any editor you are comfortable with for current I'll be moving with VI

```bash
vi script.sh
```
4.Press `i` after it you will move to edit mode 

5.Insert shebang: A shebang is a declarative which is used to tell parent session which interpreter should be used to execute the script its goes like this #! in succession with path to desired interpreter combining togetehr to result in #!/PATH-TO-DESIRED-INTERPRETER ; example #!/bin/bash

```bash
#!/bin/bash
```

6.Inset commands you wanna execute 
```bash
#!/bin/bash
echo "Hello World"
```

7.After you have written all of the stuff;  press `escape` key and type `:wq` and enter

8.Now your shell script have been made just execute it with command 
```bash
bash ./script.sh
```

9.Output
```bash
Hello world
```

Hurray !! 👍🏼 After your Hello World ritual you are good to move to core concepts of shell scripting 