# df (disk free) 

This command is used to retrieve information regarding the disk usage, total space and available space, of a file system

The difference between the df command and the du command is that df provides a an ovrall figure for the amouunt of space being used on your filesystem as a whole. The du command provides a more accurate figure of any given directory or subdirectory.


## Syntax:
```yaml
$ df <option> <file> 
```
---

When using this wth no file specfied, it will display the amount of space available on all currently mounted file systems.

![image](https://user-images.githubusercontent.com/107522496/196984091-ec0f7c15-7582-4467-bc42-b3d08f68df17.png)

When specfiying a file, it will display the mount information of that specfied file.

![image](https://user-images.githubusercontent.com/107522496/196984366-649bff19-a3d2-48c9-93ed-3d95554090a1.png)

---

## `-h` option

Using `df` with the `-h` option will display the volumn sizes in power of 1024

![image](https://user-images.githubusercontent.com/107522496/196985567-1b299493-84e4-4b6c-9716-fb528c16780a.png)









