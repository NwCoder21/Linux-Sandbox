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

# Variables

* Variables are declared by setting the variable name equal to another value. For example, to set the variable `greeting` to “Hello”, you would use the following syntax:
```console
greeting="Hello"
```
> Note: there should be no spaces between the variable name, the equals sign, or “Hello” (the value).

* To access the value of a variable, we use the variable name prepended with a dollar sign ($). In the previous example, if we want to print the variable value to the screen, we use the following syntax:
```console 
echo $greeting
```
---

The below script would add the value `Hello World!!` to the variable `openingGreeting` and then print it out to the screen. 

![image](https://user-images.githubusercontent.com/107522496/197706656-92f5ddfe-05e4-49be-8bf0-509f70767d0d.png)

---

# Conditionals 

* Conditionals are used to control what set of commands are run within a script. 
* An if statement will start with a `if` followed by the condition, which will be in between a pair of square brackets.

> Important! - Remember to leave a space betweeen both of the square brackets and the conditional statement.

![image](https://user-images.githubusercontent.com/107522496/197709581-4ebe6e00-47fd-494d-b9ca-11b6cc6a82f1.png)

* `then` will start the code which is run if the condition is met.
* `else` will start the code whcih is run if the condition is not met.
* `fi` the condition is closed with a `fi`, this is `if` but backwards. 

---

# Comparison Operators 

> Table of comparison operators for numbers which can be used within bash scripts:

| **Operator**|  **In Bash**|
| :-----------: | :-----------: |
| Equal|-eq|
| Not equal|-ne|
| Less than or equalt to|-le|
| Less than|-lt|
| Greater than or equal|-ge|
| Greater than|-gt|
| Is null|-z|

When comparing strings: 

| **Operator**|  **In Bash**|
| :-----------: | :-----------: |
| Equal| == |
| Not equal| != |

* Wrap the variables in quote marks `"` as this will prevent from errors occuring if the variable is null or contains spaces. 

```console
if [ "$name1" == "$name2" ]
```

