# Bash Basics

## These are some of the basics points which you need to keep in mind when starting out in Bash

* Bash is very helpful in automating tasks and can help you save time and money
* Any command which can be run in the Command Line can be run in a Bash Script


* The following conventions will allow your computer to excecute Bash scripts
  *  The top of the script file should start with **`#!/bin/bash`** 
  *  When saving your script file, save them in the **`~/bin/`** directory
  *  The script files also need to have the “execute” permission to allow them to be run. To add this permission to a file with filename: script.sh use **`chmod +x script.sh`**
  *  To ensure that scripts in **`~/bin/`** are available, you must add this directory to your **`PATH`** within your configuration file:
**`PATH=~/bin:$PATH`**. Now any scripts in the **`~/bin`** directory can be run from anywhere by typing the filename. 

#### Variables

* Variables are declared by setting the variable name equal to another value. For example, to set the variable greeting to “Hello”, you would use the following syntax:
```console
greeting="Hello"
```
Note: that there is no space between the variable name, the equals sign, or “Hello”.
* To access the value of a variable, we use the variable name prepended with a dollar sign ($). In the previous example, if we want to print the variable value to the screen, we use the following syntax:
```console 
echo $greeting
```

---

# Variables 

To delcare a variable 






