# Automating System Updates Script

 This is a walkthrough of how to update the system by running one script.
 
 ---
 
![image](https://user-images.githubusercontent.com/107522496/197344596-9a731fdc-32af-47ec-895e-ecaca1a6fd0c.png)

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

---

![image](https://user-images.githubusercontent.com/107522496/197344486-190c2533-105b-430f-9561-6741b3722292.png)

From the above, we can see that by running our script, `update-sys.sh`, our scripts runs the whole process of updating and upgrading.

![image](https://user-images.githubusercontent.com/107522496/197344540-6bd98a60-2112-4ba7-a1f3-d5cf8acd1df4.png)

All updates have now been installed.

---

# Running this script from anywhere 

![image](https://user-images.githubusercontent.com/107522496/197344964-61c6ea97-1ee3-4dfe-9928-42d10119b2fa.png)

Because we have added the examples directory to the PATH variable, this means we can run our script from anywhere. For example: 

![image](https://user-images.githubusercontent.com/107522496/197345035-e18f9c73-3d8a-440a-b56f-08d0fc2fc744.png)











