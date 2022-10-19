# How to Copy Files and Directories 

# `cp`

The `cp` command is used to copy file/s or directories.

## Syntax:
```yaml
$ cp <source> <destination> 
```
---

The following command will copy the contents of the test1.txt file into the test2.txt file 

```yaml
$ cp text1.txt text2.txt
```
---



Example of copying a file into a directory:

![image](https://user-images.githubusercontent.com/107522496/196704713-bdac2678-18a3-4cff-b47a-6c7f28210c0b.png)


---

Here, copied mancity.txt to the home directory. With copy, can copy and move a file to anywhere if provide a absolute path:


![image](https://user-images.githubusercontent.com/107522496/196706782-cd6c1b16-bacf-49fb-bd5b-65da5c7d9a61.png)

---

Example of copying multiple files to a destination folder:

![image](https://user-images.githubusercontent.com/107522496/196707470-66e7c3c1-53c5-4b52-ac0c-6ef42d256f91.png)

Note: Destinaiton folder already needs to have been created

---
Can copy multiple files using the `*` wildcard. 

![image](https://user-images.githubusercontent.com/107522496/196708830-2cf2b2a6-c81a-4f7c-986d-d67bb0acca5d.png)

Note: `*` wildcards only grab files but not directories. So, to copy folders too, we need to use the -R (recursive) option with cp .....

![image](https://user-images.githubusercontent.com/107522496/196709908-b776127b-8568-414b-afae-c3b78adcdd83.png)












