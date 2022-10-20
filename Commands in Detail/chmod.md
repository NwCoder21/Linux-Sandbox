# **chmod** 

Evry file has three types of permissions. They are:

* Read
* Write 
* Execute

---

To check a file's permissions, type the command ls -l:

![image](https://user-images.githubusercontent.com/107522496/196937544-42608669-eaed-4e36-8c16-7bd334ff20c0.png)

The part highlighted in red represents the following:


The first column represents the type of file

* `-` means it is a normal file 
* `d` means it is a directory
* `l` means it is a link

---


![image](https://user-images.githubusercontent.com/107522496/196938662-c2039d40-2ece-4c14-a5c8-7248ede81707.png)

Then we have three sets of values 

* Red: these are the owner's permissions 
* Yellow: these are the group's permissions
* Blue: these are everybod else's permissions

Each set of values can be represented by one outof four characters. They are:

* `r`: reading permission 
* `w`: writing permission 
* `x`: execution permission
# `-`: this means that user does that have this specific permission 

---

A file's permissions are be able to be changed. To do this, we can use the `chmod` command either by using symbolic arguments or numeric arguments.

# Symbolic Arguments

To change a file's permissions using symbolic arguments, we: 

1. Type `chmod` 
2. Followed by: 

* `a`: this means all 
* `u`: this means the user
* `g`: this means the group
* `o`: this means others

3. Followed by: 
* To add permissions, we use the `+` symbol
* To remove permissions, we use the `-`symbol

4. Followed by the permission/s you want to allocate or de-allocate:

* `r`: reading permission 
* `w`: writing permission 
* `x`: execution permission

## Examples

![image](https://user-images.githubusercontent.com/107522496/196946508-6a2e0446-7ff8-4df8-957c-0925d3a24ec3.png)

* *`chmod o-r test1`* is removing the read permissions from `others`
* *`chmod g-rw test1`* is removing the read and write permissions from the `group`
* *`chmod u-rw test1`* is removing the read and write permissions from the `user`

---

![image](https://user-images.githubusercontent.com/107522496/196948236-ecad1059-da7f-4d50-92a0-f7c646cc6691.png)

* *`chmod u+rxw test1`* is adding the read, write and execute permissions to the `user`
* *`chmod g+rw test1`* is adding the read and write permissions to the `group`
* *`chmod o+r test1`* is adding the read permission to `others`

---

![image](https://user-images.githubusercontent.com/107522496/196949450-f2977e31-9b8f-42bd-a9f5-16f299698b79.png)

* *`chmod a+rxw test2`* is adding the read, write and execute permissions to `everyone`
* *`chmod a-x test2`* is removing the execute permissions from `everyone`


> Note: can add or rmeove permissions to/from multiple users by adding the relevant characters before the `+` or `-` symbol. For example: 
> When editing a folder's permissions, can use the -r option to 

![image](https://user-images.githubusercontent.com/107522496/196950722-6dcdfc90-006d-4ecf-9343-39c2626b8a1f.png)

---
# Numeric Arguments 

When using numeric values to set or remove permissions, certain values represent certain permissions. They are:

* 7: read, write and execute
* 6: read and write 
* 5: read and execute
* 4: read 
* 3: write and execute
* 2: write
* 1: execute
* 0: none































