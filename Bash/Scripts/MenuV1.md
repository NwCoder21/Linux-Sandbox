# Menu - to print all scripts and allow user to choose one to run 

![image](https://user-images.githubusercontent.com/107522496/198306114-bb76ef78-e280-4bd3-8c7c-c34241417398.png)

![image](https://user-images.githubusercontent.com/107522496/198306309-095a8901-cbd8-4f62-8221-3ab34b643b32.png)


# Script 

```console
#!/bin/bash

count=1
numofscripts=0

echo "What is your name?"
read name

echo "Hello $name, please select one of the following options to run the corresponding script."

# for loop to iterate over the scripts avaiable in the directory 

for script in ./*
do
        # this ensures this script is not outputted 

        if [ "$script" == "./menu.sh" ]
        then
                ((count++))
        else

        # prints out script with associated number
        
        echo "Press $count to run $script"
        ((count++))
        ((numofscripts++))
        fi
done

read choice

# this while loop user enters a valid number

while [ $choice -lt 1 ] || [ $choice -gt $count ]
do
        echo "Please enter a number between 1 and $count"
        read choice

done

# case statement to run the relevant script

case $choice in

        1)
                ./blastoff.sh
                ;;
        2)
                ./hello.sh
                ;;
        4)
                ./months.sh
                ;;
        5)
                ./output-files.sh
                ;;
        6)
                ./sys-info.sh
                ;;
        7)
                ./test1.sh
                ;;
        8)
                ./update.sh
                ;;
                
        9)      ./weather.sh
                ;;
        *)
                echo "Something seems to have gone wrong, please re-run the script or contact ............
                ;;"
esac

exit

```


