# Piping 

This is where we can see why a command being able to accept standard input is important as it is used with piping.

Normally, commands are run one at a time. However, by using piping, we can run multiple commands in one go. The `|` symbol is used to separate two commands. The output of the command on the left of the `|`is passed onto the command to the right of the `|`. For example;

```console
$ command 1 | command 2
```
Here, command 1 will run and the output of command 1 will be passed command 2.

> Note: Using `|`, we can take the standard output of one commmand and pipe it to the standard output of the second command. This allows multiple commands to be stringed/chained together.

![image](https://user-images.githubusercontent.com/107522496/198016325-c58b6330-a6ae-4933-b6d9-78cc88dfa8a6.png)
 
In the above example, we are taking the output of `cat animals.txt` and send it to the command `wc -w` (which outputs the word count). 

> Piping means taking the output of one command and sending it to the input of a second.

---

![image](https://user-images.githubusercontent.com/107522496/198063744-b7ce5c95-fcab-4dd7-83ab-c6af77971ef2.png)

In the above example, we are looking at the long list of executables on the system. However, we could use piping to take the output of `ls /usr/bin -l` and send it to the `sort` command to be sorted according to size, and then outputted.

![image](https://user-images.githubusercontent.com/107522496/198059326-f7637aef-9d69-435a-9051-e20c24ade619.png)

 ---
 
 # Difference Between Piping and Redirection
 
 * `>`/ redirection: connects the output of a command to a file, in other words, redirecting standard input/output/error. For example, redirecting standard output to a file instead of to the terminal. 
   
 * `|`/piping: connects a command to another command, in other word, sends the output of one command to the input of another command. 

---

Redirection and piping can be combined together, but they are not the same .   

![image](https://user-images.githubusercontent.com/107522496/198067941-d1e74b0e-7dd5-4c5c-8144-b49c11838de7.png)

In the above example, we are combining two commands together using a pipe, and then sending the combination of the two commands to a new file named sortedExe.txt. This is an exampple of using pipeing and redirection together. 

---

# `tr`- translate 

![image](https://user-images.githubusercontent.com/107522496/198072900-ee1ed4a9-ddec-4c93-b7bf-02fb66dc4e4b.png)

`tr`requires that data is provide dto it via standard in. In the above example, we are using multiple pipes to have only the number remain for each line. Using `tr`, we are doing the following:

* `| tr -d [:alpha:]`: is taking the output of `cat contact.txt` and removing alphabetical characters
* ` | tr -d : `: is removing the colon 
* `| tr -d [:blank:]`: is removing the space 
* `>`: this is then redirecting the output to a file 

---

# Multiple Pipes - To be Continued 
































