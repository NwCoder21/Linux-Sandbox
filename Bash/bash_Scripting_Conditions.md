# Bash Scripting - Basic Condition

With a script named *script.sh*, the following script:

```bash

#!/bin/bash
first_greeting="Nice to meet you!"
later_greeting="How are you?"
greeting_occasion=1

if [ $greeting_occasion -lt 1 ]
then 
  echo $first_greeting
else
  echo $later_greeting
fi
```
when run with the below command in the terminal: 

```console
./script.sh
```
will result in the following:

```console
How are you?
```

> Key points from this lesson are: 

* Use if to start the conditional, followed by the condition in square brackets ([ ])
* Make sure to leave a space between a bracket and the conditional statement
* The conditional is closed with a backwards if, fi


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
