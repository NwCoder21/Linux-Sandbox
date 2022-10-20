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

## Symbolic arguments

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

# Examples

![image](https://user-images.githubusercontent.com/107522496/196946508-6a2e0446-7ff8-4df8-957c-0925d3a24ec3.png)

* `chmod o-r test1` is removing the read permissions from `others`
* `chmod g-rw test1` is removing the read and write permissions from the `group`
* `chmod u-rw test1` is removing the read and write permissions from the `user`



