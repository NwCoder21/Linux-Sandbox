# Redirection 

Normally, a command is run in the command line and its result is outputted to the terminal. However, there are ways we can *redirect* this output to somewhere else, such as another file, program, device, or even another command. This allows us to **chain** commands together in a **pipline**.   

There are three types of communication streams between a computer program and its enviroment 

* `Standard Input` (`stdin`): this is information inputted into the terminal by using a keyboard or another input device 
* `Standard Output` (`stdout`): this is information outputted once a command has been run
* `Standard Error` (`stderr`): this is an error message which is outputted when a falied process or incorrect command is run 

---

# Redirecting Standard Output

When talking about redirecting standard output and standard error, it means redirecting them do a different output detination other than the default destination, for example, to another command or file. 

> The default destination for standard output and standard error is the terminal. 

If the below commmand was run:

```console
echo "Hello World!!"
```
Here, `Hello World!!` is entered as the standard input and `Hello World!!` is then outputted to the terminal as standard out (as this is the default destination for output). However, we can redirect the output to a file instead of directing it to the terminal. To do this, we would use the `>` command followed by the filename of where we want to send the output. 

```console
echo "Hello World!!" > greeting.txt
```
In the above example, `Hello World!!` would be redirected to the `greeting.txt` file instead of outputting it onto the terminal. We can check that the redirection has worked b using the `cat` command followed by the name of the file we sent the direct to, for example, 

![image](https://user-images.githubusercontent.com/107522496/197761925-2ce542de-981e-4402-93fe-64c46ee7b838.png)


---

# `>`

This `>` symbol is used to redirect standard output. It  takes the takes the standard output of the command to its left, and redirects it to the file to its right. 

> IMPORTANT!!: `>` completely overwrites (erases and replaces) the contents of a file. For example:

![image](https://user-images.githubusercontent.com/107522496/197796581-8c601107-db34-4aa7-93c7-190cd600d82a.png)

> To know how to append data onto the end of a file, see the next section. 

---

![image](https://user-images.githubusercontent.com/107522496/197794301-d42907de-cb86-40fe-932f-e6af0a53a734.png)

In the above example, when typing the `ls` command, by default, the output is sent to the terminal and dispalyed. However, by using the `>` symbol, we can redirect this output to a file (in this case, files.txt). Hence, nothing will be displayed on the terminal. We can check if redirection has work by using the `cat` command with files.txt as its argument. 

---

![image](https://user-images.githubusercontent.com/107522496/197763872-d8559b55-63a5-476f-b007-817aef207df4.png)

In the above example, we are taking the contents of the `cities.txt` file and sending it (redirecting it) to the `namesofcities.txt` file. Because we have redirected the output to a file, we won't see the output on the terminal.

We can confirm that indeed this redirect has been successful by using the `cat`command on the new file:

![image](https://user-images.githubusercontent.com/107522496/197764218-9795681f-5dd4-4f9b-8b40-10abf4f32077.png)


---

# `>>`

When redirecting, tThe `>>` symbol allows to add text to end of a file without losing the original text.

![image](https://user-images.githubusercontent.com/107522496/197770528-570fe7d1-6efc-4e12-960e-a090cb67f7d2.png)


Here, the contents of `animals.txt` have been sent (**appended**)) to the end of the contents of `greeting.txt`. The orginal text of `greeting.txt` remains. 


---

![image](https://user-images.githubusercontent.com/107522496/197807374-9b4a8df6-b1f7-4eea-9fb0-844bc411de8d.png)

This is another example. we have a file named files.txt which contains the files in that directory. Then using the `>>` command, we can append the output of `date` to the end of files.txt. The original text remains when using `>>`.

---

The standard output for the `echo` command is to the terminal. However, we can, using redirection, quickly create a file and send the output of `echo` to file instead.

For example, to create a file called greeting.txt and write "hello world" into it, we would have to take the following steps:

![image](https://user-images.githubusercontent.com/107522496/197809975-94a1ef6f-df34-4b92-b5be-d30d222661d4.png)

However, we can achieve the same thing using redirection. For example:

![image](https://user-images.githubusercontent.com/107522496/197810726-552fa260-88db-4f7f-8654-74ccd4b768d9.png)

---

# Redirecting Standard Input 
 
To redirect the contents of a file to standard input, use the `<` symbol.

![image](https://user-images.githubusercontent.com/107522496/197814351-d9bcc8ed-da32-4b9a-a80a-4fe2475459a7.png)

 This comes more into play when using pipelines. However, the results of both commands may look the same, however, they are technically different.
 
 ```console
cat animals.txt
```
 In the above command, we aare passing `animals.txt` as an command line argument, to the command `cat` 
 
 ```console
cat < animals.txt
```
In the above line, we are passing the contents of `animals.txt` to `cat` via standard input. 
























