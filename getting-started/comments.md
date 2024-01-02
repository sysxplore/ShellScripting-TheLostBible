# Bash Comments

Like any programming language, Bash scripts support writing comments to document your code. Comments are useful for explaining sections of your script, leaving notes for other developers, or commenting out debug code.

There are two types of comments supported:

## Single Line Comments

Single line comments start with a hash/pound symbol (#). Any text after the # on that line will be ignored by the Bash interpreter:

```bash
# This is a single line comment
echo "Hello World" # This line will print Hello World
```

## Multi-line Comments

For comments that span multiple lines, there are two options:

### Using single or double quotes:

```bash
: ' 
This is a multi-line 
comment in Bash
'
```

### Or using heredocs:

Heredocs allow multi-line strings to be captured by using a delimiter. The starting delimiter << must be on its own line and the ending delimiter must be on its own line with no leading whitespace. For example:

```bash
<<COMMENT
This is a multi-line 
comment in Bash 
using heredocs
COMMENT
```

Anything between <<COMMENT and COMMENT will be ignored by Bash as a comment. The delimiter COMMENT can be replaced with any text as long as the starting and ending delimiters match.

Heredocs are useful not just for comments but also for multi-line strings without having to escape newlines (we will discus about this on this section).