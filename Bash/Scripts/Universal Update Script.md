```bash
#!/bin/bash 

# Save the contents of /etc/os-release file into the variable release_file

release_file=/etc/os-release

# If statement to check if release_file contains the word "Arch". -q means quiet mode
# -i means it won't be case-senstive
if grep -qi "arch" $release_file
then
         # The host is based on Arch, run the pacman command
         echo "This is an Arch System"
         sudo pacman -Syu
fi

if grep -qi "debian" $release_file || grep -qi "ubuntu" $release_file
then
         # The host is based on Ubuntu, run the apt command
         echo "This is an Ubuntu System"
         sudo apt update
         sudo apt dist-upgrade

fi

```
