
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

<hr> 

Move to the other parts of the core concepts and keep nuking 