# `locate`

This command is used to find files by their name. There are two main ways of finding and searching for files/directories:

* `locate`: faster than `find`, searches the database entries to search for the files. The database needs to be updated before using `locate`, otherwise may not give up to date results.  `locate` searches the entire database. 
* `find`: this searches the filesystem. This makes is slower than `locate`. `find` has more options which can be used with it, such as searching by name, size, the time it was created. Also, `find`, by default, will search in the current directory   

Note: will have to update the database, using `sudo updatedb` before being able to use `locate`

![image](https://user-images.githubusercontent.com/107522496/197186126-6730225d-d7b0-41dd-b732-e67d9e77e8d8.png)













