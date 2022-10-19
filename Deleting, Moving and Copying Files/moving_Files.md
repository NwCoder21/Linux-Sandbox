# How to Move Files and Directories 

# `mv`

The `mv` command is used to moves files. Similar to `cp` in usage, however, `mv` moves a file without making a copy.

## Syntax:
```yaml
$ mv <source> <destination> 
```

For example: 
```yaml
$ mv testFile.txt testDirectory 
```
will move the testFile document into the testDirectory folder

> Note: the destination can be a relative path or absolute path
---



Can use `mv` to move multiple files. The first arguments will be the source files and the last argument will be the destination directory. For example: 

```yaml
$ mv test1.txt test2.txt test3.txt other/
```
will move the test1, test2 and test3 files into the _other_ folder

Note: if the destination is a directory, do not forget the `/`.

---

# Renaming a File

To rename a file, the first argument will be the old file name and the second argument will be the new file name. For example: 

```yaml
$ mv test4.txt test5.txt
```

here, the test4 file will be renamed as test5


---





