# Flow Control
Flow - control is one of the most important aspect of shell Scripting without them a script will be nothin just a collection of statements, so in order to add logic and flow to script Flow-Control statements are used. These flow control statements can be:
- Iterative - execution of same block multiple times in respect condition, 
- Conditional - execute block which satisfies the condition
- jump - chnage the control
- function - executeable units which can accept arguments. 

To move with Flow control statements these flags can be used to perform comparisons 
```bash
-le   # for less then or equall
-ge   # for greater then or equall
-gt   # for greater than 
-lt   # for less than 
-eq   # equals
-ne   # not equals 
!     # for inverting 
true  # keyword representing false
false # keyword representing true
```

## Conditional Statements 

### ` if ` 

Syntax

```text

if [[ condition ]]
then
   commands 
fi

```
Example 

```bash
#!/bin/bash
condition="true"
if [[ $condition -eq "true" ]]
then
    echo "Condition satisfied"
fi
```


### ` if elif `
If the condition satisfies the if block will be executed otherwise the commands present in the else block will be executed 

Synatx

```text

if [[ condition ]]
then 
   commands 
else
   commands
fi

```
Example

```bash
#!/bin/bash
conditiion="true"
if [[ ! $condition -eq "true" ]]
then
    echo "condition satisfied"
else
    echo "condition failed"
fi
```

### ` if elif else` 
The respective blocks are executed on the basics of the condition they satisfies but if now condition satisfies the else block will be executed  

Synatx

```text
if [[ condition ]]
then 
   commands
elif [[ commands ]]
then 
   commands 
else
   commands
fi
```

Example 

```bash
#!/bin/bash
condition="maybe"
if [[ $condition -eq true ]]
then 
   echo "Condition is satisfled and is true"
elif [[ $condition -eq false ]]
then 
   echo "condition is satisfied and is false" 
else
   echo "condition failed"
fi
```

### ` Switch Case `  
In case the constants are evaluated, if the constant matches the choice provided that respective block is executed. If any of the condition fails to satisfy the defult case denoted by `*` is executed.

Synatx 

```text
case "${choice}" in
    constant1)
        commands
        ;;
    constant2)
        commands
        ;;
     *)
        commands
        ;;
esac
```
Example 

```bash
#!/bin/bash
choice="23"
case "${choice}" in
    23)
        echo "The case with value 23 executes"
        ;;
    32)
        echo "The case with value 32 executes"
        ;;
     *)
        echo "None of the case matched"
        ;;
esac
```

### ` Select `
The select is quite the iterative one yet its conditional on user side. Init out of multiple options one is selected by user according to which the respective block executes 

Syntax

```text
select option in "Option 1" "Option 2" "Option 3" "Quit"
do
    if [[ "$option" == "Option 1" ]]; then
        echo "You chose Option 1"
    elif [[ "$option" == "Option 2" ]]; then
        echo "You chose Option 2"
    elif [[ "$option" == "Option 3" ]]; then
        echo "You chose Option 3"
    elif [[ "$option" == "Quit" ]]; then
        echo "Quitting..."
        break
    else
        echo "Invalid selection"
    fi
done
```

```bash
#!/bin/bash
select option in "eat" "sleep" "code" "Quit"
do
    if [[ "$option" == "eat" ]]; then
        echo "eat a apple "
    elif [[ "$option" == "sleep" ]]; then
        echo "slept for two hours"
    elif [[ "$option" == "code" ]]; then
        echo "coded for two hours"
    elif [[ "$option" == "Quit" ]]; then
        echo "exited"
        break
    else
        echo "Wrong selection"
    fi
done
```

## Iterative Statements 

### `For each loop `
The loop will run will the range of input until condition fails 

Syntax

```text 
for element in ${elements}
do
  commands 
done 
```
Example 

```bash
#!/bin/bash
elements="1 2 3 4 5"
for element in ${elements}
do
	echo ${element}
done
```

### ` For loop `
The loop will run till the control variable fails to satisfy the condition

Syntax

```text
for((i=0;i<5;i++))
do
  commands
done
```
Example 

```bash
#!/bin/bash
for((i=1;i<=5;i++))
do
	echo " hi "
done
```

### ` while loop `
The loop will run continiously if condition satisfies

Syntax

```text
while [[ condition ]]
do
  commands
done 
```
Example 

```bash
#!/bin/bash
x=5 
while [[ $x != 0 ]]
do
	echo "yo "
	x=$((x-1))
done 
```

### ` until loop `
The loop will run until the condition satisfies 

Syntax

```text
until [[ condition ]]
do
  commands
done 
```
Example 

```bash
#!/bin/bash
until [[ $x -gt 10 ]]
do
	echo "hay "
	x=$((x+1))
done
```

## Jump statements 

### ` break `

Break can be used to move the control out of the block is currently in 

Example

```bash
#!/bin/bash
for i in {1..5}
do
    echo $i
    if [[ $i == 3 ]]
    then
        break
    fi
done
```

### ` continue `
continue can be used to skip a set of satatements 

Example 

```bash
#!/bin/bash
for i in {1..5}
do
    if [[ $i == 3 ]]
    then
        continue
    fi
    echo $i
done
```

## Others 

### ` Function ` 
Functions in shell scripting are reusable blocks of code that can be called with arguments. 

Syntax 

```text
function_name() {
    commands
}

# Call the function
function_name argument1 argument2
```

Example 

```bash
#!/bin/bash
print_message() {
    echo "Hello, $1!"
}

# Call the function
print_message "World"
```

