
# Variables 

Variables in shell scripting can hold integers, booleans, text, file paths, functions, bitcoin anything just name it one can perform tones of operations on them to get desired results. Its a scripting language so type of the variable is defined dynamicially in normal cases, however one can define the type during declaration.


## Declaration, Initilization and Use

The general declaration of a variable includes a VARIABLE-NAME ASSIGNEMNT-OPERATOR VALUE-IN-QUOTES  with no type defined. However
one can declare variable in various ways using the ` delcare ` command which includes declaration options like integer, array, read only etc. Delcaration of variables using the ` declare ` command results in better backward compatibility, efficiency and readibility. As a better practice initilize a variable with "" nothing during the time of declarations. Below are the declaration type-examples 

`All in one`

```bash
VARIABLE="DESIRED-VALUE"             # syntax
PLANET="Urnus"                       # example
echo $PLANET                         # use
``` 

`Strings or character`

```bash
declare VARIABLE="DESIRED-VALUE"     # syntax
declare GALAXY="Milkyway Galaxy"     # example
echo $GALAXY                         # use
```

`Integers`

```bash
declare -i VARIABLE="DESIRED-VALUE"  # syntax 
declare -i GRAVITY="9"               # example
echo $GRAVITY                        # use
```

`booleans`

```bash
# booleans are just comprised of true or fasle binaries not true or false strings 
IS_HABITABLE=false                  # example of false 
IS_BEAUTIFUL=true                   # example of true
echo $HABITABLE                     # use
```

`Constants`

```bash
declare -r VARIABLE="DESIRED-VALUE"  # syntax  
declare -r COLOR="BLUE"              # example
echo $COLOR                          # use
```

`Array`

```bash
declare -a VARIABLE_NAME=("ZEROth Index" , "ONE", "TWO" )   # syntax
declare -a PLANETS=("EARTH", "URANUS")                      # example

# Syntax                             #  Operations 
${ARRAY-NAME[*]}                     # All elements
${#ARRAY-NAME[@]}                    # size of the array
${ARRAY-NAME[INDEX]}                 # indexed operation

# Example                            # Task
echo ${PLANETS[*]}                   # Prints all elements of the array
echo ${#PLANETS[@]}                  # Prints size of the array
echo ${PLANETS[0]}                   # Prints elements at 0th index 
```


## Scope of the variables 
Variables defined have defined accessibility in respect to the scope they are defined in.
It is to be noticed that variables can be defined in the session or in the shell script so the scope differs accordingly. Moving on, we have three major scopes including 

`local` <br> 

Variables with local scope are limited to the block they are defined in. For example if a variable is declared as local in the loop it will not be accessiable outside of the loop. Local variables are declared with the help of local.

local variables cannot be defined in the session; they are limited to the logical block of the shell script.

Declare local variables in script 
```bash
# Only for shell scripts 
local VARIABLE="VALUE"              # syntax   
local CITY="Uthopia"                # example 
```

`global` <br>

Global variables are accessiable by all the process running in the session but not the child processes. 

Global variables when declared in the shell script will be accessiable throught the shell script it will be accessiable by all the blocks like loops and other how ever they loose their existance outside the shell script.

Global variables when declared in the session will be accessiable throught the session. But not the child processes for example if a shell script using that variable is executed it will read an empty variable.

Declare global variables in scripts and session 
```bash
VARIABLE="VALUE"                  # syntax for both in session and script 
```

Source variables as global variables using the source command from a file/script 
```bash 
source PATH-TO-FILE-CONTAINING-VARIABLES   # syantx for session 
```

`environment` <br>
Environment variables are the variables that are accessiable throught the current session, child sessions also shell scripts. One can check all of the environment variables with the help of env command. The environment variables are defined with the help of export builtin.

Environment variables will not be accessiable outside the script until they are sourced just like we did in global 

Environment variable declared in the session will be accessiable to the shell scripts child session aka everything. 

Declaring a environment variables 
```bash
export VARIABLE="VALUE"        # syntax 
export PS1="\u @ \w :"         # example 
```

Sourcing a environment variable script
```bash
source PATH-TO-FILE-CONTAINING-VARIABLES  # syntax for the session 
```

## Presistence of the variables 

If a user simply declares variable in the session and ends the session the variables will lose its existance, similarly variables declared in the scrip/tfile lose their existance outside the script so we have to source the variables in order to use them. Leading to situation where user have to source every time in case of file and command to re declare every time in case of session.

However these can be avoided using .bash_profile file present in the home directory; this file is executed every time a new session is spawned we can define our source command for all the file which contains our global and environment variables.

## User Input 
To input the values at the run time by the user read command is used along with read positional parameters are used to gather user input in basic scenarios. 

Read user input during the execution using read 
```bash 
read -p "DESIRED MESSEGE TO BE PROMPTED BEFORE INPUT" VARIABLE-TO-STORE-INPUT 
```

Positional parameteres: positional parameters are passed during the invocation of the script. each argument is mapped with a position as they are defined in which can be used within the script.

Sample script with name position present in current working directory 
```bash
#!/bin/bash
# This is a script which prints three arguments passed via command line 
echo "first position $1"
echo "second position $2"
echo "third position $3"
```

Sample execution from script working directory 
```bash
bash position "player69" "player420" "player1945" 
```

Result 
```bash
first player69
second player420
third player1945
```

## Variable Quoting and Expantion 

`Case 1`: seperating variables from the other tokens 

When the variables are used along with multiple tokens the statemets tend to lose their readibility and also may let to anormalities. 

Scenario 
```bash
#!/bin/bash
variable="value"
echo "$variableIS THE VALUE OF THE VARIABLE "
```
Explanation 
In the above example the script fails as the variable collides with the remaining message to prevent this we use curly braces to seperate the tokens.

Solution 
```bash
#!/bin/bash
variable="value"
echo "${variable}IS THE VALUE OF THE VARIABLE "
```

`case 2`: splitting of the variables' content 

The content of the variable gets splitted if they are sperated by tabs or spaces this situation occur during the time of iterative statements. Its great feature but the problem comes when we have to perform action on the combined set of values multiple times.

Scenario 
```bash
#!/bin/bash
variable="value1 value2 value3 "
for element in ${variable}
do 
   echo ${element}
done
# prints 
# value1
# value2
# value3
```

Explanation 
In the above script the content of the variable gets splitted and the each value is print individually to prevent this kind of behaviour one can enclose the variable within quotes. 

Solution 
```bash
#!/bin/bash
variable="value1 value2 value3 "
for element in "${variable}"
do 
   echo ${element}
done

# prints value1 value2 value3 
```

<hr> 

Move to the other parts of the core concepts and keep nuking 