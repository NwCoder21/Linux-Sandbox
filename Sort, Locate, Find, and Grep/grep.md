# grep 

This is used to search for information within files by searching for patterns provided byt the user in each file's contents. `find` searches in filenames, whereas `grep` 
searches within files and text. 
* `grep` outputs each line which matches the pattern the user provides. 

Syntax
```yaml
$ grep <pattern> <file_name> 
```
![image](https://user-images.githubusercontent.com/107522496/199477920-fd97fb2c-8692-4f61-8bf1-a9df77805ef4.png)

In the above example, the `grep` command searches for the pattern london in the animalsandcities.txt file and prints it out.

---


# The `-i` option 

`grep` is case-sensitive. to make it not case insensitive, use the `-i` option. For example,

```yaml
$ grep -i "london" nameofcities.txt
```

---

# The `-w` option  

When using this with `grep`, it tells the grep commmand to look for the exact pattern provided and not for it to be part of a word. For example; 

```yaml
$ grep -w "man" cities.txt 
```
will match the word man but not mancity.

![image](https://user-images.githubusercontent.com/107522496/199530582-d5e30ed3-8a8c-44db-b61d-3fa656a7e4ef.png)

Here, we can see that `grep  "tree" shortstory.txt` looks for any words which contain the pattern tree. This includes words such as trees. Whereas, `grep -w  "tree" shortstory.txt` only returns words which match tree exactly.

---

# Using `grep` Recursive Search 

Can use the `-r` option to search the current directory and any nested directories and files for the pattern provided. 

![image](https://user-images.githubusercontent.com/107522496/199532774-cb2f4c09-0914-400c-9412-a43ad13bd4dc.png)

Can also provide the `grep` command a directory to search in if don't want to search in current directory. For example:

![image](https://user-images.githubusercontent.com/107522496/199534578-bf41f5a0-a2d8-4923-9cc2-19851959bc33.png)















