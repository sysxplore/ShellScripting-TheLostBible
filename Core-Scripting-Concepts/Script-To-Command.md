# Script To command

One can use script in form of commands afterall at end of the day its an executeable. For simple setup one can set up alias for user but that will be a tedious task and will require too much hard-code however one can follow these steps to make it a real one.

Script must be stored in ` /usr/local/bin/ ` for users and ` /usr/local/sbin/ ` for root, script stored in this will not be needed to sprcify paths across system, Make sure it must not have nay extension just a simple file. Write you commands and logic init and make it executeable, hurray you are good to go.

Example 

```bash
# Move to directory we are going to store our script into 
$ cd /usr/local/bin
```

```bash
# Create a file/script with no extension 
$ touch script
```

```bash
# Open any editor and write all the stuff init and its all done !
!/bin/bash
if [[ $# == 0 ]]
then
        echo "PEACE IS THE UNIVERSAL LANGUAGE"
else
        case "$1" in
                --version)
                        echo "∞"
                        exit 0;
                ;;
                --symbol)
                        echo "☮"
                        exit 0;
                ;;
                *)
                        echo "This is the default one"
                ;;
        esac
fi
```

```
# Test/Sample outputs 

$ peace
PEACE IS THE UNIVESAL LANGUAGE

$ peace --version
∞

$ peace --symbol
☮
```