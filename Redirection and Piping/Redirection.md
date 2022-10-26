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

# Redirecting Standard Input - `<`
 
To redirect the contents of a file to standard input, use the `<` symbol.

![image](https://user-images.githubusercontent.com/107522496/197814351-d9bcc8ed-da32-4b9a-a80a-4fe2475459a7.png)

 This comes more into play when using pipelines. However, the results of both commands may look the same, however, they are technically different.
 
 ```console
cat animals.txt
```
 In the above command, we are passing `animals.txt` as an command line argument, to the command `cat`.
 
 ```console
cat < animals.txt
```
In the above line, we are passing the contents of `animals.txt` to `cat` via standard input. 

# Redirecting Standard Input and Standard Output

Standard input and standard output can also be redirected at the same time.  

![image](https://user-images.githubusercontent.com/107522496/197976654-5883bb58-5e4a-4c48-9fc3-28aca54bca60.png)

In the above example, we are using `cat` to read (standard input) the contents of the namesofcities.txt file and, instead of outputting the contents to the terminal, it redirects the output (standard output) to the greeting.txt file. 

> Remember: use the `<` symbol to redirect standard in and the `>` symbol to redirect standard ouput

In this example, becuase we have used the `>` symbol, the contents of greeting.txt are being replaced and overwritten by the data which is in namesofcities.txt.

---

# Appending Data when Commbining the Redirection of Standard Input and Standard Output - `>>`

To append data to a file when combining standard input and standard output, the `>>` can be used. For example, 

![image](https://user-images.githubusercontent.com/107522496/197985142-9a1dd2ea-5dba-4b16-9f98-574fc0afa1e6.png)

Here, the contents of namesofcities.txt are being sent into `cat`, which then sends (redirects) these contents to the end of the greeting.txt file. The orginal contents of greeting.txt remain and the data of namesofcities.txt is appended to the end. 

---

We can also combine Standard input and standard output to crete a new file. For example: 
 
![image](https://user-images.githubusercontent.com/107522496/197983326-85560532-4cc8-4594-9257-f08b122b15fa.png)

Here, the new-list.txt file does not exist, however, by redirecting the output to a file names new-list.txt, the system creates this file and sends the contents of standard input (in this case, the contents of namesofcities.txt) to new-list.txt.

---

#### Another Example 

![image](https://user-images.githubusercontent.com/107522496/197988384-f541f5a1-e97d-4ce2-97a7-60b377a1ed91.png)

In this example, the data from the numbers.txt is being sent into the `sort` command, and instead of sorting the data and outputting it onto the screen, instead, it is redirecting that **sorted** data into a file named sorted-numbers.txt. 

---

# Redirecting Standard Error - `2>`

By default, errors are outputted to the terminal. For example: 

![image](https://user-images.githubusercontent.com/107522496/197989637-a58935eb-0d5e-422c-b49e-57d47f3326c0.png)

Firstly, there is no command "echoo" so an error is sent to the terminal. Seoondly, because there the file "abcde" does not exist, the terminal is unable to read from it and throws an error to the terminal window. 

---

![image](https://user-images.githubusercontent.com/107522496/197995296-5b973959-c330-479a-a015-4479dc90294e.png)

> Note: in this example, the reason why there is an error is because numbers.txtt is not a valid name.

In the above example, even though we are redirecting standard output, the reason why the error shows up on the terminal is because errors are treated differently to output. 

This means errors are, by default, sent to the terminal. However, the errors can be redirected.

Just the way we use `<` to redirect standard input, and use `>` and `>>` to redirect standard output, we use the `2>` operator to redirect errors somewhere else.

![image](https://user-images.githubusercontent.com/107522496/197992396-f059d535-dce6-4473-8e2c-742c9f6a6340.png)

Here, instead of outputting the error to the terminal, the error is being sent to the errors-log.txt file. 

> Note: The reason why we may redirect errors is so to keep a log of them in a seperate file.

---

# Appending Data when Redirecting Standard Error - `2>> ` 

To append data to an error log for example, the `2>>` symbol is used. For example: 

![image](https://user-images.githubusercontent.com/107522496/197999459-2974367f-28e2-4c51-9fb1-84a633e63777.png)

So, this is how we redirect standard error. Either redirecting it to a file or appendinng it to a file. 

---

# Redirecting Multiple Streams 
 
Can also redirect multiple streams at one time.
 
Can redirect standard out and standard error at the same time. For example:
 
![image](https://user-images.githubusercontent.com/107522496/198004261-38e3aa01-3ff1-45fe-8def-456b1a4d661d.png)

Here, we are taking the contents of two files, animals.txt and namesofcities.txt and redirecting (using `>`) it to a new file called collection.txt. If an error occurs when running this commmand, the error will be redirected (using `2>`) to a file named errors-log.txt.

If the errors-log.txt file has already data in it and we don't want that data overwritten, we should use the `2>>`. For example:

```console
cat animals.txt namesofcities.txt > collection.txt 2>> errors-log.txt
```
> Note: when combining standard output and standard error, standard output comes first. 

---

# Redirecting Standard Ouput and Standard Error to the Same File - `2>&1`

To Redirect standard ouput and standard error to the same file, we can either use:

### Method 1

```console
cat namesofcities.txt > collection.txt 2>> collection.txt
```
or use:

### Method 2

```console
cat namesofcities.txt > collection.txt 2>&1
```

The `2>&1` means redirect standard error to the same destination where standard output is being redirecting to. This is used as a shortcut version to method one. SO, instead of writing the file name twice, we can just write `2>&1`.

---

# Newer Version of Redirecting Standard Ouput and Standard Error to the Same File - `&>`

Newer versions of bash support the `&>` redirecting standard ouput and standard error to the same file. 

```console
cat namesofcities.txt &> collection.txt 
```

```console
cat namesofcities.txt &>> collection.txt 
```

> Note: `&>` is used to redirect data to a file and overwrite any pre-existing data, whereas, the `&>>` appends the redirected data to the end of the file. 
> For example:

![image](https://user-images.githubusercontent.com/107522496/198009453-2dfc3387-6891-4070-a8c7-4835a1610c15.png)




















 








