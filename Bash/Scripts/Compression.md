# Compression Script 

The aim of this script is to output all folders in the current directory and ask user which one they would like to compress and archive.

```bash
  1 #!/bin/bash
  2 
  3 # Script which outputs list of folders in current directory and asks user which one would they like to compr    ess
  4 
  5 # Declaring count variable 
  6 COUNT=0
  7 COUNTER=0
  8 
  9 # Declare array to hold name of folders in current directory
 10 declare -a FOLDERSARRAY
 11 
 12 # Output only folders in current directory
 13 for folder in $(ls -d */)
 14 do
 15         FOLDERSARRAY[$COUNT]="${folder%%/}"
 16         ((COUNT++)
 17 done
 18 
 19 # Finding the length of the FOLDERSARRAY
 20 FOLDERSLENGTH=${#FOLDERSARRAY[@]}
 21
 22 # Length of FOLDERSARRAYminus 1 
 23 FOLDERARRMIN1=$(( ${#FOLDERSLENGTH[@]} - 1 ))
 24 
 25 # For loop to output folders in currennt directory 
 26 for (( i=0; i<${FOLDERSLENGTH}; i++ ));
 27 do
 28         echo "Press $COUNTER to compress ${FOLDERSARRAY[$i]}"
 29         ((COUNTER++))
 30 done
 31 
 32 # Read user's input
 33 read choice
 34 
 35 
 36 # this while loop user enters a valid number
 37 #while [ $choice -lt 0 ] || [ $choice -gt $FOLDERARRMIN1 ]
 38 #do
 39  #       echo "Please enter a number between 0 and $FOLDERSLENGTH"
 40   #      read choice
 41 #done
 42 
 43 
 44 # Folder which will be compressed
 45 TOCOMPRESS=${FOLDERSARRAY[choice]}
 46 echo "You will be compressing the ${TOCOMPRESS} folder"
 47 
 48 echo "What would you like to name the archive?"
 49 read ARCHIVENAME
 50 
 51 tar -cf ${ARCHIVENAME}.tar.gz ${TOCOMPRESS}
 52 
 53 exit
 54 
```

![image](https://user-images.githubusercontent.com/107522496/203955029-901ee2eb-575b-4525-a80f-6f104802084b.png)

