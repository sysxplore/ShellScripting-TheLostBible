# Bash Comments

Comments are the tokens which are ignored by the interpreter during execution. Bash scripts support writing comments in two ways single line and multiline to document your code. Comments are useful for explaining sections of your script, leaving notes for other developers, or commenting out debug code.

### hastag for single line comments
Single line comments start with a hash/pound symbol (#). Any text after the # on that line will be ignored by the Bash interpreter but they must be remain in a single any line break will make them invalid:

```bash
# This is a single line comment
echo "Comments are Cool" # after hashtag all stuff is comment too 
```

### Quotes for myltiline comments:
Anything will be considered as comment as long as it lies between quotes which is succeed after a colon : 

```bash
: ' 
This is a 
multi line comment 
'
```

### Heredocs for multiline comments:
Heredocs allow multi-line strings to be captured by using a delimiter. The starting delimiter << must be on its own line and the ending delimiter must be on its own line with no leading whitespace. For example: 

Anything between <<COMMENT and COMMENT will be ignored by Bash as a comment. The delimiter COMMENT can be replaced with any text as long as the starting and ending delimiters match.
```bash
<<COMMENT
This is a multiline 
comment using 
heredocs
COMMENT
```

