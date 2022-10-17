# Basic Linux Commands

The below is a list of common Linux commands and a brief explanation for them

##  **`pwd`**  

Displays the present working directory

##  **`ls`** 

Lists all files and directories in the current working directory

```yaml 
$ ls
Home Documents Desktop football.txt
```


## `ls -a` 

Lists all contents in the working directory, including hidden files and directories
```yaml
$ ls -a
. .. Home Documents Desktop football.txt
```


## `ls -l` 

Lists all contents of a directory in long format. 
```yaml
$ ls -l
```
![image](https://user-images.githubusercontent.com/107522496/195522842-8ab44db6-5155-4e64-bbe2-cb7567f59117.png)



## `ls -t` 

Orders files and directories by the time they were last modified
```yaml
$ ls -t
```

## `mkdir`

Takes in a directory name as an argument, and then creates a new directory in the current working directory. Here we used mkdir to create a new directory named games/.

```yaml
$ mkdir games
```

## `mv`

To move a file into a directory, use mv with the source file as the first argument and the destination directory as the second argument. Here we move pens.txt into stationery/.

```yaml
$ mv pens.txt stationery/
```
*__Note__*: The mv command moves files and directories from one directory to another or renames a file or directory. When moving a file or directory to a new directory, it will keep its name. 


## `rm`

Deletes files. The following command removes the file footbal_players.txt from the file system

```yaml
$ rm football_players.txt
```


## `rmdir`

Deletes directories. Only works on empty directories; otherwise you get an error
* 
```yaml
$ rmdir games
```



## `rm -r`

The command `rm` with the option `-r` deletes a directory and all of its child directories. Here, the teams directory is being deleted along wiht any files and/or directories it contains

```yaml
$ rm -r teams
```


## `rm -f` 

The command `rm` with the option `-f` forcefully removes a file. Here, the flowers.txt file  being deleted

```yaml
$ rm -f flowers.txt
```



## `rm -i`

The command `rm` with the option `-i` interactively removes a file. Here, the flowers.txt file  being deleted.

```yaml
$ rm -i flowers.txt
```

*__Note__*: If you are not certain about removing files that match a pattern you supply, it is always good to run rm interactively `rm –i` to prompt before every removal.



## `sort`

Takes a filename or standard input and orders each line alphabetically, printing it to standard output. In the example below, the names of the football players will be outputted in alphabetical order 


```yaml
$ sort player_names.txt
```


## `touch`

Creates a new file inside the working directory. It takes in a file name as an argument, and then creates a new empty file in the current working directory


```yaml
$ touch staff_list.txt
```



## `touch`

Creates a new file inside the working directory. It takes in a file name as an argument, and then creates a new empty file in the current working directory


```yaml
$ touch staff_list.txt
```



## `grep` 

Stands for “global regular expression print”. It searches files for lines that match a pattern and returns the results. __*Note*__: It is case *__sensitive__*.

```yaml
$ grep "Ronaldo" player_names.txt
```


## `grep -i` 

When `grep` is used with the `-i` option it allows for the enables the command to be case *__insensitive__*

```yaml
$ grep "Ronaldo" player_names.txt
```

## `grep -n`

When `grep` is used with the `-n` option, it will also show the line number in the result

```yaml
$ grep -n "Ronaldo" player_names.txt
```



## `grep -C`

 The `-C` option is used with `grep` to show some contect to the result. For example, we want to also see 3 lines before and 3 lines after the line we have searched for:

```yaml
$ grep -nC "Ronaldo" player_names.txt
```


## Using `grep`to filter the output of another command 

`grep` can be used to filter the results of a search. To achieve this, the user needs to pipe the output of the command via grep. The symbol `|` is used to to pipe.  

For example, the user searches for all files which have the .txt extension:

```yaml
$ ls -l *.txt
```

This will output all the files which have .txt as an extension

```yaml
$ ls -l *.txt
-rw-r--r--  1 test_user       1248 Feb 21 11:01 england.txt
-rw-r--r--  1 test_user       8462 Dec 22 17:13 france.txt
-rw-r--r--  1 test_user       0124 Apr 21 18:52 italy.txt
-rw-r--r--  1 test_user      12345 Jan 22 22:34 spain.txt
-rw-r--r--  1 test_user       0972 Sep 21 23:13 Germany.txt
$
```

To narrow our search down and only output those files which have Ronaldo, we can use the `|` and grep:

```yaml
$ ls -l *.txt | grep Ronaldo
-rw-r--r--  1 test_user       1248 Feb 21 11:01 england.txt
```

## `grep -R`

When `grep` is used with the `-R` option, it searches all files in a directory and outputs filenames and lines containing matched results. `-R` stands for “recursive”.

```diff
-Example to be found
```

## `grep -RI` 

When `grep` is used with the `-RI` option, it ssearches all files in a directory and outputs only filenames with matched results. `-R` stands for “recursive” and `l` stands for “files with matches”.

```diff
- Example to be found
```


## `>` 

Takes the standard output of the command on the left and redirects it to the file on the right. For example:
```yaml
$ cat football.txt > cricket.txt
```

  *Note:*`>` overwrites all original content in cricket.txt. When you view the output data by using cat on forests.txt, you will see only the contents of football.txt.
    
![image](https://user-images.githubusercontent.com/107522496/195457714-29f61832-1415-44c6-b8a4-7497018eff0b.png)



## `>>` 

Takes the standard output of the command on the left and appends (adds) it to the end of the file on the right. For example: 
```yaml
$ cat scores.txt > results.txt
```

  *Note:* here, the output data of results.txt will contain the original contents of results.txt with the content of scores.txt appended to it. 
  
  

## `<` 

Takes the standard input from the file on the right and inputs it into the program on the left. For example: 
```yaml
$ cat < results.txt
```
  `<` takes the standard input from the file on the right and inputs it into the program on the left. Here, results.txt is the standard input for the cat command. The standard output appears in the terminal




## `|` 

`|` is a “pipe.” The `|` takes the standard output of the command on the left, and pipes it as standard input to the command on the right. You can think of this as “command to command” redirection.
```yaml 
$ cat football.txt | wc  
```
Here, output of cat football.txt becomes the standard input of wc. In turn, the wc, “word count”, command then outputs the number of lines, words, and characters in football.txt.




## *`cd`* 

Takes a directory name as an argument, and switches into that directory
```yaml 
$ cd Documents/
```



## *`cd ..`* 

To move up one directory, use cd .. For example, cd .. navigates up from jan/memory/ to jan/.
```yaml 
$ cd ..
```


## *`cp`* 

Copies files or directories. Here, we copy the file linux_commands.txt and place it in the Documents/ directory

```yaml
$ cp linux_commands.txt Documents/
```


---
* 






```yaml 

```
