# Automating System Updates Script

 This is a walkthrough of how to update the system by running one script.
 
 ---
 
 ![image](https://user-images.githubusercontent.com/107522496/197343906-490afd91-bf95-43f4-8a8a-24660a5390c2.png)

 Create and open a file using a text editor, in this case I will be using vim.
 
 ---
 
![image](https://user-images.githubusercontent.com/107522496/197344187-a99e0cf7-3911-48ff-840a-2fae10cedd13.png)

 This is the script.
 
 `sudo apt update` checks for avaialable updates
 
 `sudo apt dist-upgrade` installs thw updates
 
 > Note: Don't forget to include the shebang, ``#!/bin/bash` as the top of the script.  

---

![image](https://user-images.githubusercontent.com/107522496/197344227-dc2f08b9-bc20-4a01-8c08-773d0e66426a.png)

Can also use the `-yy`. This means when checking and installing updates, it will bypass asking you to type `y` to confirm if you want to go ahead or not 

---

![image](https://user-images.githubusercontent.com/107522496/197344348-e1cef23d-9dcd-4540-a42f-e8f6bbe61945.png)

We can checking the permissions on the file by using the command ls -l. 
We can see that it does not have the execute permission. To implement this, we use the chmod =x {name of script}.sh command.

















