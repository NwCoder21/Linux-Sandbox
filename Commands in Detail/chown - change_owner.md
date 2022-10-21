# `chown` - change owner 

This command is used to change the owner of a file. 

## Syntax:
```yaml
$ chown <newowner> <file> 
```

For example: 

## Syntax:
```yaml
$ chown helen test1 
```

In the above example, helen will become the new owner of the file test1.

An example of where `chown` may be used is when a file is owned by the root user. If another user wanted to make changes to this file, they would not be able to do so. The `chown`command can then be used to transfer the ownership to another user who then will be able to make changes:

![image](https://user-images.githubusercontent.com/107522496/197178796-4c04aee1-2729-41cb-9fcd-45265ceb3e12.png)

---

# `-R` - Changing Ownership of a Directory and all of its files 

`-R` option can be used to transfer ownership of a directory and all its files. 

```yaml
$ chown -R <newowner> <file> 
```

> Note: can also change the group of a file  or directory using the below syntax

```yaml
$ chown <newowner>:<newgroup> <file> 
```

> Using `chgrp` can just change the group of a file. The syntax for this will be:

```yaml
$ chgrp <newgroup> <file> 
```

