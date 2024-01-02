# Operators

Operators allow you to perform operations on values and variables in Bash. Bash provides various types of operators for different purposes:

- Arithmetic Operators
- Assignment Operators
- Relational Operators
- Logical Operators
- Bitwise Operators
- Ternary Operator

In this section you are going to learn about all these operators in detail

## Arithmetic Operators

Arithmetic operators allow you to perform mathematical operations on integers. In other words, arithmetic operators allow combining integer variables and values to produce a new integer result.

The following table provides a list of all the arithmetic operators available in bash.

| Operator | Description         | Example   |
| -------- | ------------------- | --------- |
| +        | Addition            | `$a + $b` |
| -        | Subtraction         | `$a - $b` |
| *        | Multiplication      | `$a * $b` |
| /        | Division            | `$a / $b` |
| %        | Modulus (remainder) | `$a % $b` |

The addition, subtraction, multiplication, and division operators work as expected for mathematical operations. 

The modulus (%) operator returns the remainder when dividing two integers. This is useful for checking if a number is even or odd, among other use cases.

## Assignment Operators

The assignment operators allows storing values or the result of an expression into a variable.

| Operator | Description         | Example |
| -------- | ------------------- | ------- |
| =        | Simple assignment   | `a=5`   |
| +=       | Add and assign      | `a+=2`  |
| -=       | Subtract and assign | `a-=3`  |
| *=       | Multiply and assign | `a*=4`  |
| /=       | Divide and assign   | `a/=5`  |
| %=       | Modulus and assign  | `a%=6`  |

Simple assignment allows storing values in a variable. Combined assignment operators like += and -= allow modifying variables with shorthand instead of rewriting the full expression. For example, the add and assign operator (+=),  adds the right operand to the left operand and stores the value to the left operand. Look at this

- a+=b is the same as  a = a + b

- a-=b is the same as a= a - b

- a*=b is the same as a= a \* b

- a/=b is the same as a= a / b

- a%=b is the same as a= a % b

## Relational Operators

Relational operators allow comparing integers and strings to evaluate conditions.

| Operator | Description                     | Example            |
| -------- | ------------------------------- | ------------------ |
| -eq      | Equal to                        | `[ $a -eq $b ]`    |
| -ne      | Not equal to                    | `[ $a -ne $b ]`    |
| -gt      | Greater than                    | `[ $a -gt $b ]`    |
| -ge      | Greater than or equal to        | `[ $a -ge $b ]`    |
| -lt      | Less than                       | `[ $a -lt $b ]`    |
| -le      | Less than or equal to           | `[ $a -le $b ]`    |
| <        | Less than (strings)             | `[ "$a" < "$b" ]`  |
| <=       | Less than or equal (strings)    | `[ "$a" <= "$b" ]` |
| >        | Greater than (strings)          | `[ "$a" > "$b" ]`  |
| >=       | Greater than or equal (strings) | `[ "$a" >= "$b" ]` |
| ==       | Equal to                        | `[ $a == $b ]`     |
| !=       | Not equal to                    | `[ $a != $b ]`     |

 -eq, -ne, -gt, -ge, -lt, and -le work on integers, while <, <=, >, and >= work on string sorting order. These are commonly used in if statements and loops to control program flow. The equal (==) and not equal (!=) operators are useful for comparing integers.

## Logical Operators

Logical operators allow combining and negating conditional expressions.

| Operator | Description | Example                         |
| -------- | ----------- | ------------------------------- |
| !        | Negation    | `! [ $a -eq $b ]`               |
| &&       | AND         | `[ $a -eq 5 ] && [ $b -eq 10 ]` |
| \|\|     | OR          | `[ $a -eq 5 ] \|                |

The NOT operator (!) inverts a true condition to false or a false condition to true. The AND operator (&&) evaluates to true if both operands are true, while the OR operator (\|\|) evaluates to true if either operand is true. These allow creating complex conditional logic in scripts.

## Bitwise Operators

Bitwise operators manipulate integers at the bit level.

| Operator | Description | Example    |
| -------- | ----------- | ---------- |
| &        | Bitwise AND | `$a & $b`  |
| \|       | Bitwise OR  | `$a \| $b` |
| ~        | Bitwise NOT | `~$a`      |
| ^        | Bitwise XOR | `$a ^ $b`  |
| <<       | Left shift  | `$a << 2`  |
| >>       | Right shift | `$a >> 2`  |

Bitwise operators treat integers as binary strings and set, unset, or toggle bits at specific positions. This allows bitmasking, toggling, and shifting values for flags and low-level binary operations.

## Ternary Operator

The ternary operator allows simple conditional expressions.

| Syntax                                 | Description                                                             |
| -------------------------------------- | ----------------------------------------------------------------------- |
| `<condition> ? <if true> : <if false>` | Evaluates test condition and returns the "if true" or "if false" result |

The ternary operator is structured as `condition ? resultIfTrue : resultIfFalse`. It tests the given condition and returns the specified result depending on whether the condition evaluated to true or false. This provides a concise way to assign values based on conditions.

# Summary

Bash provides a set of operators including arithmetic, relational, logical, bitwise, assignment, and ternary operators. These allow performing mathematical computations, evaluating conditions, combining expressions, manipulating bits, assigning values, and conditional ternary expressions within Bash scripts. Understanding the operators available is key to effectively writing conditional logic, numeric operations, and data manipulations in Bash.
