```console

#!/bin/bash

# This scripts displays the User ID and username of the user executing this script 
# Display if the user is the root user or not


# Display User ID
echo "Your User ID is ${UID}"

# Display Username
USERNAME=$(id -un)
echo "Your username is ${USERNAME}"

# Display if the user is the root user or not
if [[ "${UID}" -eq 0 ]]
then
        echo "You are root user."
else
        echo "You are not root user."
fi
```
