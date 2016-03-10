# About this project

I'm a fairly new developer without much knowledge of bash and was hoping make a small bash script. I have a background in c++ and javascript and wanted a quick format guide that would take me from those languages to the bash equivalents.

I started just trying to wing it myself but had a little trouble. So, I googled it to find out more and had a hard time finding a quick "Cheatsheet" showing the proper syntax. So, I thought, why not make one.

So I've tried to curate a few resources and pull the information to make a complete beginner's guide.

I hope to include example scripts eventually that you can download and just take and modify. For now though, it's just this simple guide.

It's a rough piece of work but hopefully it provides some usefulness to someone.

Enjoy!

# Basics

Start files with: `#!/bin/bash`

Comments: `#This is a comment`

create a variable: `VARIABLE="hello world"`

NOTE: You cannot have spaces around the "=" sign. If you do it won't evaluate.

reference a variable: `$VARIABLE`

# Command Line Arguments

Name of the script: `$0`

1st command argument: `$1`

2nd command argument: `$2`

etc.

## get output from a command

```
#!/bin/bash
OUTPUT="hello world"
OUTPUT="$( ls )"
echo $OUTPUT
```
This program sets OUTPUT to "hello world". It then re-sets it to the ouput of the command `ls`. So in the end, this script will print out the output of ls, not "hello world".

# Basic Commands

Read input and into variable `read VARIABLE`

Print out to the console `echo "Hello World"` or `printf "Hello World"`

Print out to a file `echo "Hello World" >> path/to/file`

Delay for 1 second `sleep 1`

# Conditional Statements:

## if statements

```bash
#basic case
if ["foo" = "foo"];
  then
    echo "these are equal"
fi

# Use parentheses when working with integers
if (($COUNT < 10))
  then
    echo "Numbers are equal"
fi

# Use square-brackets when working with strings
if [[$VARIABLE = "string"]]
  then
    echo "Strings are equal"
fi
```

## if else block

```bash
if [[   ]]
    then
      echo "true"
  elif [[   ]]
    then
      echo "also true"
  else
      echo "false"
fi
```

## case statements

```bash
case $1 in
  "string1")
    echo "1st condition met"
    ;;
  "string2")
    echo "2nd condition met"
    ;;
  *)
    echo "This is the 'default' case"
  ;;
esac
```

# Loops

## while loops

`while` runs the loop while the condition is true

```bash
#basic while true loop
while true
  do
    echo "Infinite loop"
done
```

## until loops

`until` runs the loop until the condition is true (i.e. while the condition is false).

```bash
COUNT=0
until ((COUNT > 10))
do
  echo "$COUNT"
  ((COUNT ++))
done
echo "Outside until loop"
```

## for loops

c++ type for loops are done with a counter and a while loop.

```bash
#for type while loop
COUNT = 10
while(( COUNT > 0))
  do
    echo "$COUNT"
    ((COUNT --))
done
echo -e "\n\nFIRE!!"
```

## for each loops

bash `for` loops iterate through a list of objects and perform an action for each item.

```bash
for F in $(ls)
do
  [! -f $F] && continue
  DT=$(stat $F)
  echo ""
done
```

# Functions

```bash
function_name () {
    command...
}
```

# Resources

[Beginner's Guide](http://tldp.org/LDP/Bash-Beginners-Guide/html/intro_01.html)

[How To Guide](http://tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-7.html)

[Youtube Tutorials](https://www.youtube.com/watch?v=C2LPwIvIEjo&list=PLfQDYTKBwSuaSPBHRR9CE_v1hTkaR_V6g&index=5)
