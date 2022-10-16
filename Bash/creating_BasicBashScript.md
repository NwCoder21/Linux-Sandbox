# Visual Walkthrough of First Bash Script

This is a visual walkthrough of how I created my first Bash Script

For this task, I will be using the vim Text Editor

---

![image](https://user-images.githubusercontent.com/107522496/196006333-a3edbd9d-05c6-45fa-b52d-8b6332e167aa.png)

Whilst in the Home directory, type vim, followed by the name you want to name the Bash Script, in this case, hello.sh 

---

![image](https://user-images.githubusercontent.com/107522496/196006519-0f5855d6-bdfc-4f6a-8f72-1473ffaf0a07.png)

Start the script with the Shebang `#!/bin/bash`.

Write the script and type `x!` to save changes to the script. 

---

![image](https://user-images.githubusercontent.com/107522496/196006931-e9d0196d-864e-4245-a7ae-47c715a14f13.png)

Type **`./{name ofscript}.sh`** to run the script. If an error, such as `permission denied` is displayed, the access rights needs to be adjusted. 

![image](https://user-images.githubusercontent.com/107522496/196007572-9ba04759-1cbb-4111-a9e9-4e0c29dde7af.png)


`r` stands for read, `w` stands for write, and `x` executable. We need to add executable rights to this script.

To do this, type `chmod +x hello.sh` and press `ENTER`

![image](https://user-images.githubusercontent.com/107522496/196007578-c8df4c53-04ce-440d-a51d-5a50158abd0d.png)

Now the `x` rights have been addedd to the file, which means we can now execute and run this file

*`NOTE:`*: can also use `chmod 777 {name of script}.sh` 

---

![image](https://user-images.githubusercontent.com/107522496/196007181-9d6e2175-a124-4096-8897-22b17b0e3538.png)

In the Home directory, type `ls` to see all the files and directories. The file we just created should also now be listed.

Thereafter, create a directory to store our scripts. For this task, I will create a directory called 'examples'. 

Once created, we can move the hello.sh script into the examples directory using the mv command. 

---

![image](https://user-images.githubusercontent.com/107522496/196008616-7656e1cb-f992-48bb-a5d5-3455d8f29486.png)

Once moved, issue will be that we can't access and run this script. This is why location of the examples directory needs to be added to the PATH variable. 

---
![image](https://user-images.githubusercontent.com/107522496/196051393-b34e3ef5-892c-4549-99d1-7970bbba5f91.png)


First, by issuing the command `echo $PATH`, we can see it has not yet been added. To add it, we can either open the .bashrc file using a text editor such as vim
by doing the following:

![image](https://user-images.githubusercontent.com/107522496/196051465-0cf58ac4-db27-48bc-ae1b-7b60d22395b3.png)

and then typing `PATH=~/{name of directory you want to add to the PATH variable}examples:$PATH` and saving it by typing `:x!` (this will add the scripts location to the PATH variable):

![image](https://user-images.githubusercontent.com/107522496/196051578-67bd4b49-ca3d-4da3-9390-ad3cf3ef223d.png)


And then run the `echo .bashrc` command again. 

![image](https://user-images.githubusercontent.com/107522496/196051768-5b2abfd5-5046-479c-8941-39f97c27d17d.png)

If the PATH variable has not been updated, it means the user needs either :
* to log out and then back in to restart to console
* or can type in `.{space}./bashrc`
* or type `source .bashrc`

![image](https://user-images.githubusercontent.com/107522496/196051846-06de13ff-eaf5-4ac7-a989-3e02a420bc2f.png)

From the above screenshot, can see the examples directory has been addedd to the PATH variable.

> *Note*: we can also type in export PATH=/home/{username}/{name of directory where scripts saved}:$PATH. For example: 
> 
>  **`export PATH=/home/testuser/examples:$PATH`** 

---

![image](https://user-images.githubusercontent.com/107522496/196052027-4ca8af3d-838f-4769-9ce0-e848792cd8ac.png)

Can see now that we can call and run the script from anywhere if the filesystem 





