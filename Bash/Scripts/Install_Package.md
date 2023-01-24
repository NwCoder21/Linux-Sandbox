# Installing Packages Script 

```bash
#!/bin/bash

package=$1

: ' 
The below line of code takes argument passed in by user and tries to install it. It then takes the output
: '

sudo apt install $package >> package_install_output.log

# If statement to print statements if exit code is 0 - i.e., successful 
if [ $? -eq 0 ]
then
        echo "The installation of $package was successful"
        echo "The new command is available here:"
        which $package

# Else statement - if installation of package is a failure and exit code is not 0
else
        echo "$package failed to install." >> package_install_failure.log
fi
```

![image](https://user-images.githubusercontent.com/107522496/214433819-0b529110-af3f-44cb-92ee-7097dd8c5220.png)

---

![image](https://user-images.githubusercontent.com/107522496/214344409-db9b573a-4878-4ff5-90ac-2eafd1ae9317.png)

When we run this script, we should see less output. If the script is successful, the output will be sent to the `package_install_output.log` file. If the script does not run successfuly, the output will be sent to `package_install_failure.log`.

---

![image](https://user-images.githubusercontent.com/107522496/214431206-9dd198ab-1675-4960-a674-891cbae5d5d4.png)

Here, we are trying to install a package called `treee`. This package does not exist. So, it should not be successful ...

![image](https://user-images.githubusercontent.com/107522496/214431511-9677d00a-7246-4244-94c6-0725a1c8c83f.png)

We then are checking the data entered  into both files. 

---

![image](https://user-images.githubusercontent.com/107522496/214433634-c2d4614d-f597-409b-b90c-5f2cffe75f21.png)

Here, we are running a valid command and then checking the output in the `package_install_output.log`.

---

![image](https://user-images.githubusercontent.com/107522496/214433207-0d102036-5ead-484f-b2d4-f9e78332045f.png)

When you use an exit code, the script comes to an end and does not ready anything after that.  









