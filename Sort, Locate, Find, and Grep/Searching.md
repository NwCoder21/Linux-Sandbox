# Searching 

There are several ways we can look and search for things in our system. 

---
# `locate`

The first method to search for things is by using the `locate` command. It performs a search of pathnames (or file names) across the machine that match the provided substring and then prints out any mathching names. 

* `locate` is fast as uses a pre-generated database file that the system constructs to search for substring provided rather than searching the whole machine (instead of searching every file and folder).
* This database file is indexed and is kept relatively up to date and contains entries for every file on the machine. 
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

# How to use `locate`

```yaml
$ locate <option> <pattern>
```

For example, we can search for part of a file name and see where it is located, such as: 

![image](https://user-images.githubusercontent.com/107522496/198534485-f52701c3-8328-4f4b-a288-41f211db6524.png)

> `locate` is case-senstive 
 
`locate` does not run relative to your current location. This means the user can be anywhere and search for a file in a different directory. For example: 

![image](https://user-images.githubusercontent.com/107522496/198538940-7deeed5d-84f8-424b-b851-8fc0aeaa4203.png)

even though the user is in the Pictures directory, they have been able to find a file in a different directory.

---

# `-i` option with `locate` to carry out an case-unsenstive search

Use the `-i` option with `locate` to carry out an case-unsenstive search. For example: 

![image](https://user-images.githubusercontent.com/107522496/197208226-19822663-ded7-4005-b9fa-93229567e8bf.png)

# `-l` or `--limit` options to limit the results to a certain amount 

To limit the amount of results returned, use the  `-l` or `--limit` options. For example: 

![image](https://user-images.githubusercontent.com/107522496/197208699-e65b01fc-f421-480d-a376-fac30fff4680.png)

In the above example, by using `-l3`, it returns the first three results.

---

# `-e` (exists) - searching for files which actually exist

This opton is used with `locate` when trying to find files which actually still exisit, and have not been deleted since the last time the database was updated.

This is because, since the last time database was updated, any files which have been removed since, will still show up in results when using `locate`. The `-e` option ensures that only the files which have not been deleted since the last update, and still exist, are displayed.

![image](https://user-images.githubusercontent.com/107522496/198541697-3b697979-53c9-4f06-9cd4-57158da05061.png)

In the above example, after having removed the Mancity.txt file and then searching for it using `locate`, it still shows up in the results even though it has been deleted This is because the database which `locate` uses, has not been updated as of yet. This is where we can use the `-e` option to see ensure that the files which are outputted, do actually exist, for example, 

![image](https://user-images.githubusercontent.com/107522496/198543033-8a83df3e-14a3-4330-8bbf-66d0232725d5.png)

here, when we run the `locate` command now using `-e`, we cann see that the /myFoldersBackup/fruits/Mancity.txt file does not show up in the results.

To solve this issues, we can run the following command:

```yaml
$ sudo updatedb
```

![image](https://user-images.githubusercontent.com/107522496/198548581-ddeb0633-1e8b-4c87-bfcc-b8bb21bb37a7.png)

Now, after running `sudo updatedb` the /myFoldersBackup/fruits/Mancity.txt file does not show up in the results even though we have not used the `-e` option.

> Note: the database does automatically update over time, however, using the above method, it can be updated manually 

---

# `find`

* `locate` is fairly easir to use , however, it does haveits limitations. `find` is more powerful but it is also more slow than `locate` as it does not use a database to search for files. 
* `find` looks through the entire directory or machine  
* If `find` is run without any arguments, it will output every file and directory nested within our current directory. For example: 

![image](https://user-images.githubusercontent.com/107522496/198557969-eb45d62f-1af7-4267-88f2-4369a6c8fdca.png)

> Note: difference between `ls` and `find` is that `ls` outputs all the files and directories in the current directory and not the nest files, whereas `find` outputs not only all the files and directories in the current directory, but also all subsuquent nested files and directories.  
> Can also provide `find` a certain path, does not have to be current directory


---

# `-type`

The `-type` option can be used with three different characters:

* `-type d`: this searches for directories 
![image](https://user-images.githubusercontent.com/107522496/198560317-217e4532-da5e-4901-b507-85b85360eda6.png)

This only shows the directories and nested directories

* `-type f`: this searches for files 
![image](https://user-images.githubusercontent.com/107522496/198560225-58773ca7-8472-4c90-8e8c-bd797122ccd4.png)

This only shows the files and nested files 

* `-type l`: this searches for symbolic links

--- 

# `-name`

When using the `-name` option with `find`, we also provide the command with a search pattern, enclosed inside of quote marks.

For example, to find all files which end in .txt, we could use:

![image](https://user-images.githubusercontent.com/107522496/198561748-aa84c611-fd81-4332-b8ed-e4977bf7177e.png)
 
To search for all jpeg files:
 
![image](https://user-images.githubusercontent.com/107522496/198563113-c99e4e75-466a-4070-82a5-246bf854cd43.png)

---
Let's say we know we have a file/s which contain the letters "man" in them. 

```yaml
$ find -iname "man*"
```

![image](https://user-images.githubusercontent.com/107522496/198564952-161e7b6c-f661-46e8-95df-69c085abaf01.png)

The reason why `find -iname "man"` does not work is because it is searching for a file which is called man (in other words, searching for an exat match). 
Whereas,`find -iname "*man*"` and `find -iname "man*"` searches for a file which also contains the pattern "man"

> `-name` option is case-senstive, whereas the `iname` option is used for a case insenstive search.

To search for a file which contians a number, we can use:

```yaml
$ find -name "*[0-9]*"
```
![image](https://user-images.githubusercontent.com/107522496/198565403-e2e9a353-d549-4a64-91ad-cb9bebc30f90.png)

---

# `-size` - Finding by Size 

The `-size` option can be used with the `find` commmand to find files of a specfic size.

```yaml
$ find -size +200k
```
* `-` symbol is used to search for files which are **under** a specific size. For example, `-2M` means files under 2 megabytes 
* `+` symbol is used to search for files which are **over** a specific size. For example, `+500k` means files over 2 kilobytes 

![image](https://user-images.githubusercontent.com/107522496/198569042-411d5e1d-d2ef-4833-9c15-8d652bb001aa.png)

> Note: when using this option, the results do not display the exact size of the file

# `-user` - Finding by Owner

The `-user` option outputs files and directories which are owned by the name provided

```yaml
$ find -user joe
```
---

# `-empty` - Searching for Empty Files and Directories 

When `find` is used with the `-empty` option, it will search for empty files or directories 

![image](https://user-images.githubusercontent.com/107522496/198569958-4a020be5-76f6-4634-990c-033ef5ae280b.png)

In this above example, `find -empty -type d` searches for any empty directories.

To search for empty files, we can use : 

```yaml
$ find -empty -type f
```
--- 

# Finding by Time

To have a look how timestamps work and the different types, click [here](https://github.com/NwCoder21/Linux-Sandbox/blob/main/Sort%2C%20Locate%2C%20Find%2C%20and%20Grep/Timestamps.md)

### To find files according to the time in minutes, we use:

* -mmin: this searches for files depending on the time they were modified (in minutes). For example:
 * `find -mmin +30` - this will look for files which have been modified **more than** 30 minutes ago 
 *  * `find -mmin -30` - this will look for files which have been modified **less than** 30 minutes ago 

* `-cmin`: this searches for files depending on the time they were changed (in minutes). For example:
  * `find -cmin +30` - this will look for files which have been changed **more than** 30 minutes ago 
 * `find -cmin -30` - this will look for files which have been changed **less than** 30 minutes ago

* `-amin`: this searches for files depending on the time they were accessed (in minutes). For example:
  * `find -amin +15` - this will look for files which have been accessed **more than** 15 minutes ago 
 * `find -amin -45` - this will look for files which have been accessed **less than** 45 minutes ago

### To find files according to the time in days, we use:

* -mtime: this searches for files depending on the time they were modified (in days). For example:
 * `find -mtime +3` - this will look for files which have been modified **more than** 3 days ago 
 *  * `find -mtime -4` - this will look for files which have been modified **less than** 4 days ago 

* `-ctime`: this searches for files depending on the time they were changed (in days). For example:
  * `find -ctime +7` - this will look for files which have been changed **more than** 7 days ago 
 * `find -ctime -5` - this will look for files which have been changed **less than** 5 days ago

* `-atime`: this searches for files depending on the time they were accessed (in days). For example:
  * `find -atime +15` - this will look for files which have been accessed **more than** 15 days ago 
 * `find -atime -2` - this will look for files which have been accessed **less than** 2 days ago

> Note: when dealing with days, it means 24 hour blocks
















