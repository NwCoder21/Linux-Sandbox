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

> The above is an example of using multiple pipes together.   
---

# Another Example of Using Multiple Pipes 

If we wanted to display the five largest files in the current directory, we could use several pipes to achieve this. we could use the `ls`, `sort`, and `head` commands. For example, 

![image](https://user-images.githubusercontent.com/107522496/198230663-41270d4e-0315-4fb7-82dd-cd90c8a2429d.png)

* `ls -lh`: outputs the files in the current directory in long format (`-l` option) and it displays the files' sizes in human readable format (`-h` option). 
* `sort -rhk 5`: this command sorts the output of `ls -lh` according to the fifth column (`-k 5` option), into reverse order (`-r` option) i.e. from largest to smallest, displays the the files' sizes in human readable format (`-h` option)
* `head -5`: this command takes the output from `sort -rhk 5` and displays the first five results.

We could then send this output to a file instead of to the terminal. To do this, `> <filename> ` can be used. For example:

![image](https://user-images.githubusercontent.com/107522496/198234128-9d7746ca-1c2c-4579-bb64-85523cd60113.png)

### Using the `du` command to achieve this too 

Another way of acheieving the same result would be to use the `du` command:

![image](https://user-images.githubusercontent.com/107522496/198236346-46619982-ce44-4c8b-b6b1-54995a3121f7.png)

---

# The `tee` Command

































