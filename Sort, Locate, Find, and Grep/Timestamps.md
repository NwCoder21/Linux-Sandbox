# Timestamps

There are three types of timestamps:

* `mtime`: modification time. This is the time the contents/inside of a file was last changed 
* `ctime`: change time. This is when the file was last changed. This occurs anytime `mtime` changes (contents are modfied) but also when the file is:
  * renamed
  * moved
  * has its permissions altered
* `atime`: access time. This time is updated when a file is read by anapplication or a command such as `cat`

![image](https://user-images.githubusercontent.com/107522496/198571823-bc94cc0a-d6e0-4593-9d64-41d4ef805f8f.png)

When running the `ls -l` command, the time printed is the last the inside of a file was changed. 

Use the `ls -lc` command to see the last change time.

![image](https://user-images.githubusercontent.com/107522496/198572346-08fedb21-e28c-4225-9372-2a2e314b65ac.png)

Here, I've changed the name of the mancity.txt file to mancity.txt and when checking the change time, we can see it shows the time it was last chanaged.

> If `mtime` changes, `ctime` will also change, but if `ctime` changes, `mtime` won't  change

---

# `ls -lu` - Checking Access Time 

To check the last time a file was accessed, use the `ls -lu` command 

![image](https://user-images.githubusercontent.com/107522496/198573512-710f4e92-ac4a-4bae-8ed8-6bf24e9b5141.png)




