# Bash Scripting - Conditional

The following script:

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

