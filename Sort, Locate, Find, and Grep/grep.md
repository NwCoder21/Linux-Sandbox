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





















