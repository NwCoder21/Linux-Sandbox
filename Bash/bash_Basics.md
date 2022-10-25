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

### Table of comparison operators for numbers which can be used within bash scripts:

| **Operator**|  **In Bash**|
| :-----------: | :-----------: |
| Equal|-eq|
| Not equal|-ne|
| Less than or equalt to|-le|
| Less than|-lt|
| Greater than or equal|-ge|
| Greater than|-gt|
| Is null|-z|

### Table of comparison operators for strings which can be used within bash scripts:

| **Operator**|  **In Bash**|
| :-----------: | :-----------: |
| Equal| == |
| Not equal| != |

* Wrap the variables in quote marks `"` as this will prevent from errors occuring if the variable is null or contains spaces. 

```console
if [ "$name1" == "$name2" ]
```
---

# Loops

Loops are used to iterate through a list and execute an action on every step. 

* 3 different types of loops
 * `for`
 * `while`: keep looping as long as given condition is true 
 * `until`: keep looping until the provided condition is true 

> Loop conditions are written in the same way as if conditiona, between a pair of sqaure brackets.

For example, a script which needs to output an opening greeting three times and then a final greeting would look like:

![image](https://user-images.githubusercontent.com/107522496/197717627-7d74ff02-9ade-4266-8657-53bc0e6fa816.png)

![image](https://user-images.githubusercontent.com/107522496/197717819-370d782e-9b4d-4bb1-956a-8aa47117a930.png)

> Note: in bash scripting, arthmetic statements take place between the $((...)) syntax and the `$` comes before the brackets, not directly before the variable.

This script could als be written using an `until` loop. For example: 

![image](https://user-images.githubusercontent.com/107522496/197718899-a1bb5113-2d8c-4f0d-bdd1-791045fe5b3d.png)

and we would get the same output:

![image](https://user-images.githubusercontent.com/107522496/197719191-f3807c58-33f5-4880-93bb-ca5ec5305651.png)

---

# Inputs

One way to take input from user, and add it to a variable, is by using the `read` keyword is used. For example: 
```console
echo "What is your name"
read userName 
```

Another way to take input from a user is by using arguments. These are entered by the user when running the script, and accesssed usinng $1, $2, $3, etc.

> Note: these are 1 indexed. 

For example: 

![image](https://user-images.githubusercontent.com/107522496/197723927-1eeb9138-4427-4aaf-8db8-dafd6ad8ad12.png)

![image](https://user-images.githubusercontent.com/107522496/197723988-3f0af7e1-d2cc-4b44-9f9f-6598322ed562.png)

To access all the arguments entered by the user, we can use `$@`. For example: 

![image](https://user-images.githubusercontent.com/107522496/197726592-e248128f-4943-46eb-bf33-6db7dadb3af7.png)

![image](https://user-images.githubusercontent.com/107522496/197726686-e454ec60-8d8e-4407-ab29-64e7e4ac929c.png)





