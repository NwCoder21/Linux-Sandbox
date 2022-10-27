# Searching 

There are several ways we can look and search for things in our system. 

---
# `locate`

The first method to search for things is by using the `locate` command. It performs a search of pathnames (or file names) across the machine that match the provided substring and then prints out any mathching names. 

* `locate` is fast as uses a pre-generated database file that the system constructs to search for substring provided rather than searching the whole machine.
* This database is kept relatively up to date and contains entries for every file on the machine. 
* The database needs to be updated before using `locate`, otherwise may not give up to date results as the database is not a live/up to date file. 
* To install, use: 

```yaml
sudo apt install mlocate
```
> Note: will have to update the database, using:

```yaml
sudo updatedb 
```
> before being able to use `locate`. 

#######################################













































This command is used to find files by their name. There are two main ways of finding and searching for files/directories:

* `locate`: faster than `find`, searches the database entries to search for the files.   `locate` searches the entire database. 

> Locate is fast because uses that built in database file to search for things, and does not search in every folder and every file, rather looks in one database file which is indexed. Can also provide it a path to search in.

* `find`: this searches the filesystem. This makes is slower than `locate`. `find` has more options which can be used with it, such as searching by name, size, the time it was created. Also, `find`, by default, will search in the current directory   

Note: will have to update the database, using `sudo updatedb` before being able to use `locate`

![image](https://user-images.githubusercontent.com/107522496/197186126-6730225d-d7b0-41dd-b732-e67d9e77e8d8.png)


---

If I wanted to search for a file which contained "afri", I could use: 

![image](https://user-images.githubusercontent.com/107522496/197206376-3e8c3813-ef7a-4a39-adda-344512e56a6b.png)


> Doesn't matter where you are in filesystem, can give it a path to search in 

---

# `-i` option with `locate` to carry out an case-unsenstive search

Use the `-i` option with `locate` to carry out an case-unsenstive search. For example: 

![image](https://user-images.githubusercontent.com/107522496/197208226-19822663-ded7-4005-b9fa-93229567e8bf.png)

# `-l` or `--limit` options to limit the results to a certain amount 

To limit the amount of results returned, use the  `-l` or `--limit` options. For example: 

![image](https://user-images.githubusercontent.com/107522496/197208699-e65b01fc-f421-480d-a376-fac30fff4680.png)

---

# `-e` (exists) - searching for files which actually exist

This opton is used with `locate` when trying to find files which actually still exisit, and have not been deleted since the last time the database was updated.

This is because, since the last time database was updated, any files which have been removed since, will still show up in results when using `locate`. The `-e` option ensures that only the files which have not been deleted since the last update, and still exist, are displayed.














