# find


This command is used to recursively search for files or directories matching a certain pattern and prints out their relaltive path.

 ## Syntax:
```yaml
$ find . <location to start search from> <option> <what to find> 
```
The `-name` means the search will be case sensitive. To perform a case insensitive search, use the `-iname` option. See examples for both below:

![image](https://user-images.githubusercontent.com/107522496/197150178-7f3cedbe-d46c-42fe-a941-0849f91076a9.png)


---

# `*`

By using the `*` wildcard, we can search for a particular extension.  

![image](https://user-images.githubusercontent.com/107522496/197151287-8fa490f1-d54c-4278-a847-d185921a4540.png)

> Note: when using `*`, will need to enclose it with `''` 

---

# `-empty` - searching for empty files and directories 

when `find` is used with the `-empty` option, it will search for empty files and directories 

![image](https://user-images.githubusercontent.com/107522496/197152330-9882b4dc-dea4-4bf2-863f-a53c768a4e98.png)


---

# `-type`

The `-type` option can be used with three different characters:

* `d`: this searches for directories 
* `f`: this searches for files 
* `l`: this searches for symbolic links

![image](https://user-images.githubusercontent.com/107522496/197154202-22b6709d-1423-42e4-b6f1-f42da4c6bf79.png)

![image](https://user-images.githubusercontent.com/107522496/197154716-d7ba3703-0a06-44d6-b645-2eef292b6504.png)

---

# Searching Under Multiple Directories

Can also search for multiple directories: 

```yaml
$ find . <directory1> <directory2> <directory3> <what to find> 
```

![image](https://user-images.githubusercontent.com/107522496/197155818-5f65e3a7-5bbe-43c1-ab60-a299c227a579.png)














