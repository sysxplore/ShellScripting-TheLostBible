# Shell Script 
A shell Script can be defiend as a file that contains commands; in a laymen language a shell script is a collection of commands, logic, declarations/directives (like shabang), variables, statements, comments, quotations etc which is executable by the shell (the command line interpreter);

User instruct to run the shell script in the 'parent' session. This 'parent' session spawns a new 'child' session, which will run the shell script. During the execution, if input is needed, it is asked from the 'parent' session. Also, the output and errors are displayed in the 'parent' session.  

## Shebang 
A shebang is a declarative which is used to tell parent session which interpreter should be used to execute the script its goes like this `#!` in succession with path to desired interpreter combining togetehr to result in #!/PATH-TO-DESIRED-INTERPRETER ; example `#!/bin/bash`

## Bash Comments
Comments are the tokens which are ignored by the interpreter during execution. Bash scripts support writing comments in two ways single line and multiline to document your code. Comments are useful for explaining sections of your script, leaving notes for other developers, or commenting out debug code.

### hastag for single line comments
Single line comments start with a hash/pound symbol (#). Any text after the # on that line will be ignored by the Bash interpreter but they must be remain in a single any line break will make them invalid:

```bash
# This is a single line comment
echo "Here we go again.." # after hashtag all stuff is comment too 
```

### Quotes for myltiline comments:
Anything will be considered as comment as long as it lies between quotes which is succeed after a colon : 

```bash
: ' 
Oh my god.....
I did it 
'
```

### Heredocs for multiline comments:
Heredocs allow multi-line strings to be captured by using a delimiter. The starting delimiter << must be on its own line and the ending delimiter must be on its own line with no leading whitespace. For example: 

Anything between <<COMMENT and COMMENT will be ignored by Bash as a comment. The delimiter COMMENT can be replaced with any text as long as the starting and ending delimiters match.
```bash
<<COMMENT
Mamma Imma criminal 
crimidal
creaminall
COMMENT
```

## Variables 
Variables can be used to hold value on which we can perform operations; these operations can be done with statements. The value of the variable can be extracted using dollar sign before it.

```bash
# A simple variable example 
bank_balence="69¢"
echo "I have $bank_balence in my account but 20$ is 20$"
```


## Statements 
Statements are used to perform operation on/with variables or commands these can be iterative like loops or conditional like switch case or others like functions we will move through all of them in upcomming dedicated lessons.


## Commands 
Commands are the basic building blocks of the shell script nearly every thing composed of it is a command even [[ is a command; when a shell script is executed it moves from one command to other from top to bottom in a sequence, the commands init when executed generates pid and other stuff but they dies as soon as child session compleates its cycle and dies. we have gone through them in introduction session.