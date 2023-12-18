# Arithmetic operations

Being able to perform basic arithmetic operations like addition, subtraction, multiplication and division is crucial for many scripting tasks. For example, you may need to increment a counter, calculate percentages or totals, or determine if a number is even or odd.

Bash provides several ways to carry out math calculations in your scripts. In this chapter, we will cover the main methods for doing arithmetic in Bash and demonstrate them with examples.

## The expr command

The `expr` command allows evaluating an expression and printing the result. It is an external utility and not a Bash builtin.

The expr syntax looks like:

```bash
expr argument1 operator argument2
```

Here are some examples:

```bash
#!/bin/bash
expr 2 + 2 
# Prints 4

expr 5 - 3
# Prints 2

expr \( 5 + 3 \) \* 2
# Prints 16
```

To save the output to a variable, like any other command you can use command 
substitution to capture the output of expr into a variable:

```bash
result=$( expr 15 - 2 )
echo $result #=> 13
```

Note that bash special characters such as the asterisks must be escaped when using expr to prevent them from being misinterpreted. There must be spaces between the arguments and operator. If you use quotes, the expression will not be evaluated but printed as-is instead.

Take a look at this example:

```bash
#!/bin/bash

expr "6 + 3" #=> 6 + 3 
# if you put qoutes the expression will not be evaluated but printed instead.
expr 3+2 #=> 3+2

# The asterisk has special meaning in bash so we must escape it using \ to remove its special meaning.
expr 5 \* 3

# modulus operator demonstration
expr 15 % 2 #=> 1
```

Because expr is a binary rather than a shell builtin, this method may be slow and a bit cumbersome to use. In a large for-loop, it will fork a new process, which is undesirable. Furthermore, depending on the implementation, the behavior of expr may differ between systems. A better approach for arithmetic calculations is to use let or double parentheses (arithmetic expansion) which we will cover next.

## The let Command

`let` is a Bash builtin that evaluates arithmetic expressions. Its basic syntax is:

```bash
let result=expression
```

The arithmetic expression can take several forms, which we'll go over below. However, the first part is always a variable into which the result is saved.

For example:

```bash
let total=5+4
echo $total # Prints 9
```

This will evaluate the expression and store the result in the `total` variable.

With let, no spaces are needed around the arithmetic operations when not using quotes. But quoting the expression improves readability.

```bash
let "total = 5 + 4" 
echo $total # Prints 9
```

let is useful for incrementing/decrementing variables:

```bash
let counter++
let counter--
```

And assigning result of math operations to variables::

```bash
let "total *= 2" # Total = total * 2
let "value /= 4" # Value = value / 4
```

We can also use variables in expressions

```bash
let "result = 1 + 30"
echo result # 30 + first command line argument
```

So let provides a simple way of doing integer math in Bash scripts.

Like let you can also use the `declare`builtin with the `-i` option to do arithmetic operations

```bash
declare -i x=5+3
echo $x # 8
```

## Arithmetic Expansion $((...))

The Arithmetic Expansion capability of the shell is the recommended and prefered way for evaluating arithmetic expressions in Bash. The built-in shell expansion allows you to perform math calculations by using parentheses. Its syntax is:

```bash
$(( expression ))
```

For example:

```bash
val=$(( 10 + 5 )) # val = 15

(( count++ )) # Increment count

x=$(( a * b )) # x = a * b
```

Notice, you can space out without the need for quotations to improve readebility. Variables within the expression don't need the $ prefix (you can include it if you prefer) which provides a clean format:

```bash
y=$(( x + 3 ))
```

Some advantages of this method:

- More readable than expr or let
- No need to escape * like in expr
- Supports increment ++ and decrement --
- Can combine variables and math intuitively

So arithmetic expansion is so powerful, versatile and recommended approach for arithmetic in Bash scripts.

The square brackets `$[...]`can also do Arithmetic Expansion in Bash, though this notation has been deprecated and should be avoided. Instead, prefer the use of `$((...))` instead. Here is an example of using square brackets to evaluate arithmetic operations:

```bash
val=$[1+5] # val = 6

[ $x -le 10 ] # Less than or equal to comparison
```

## Comparison of Arithmetic Methods

To summarize, here are the main ways to perform integer arithmetic in Bash:

- `$((...))` - arithmetic expansion, preferred method for robust and readable arithmetic operations in scripts.

- `let`  and `declare -i` builtin - useful for incrementing counters and variables

- `expr` - external command, avoid it for math due to awkward syntax

## Bash Drawbacks

We have been performing arithmetic operations on intergers (whole numbers) only up to now, and you may be wondering why. This is due to the fact that bash only supports integers and not floats or decimal numbers. As a result, the arithmetic operations we discussed here only apply to whole numbers. When you need more advanced math capabilities, you can utilize bc (basic calculator). bc is a command line-utility that is used for precision calculation in Linux and bash scripts.

We will not discuss on the usage of this utility as it is beyond the scope of this book.

Now you have a solid understanding of how to leverage Bash for basic math in your shell scripts. With these arithmetic tools, you can calculate totals, iterate through numbers, determine remainders and more to support your scripting logic.