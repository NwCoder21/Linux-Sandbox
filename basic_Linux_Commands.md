# Basic Linux Commands

The below is a list of common Linux commands and a brief explanation for them

*  **`pwd`** - displays the present working directory



---
*  **`ls`** - lists all files and directories in the current working directory
```yaml 
$ ls
Home Documents Desktop football.txt
```

---
*  *`ls -a`* - lists all contents in the working directory, including hidden files and directories
```yaml
$ ls -a
. .. Home Documents Desktop football.txt
```

---
* *`ls -l`* - lists all contents of a directory in long format. 
```yaml
$ ls -l
```
![image](https://user-images.githubusercontent.com/107522496/195522842-8ab44db6-5155-4e64-bbe2-cb7567f59117.png)


---
* *`ls -t`* - orders files and directories by the time they were last modified
```yaml
$ ls -t
```


---
* *`mkdir`* - takes in a directory name as an argument, and then creates a new directory in the current working directory. Here we used mkdir to create a new directory named games/.

```yaml
$ mkdir games
```
---
* `>` takes the standard output of the command on the left and redirects it to the file on the right. For example:
```yaml
$ cat football.txt > cricket.txt
```

  *Note:*`>` overwrites all original content in cricket.txt. When you view the output data by using cat on forests.txt, you will see only the contents of football.txt.
    
![image](https://user-images.githubusercontent.com/107522496/195457714-29f61832-1415-44c6-b8a4-7497018eff0b.png)


---
* `>>` takes the standard output of the command on the left and appends (adds) it to the end of the file on the right. For example: 
```yaml
$ cat scores.txt > results.txt
```

  *Note:* here, the output data of results.txt will contain the original contents of results.txt with the content of scores.txt appended to it. 
  
  
---
* `<` takes the standard input from the file on the right and inputs it into the program on the left. For example: 
```yaml
$ cat < results.txt
```
  `<` takes the standard input from the file on the right and inputs it into the program on the left. Here, results.txt is the standard input for the cat command. The standard output appears in the terminal



---
* `|` is a “pipe.” The `|` takes the standard output of the command on the left, and pipes it as standard input to the command on the right. You can think of this as “command to command” redirection.
```yaml 
$ cat football.txt | wc  
```
Here, output of cat football.txt becomes the standard input of wc. In turn, the wc, “word count”, command then outputs the number of lines, words, and characters in football.txt.



---
* *`cd`* -  takes a directory name as an argument, and switches into that directory
```yaml 
$ cd Documents/
```


---
* *`cd ..`* - To move up one directory, use cd .. For example, cd .. navigates up from jan/memory/ to jan/.
```yaml 
$ cd ..
```


---
* *`cp`* - copies files or directories. Here, we copy the file linux_commands.txt and place it in the Documents/ directory

```yaml
$ cp linux_commands.txt Documents/
```


---
* 






```yaml 

```
