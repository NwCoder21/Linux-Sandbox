# Installing Packages Script 

![image](https://user-images.githubusercontent.com/107522496/214344409-db9b573a-4878-4ff5-90ac-2eafd1ae9317.png)


```bash
#!/bin/bash

package=$1

: ' 
The below line of code takes argument passed in by user and tries to install it. It then takes the output
: '

sudo apt install $package >> package_install_output.log
echo "The exit code for this script is ${?}"

# If statement to prinnt statements if exit code is 0 - i.e., successful 
if [[ $? -eq 0 ]]
then
        echo "The installation of $package was successfull"
        echo "The new command is available here:"
        which $package
# Else statement - if installation of package is a failure and exit code is not 0
        echo "$package failed to install." >> package_install_failure.log
fi
```
