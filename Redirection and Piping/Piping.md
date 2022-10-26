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

















