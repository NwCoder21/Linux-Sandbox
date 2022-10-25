# Redirection 

Normally, a command is run in the command line and its result is outputted to the terminal. However, there are ways we can *redirect* this output to somewhere else, such as another file, program, device, or even another command. This allows us to **chain** commands together in a **pipline**.   

There are three types of communication streams between a computer program and its enviroment 

* `Standard Input` (`stdin`): this is information inputted into the terminal by using a keyboard or another input device 
* `Standard Output` (`stdout`): this is information outputted once a command has been run
* `Standard Error` (`stderr`): this is an error message which is outputted when a falied process or incorrect command is run 

---

If the below commmand was run:

```console
echo "Hello World!!"
```
Here, `Hello World!!` is entered as the standard input and `Hello World!!` is then outputted to the terminal as standard out. However, we can redirect the output to a file instead of directing it to the terminal. To do this, we would use the `>` command followed by the filename of where we want to send the output. 

```console
echo "Hello World!!" > greeting.txt
```
In the above example, `Hello World!!` would be redirected to the `greeting.txt` file instead of outputting it onto the terminal. We can check that the redirection has worked b using the `cat` command followed by the name of the file we sent the direct to, for example, 

![image](https://user-images.githubusercontent.com/107522496/197761925-2ce542de-981e-4402-93fe-64c46ee7b838.png)

---





