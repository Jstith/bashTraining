__Lesson 2: Simple Scripts__
=======================

By: _Jstith_


### Objective

- Learn how to write basic bash scripts
- Learn how to incorporate command line arguments
- Practice using bash scripts to simplify a CTF challenge

### References

- [The Linux Command Line](https://nostarch.com/tlcl2) by No Starch Press

### Introduction

So we use the terminal for pretty much everything. Bash (remember that's the program we interact with using the terminal app) allows us to do pretty much everything on a linux system, and it's usually the fastest and most controlled way to get things done. It is not suprising then, that we use the command line a lot for CTFS, and that many of the tools we use are built for the command line, rather than in GUI applications.

We also like to use scripting in CTFs. You've all heard the term scripting thrown around, and if you're not quite sure what it is, it's probably simpler than you think! Scripting simple means using code (or scripts) to help solve challenges. For example, if you need to find a flag in hundreds of lines of text, rather than scroll for hours you can write a short python script that looks for you.

```python
inFile = open('inHere.txt')

for line in inFile:
    if 'flag' in line:
        print(line)
```

Python is cool, but what if you could write code to help you solve challenges using the language from the command line that we use every day? That is called bash scripting. Bash scripts can run anything you could type in the command line, *and* they leverage the power of loops, comparisons, and the other nice things about using code.

This lesson will teach you how to write basic bash scripts, how to give your bash scripts custom input, and finish with a CTF challenge which would be very difficult to do without your new found powers of bash scripting.

### Editors

Like everything in linux, bash scripts are ultimately just text files. Thus, you can edit them anywhere you want. You could use an editor like VS Code or Atom, but for most short bash scripts a simpler command line program like nano will work. Open a terminal, naviagte to a directory you can practice in, and run the following command:

```bash
nano script.sh
```

The .sh extension indicates to the user and to other programs that the file should be a shell (bash) script. However, in order for the computer to know we want to use bash to execute this script, our first line will be the sha-bang.

### Sha-Bang

The Sha-Banh is a line that starts with a sha (#) and a bang (!). It tells the computer what program we want to use to run the script. Since this is a bash script, we will tell the computer to run our script using bash. Type the following line the first line of nano:

```bash
#!/bin/bash
```

This tells the computer to look in the system binaries directory (bin), where there's an executable titled bash (the same bash we use for our command line) that we want the computer to use to run our script. After that, on a new line, you can enter anything you could run on linux normally. Try whatever you want, such as this echo command:

```bash
#!/bin/bash

echo "Woah! Just like the command line"
```

Use ctl+s and ctl+x to save and exit nano. We're almost ready to run our script, but we need to give ourselves permission to execute the file. By default, we can read and write to any files we create, but we seek higher goals, we want to run it! Type the following command into the command line to give you execute permission for your file:

```bash
chmod +x script.sh
```

Now, if you use `ls -la`, you'll see the file is green and there are some "X"s in the permissions descrptors on the left of the information.
We're ready to run our script. The first (and sometimes only) parameter needed to run a script is it's location. if you just type in 'script.sh', the computer will look for a script in the top level directory (/), and not where you are now. Rather, indicate you want to look in the current directory (.) by typing the following command:

```bash
./script.sh
```

Tada! If all went well you should see the output from your script in the command line, just as if you had typed it in there yourself. Feel free to edit your script (`nano script.sh`) and try some other commands if you want.

### Passing in arguments

Just like in other programming languages, you can use variables in bash. One of the most common ways to use variables is to pass in arguments from the command line when you run your script. You are already very familiar with this, whether you realize it or not. Let's look at an example.

```bash
cat script.sh
```

This command is simple. `cat` outputs the contents of the file you give it. The word `cat` is the command and `script.sh` is a *parameter*. In bash, parameters can be referenced using `$1`, `$2`, `$3`, etc. The first command is $1, the second $2, and so on. Let's go back to your script.sh, and put the following line in the program:

```bash
#!/bin/bash

echo "Check out my argument:"
echo $1
```

Save and exit, and run the script, but this time pass a parameter. Try something like `./script.sh MY_PARAMETER`. You should see your parameter printed in the output of the script.

### The very basics of for loops

This lesson won't get heavily into loops, so here's the quick and dirty of for loops in bash:

```bash
#!/bin/bash
for i in {1..5}
do
   echo "Welcome $i times"
done
```

If you want a better explanation, check out [this guide](https://www.cyberciti.biz/faq/bash-for-loop/). You can put your parameters in the for loop. Let's change our script to print a statement you provide 5 times:

```bash
for i in {1..5}
do
   echo $1
done
```