# Checking for Files 


The if statement can be used in Bash to test for file attributes, such as:
* File or directory existence
* Read or write permission
* Executable permission.

---

The following table is a lost of conditions and their meaning 

| **Condition**|  **Meaning**|
| :-----------: | :-----------  |
| -e |Checks if the file exists|
| -d |Checks if the file is a directory|
| -f |Checks if the file is a regular file (i.e. not a symbolic link, device node, directory, etc.)|
| -s |Checks if the file is of non-zero size.|
| -g |Checks if the file has sgid set.|
| -u |Checks if the file has suid set|
| -r |Checks if the file is readable|
| -w |Checks if the file is writable|
| -x |Checks if the file is executable|

---

Example: 

```console
if [ -x /etc/passwd ] ; then
    {Perform a particular action} 
fi

```

