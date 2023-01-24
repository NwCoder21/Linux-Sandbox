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

# If statement to print statements if exit code is 0 - i.e., successful 
if [[ $? -eq 0 ]]
then
        echo "The installation of $package was successful"
        echo "The new command is available here:"
        which $package

# Else statement - if installation of package is a failure and exit code is not 0
else
        echo "$package failed to install." >> package_install_failure.log
fi


```

When we run this script, we should see less output. If the script is successful, the output will be sent to the `package_install_output.log` file. If the script does not run successfuly, the output will be sent to `package_install_failure.log`.













