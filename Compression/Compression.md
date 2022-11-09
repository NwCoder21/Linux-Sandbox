

~~# Compression~~

~~Archiving Files with TAR and gzip~~

~~In linux and Unix based systems, a common archive format is a TGZ file.~~

~~This section will be looking at how to create and extract such files.~~

~~TGZ stands for TAR gzip. Archives are created using two different programs, TAR and gzip.~~

~~TAR (Tape Archive Utility) was initally designed to write files to tape - TAR would take multiple files and string them together into one file just like an archive does~~
~~> An archive, such as a zipped file, is a group of files inside one big file.~~

~~So, TAR collects the files together and gzip takes the files and makes them smaller.~~








---

# Compression Commands 


There are several compression commands which reduce the size of files. The three most popular compression commands are: 


* `gzip` - retains original file's ownership modes, access, and modification timestamps. Files which have been compressed using `gzip` have the `.gz` extension
* `bzip2` - Files which have been compressed using bzip2 will have the `.bz2` extension 
* `xz` - files which have been compressed using bzip2 will have the `.xz` extension 

# Syntax 

To compress a file using one of the three above compression commands, 

```yaml
<compression_utility> [option] <file_name> 
```
For example:

```console
$ gzip test1.txt
```

will result in a compressed file called test1.txt.gz AND **delete** the original file of test1.txt

# `-k` - Retaining Original Files

Using the `-k` option with any of the above three compression commands, compresses the file/s and also retains the original file/s.

Using the `-k` option in the above example:

```console
$ gzip -k test1.txt
```
will create a compressed file named test1.txt.gz AND **retain** the original file of test1.txt.

![image](https://user-images.githubusercontent.com/107522496/200800918-a8b837c6-d3bd-461e-b20b-c6b3c321204b.png)

--- 

# Compressing Multiple Files

Two ways to compress multiple files at a time:

* By adding all their names as arguments 

![image](https://user-images.githubusercontent.com/107522496/200803568-32d443b2-4f1a-4613-9cab-4be54f20d651.png)

* Using the `*` wildcard  

![image](https://user-images.githubusercontent.com/107522496/200806150-92631c02-5aa8-4902-8b9a-c59bea03a6fb.png)

This compresses all files in the current directory

---

# `-r`

`gzip` can be used with the `-r` option to compress all the files in the directory when providing a path to a particular directory

![image](https://user-images.githubusercontent.com/107522496/200808890-e8ecb6b6-dd9a-4c24-9c8f-fe4b376bd05d.png)

---

# `-d` - Decompressing Files

To decompress files, the `-d` option will be used.

![image](https://user-images.githubusercontent.com/107522496/200809577-b0649466-3634-4ef5-9273-7d024ca1ea38.png)

![image](https://user-images.githubusercontent.com/107522496/200809849-ade4d4e8-7604-4cc4-bc13-9408f9f8428c.png)

![image](https://user-images.githubusercontent.com/107522496/200810124-436952a7-9262-477c-accd-ac88812e2a6d.png)

---

# Archiving Files 

Archiving files allows to combine multiple files or directories into a single archived file. 

In linux, there are two main archive commands which have the ability to compress and archive files. They are:

* `zip`
* `tar`

The advantage of using of the two above archive commands is that, in one command the file/s size will be reduced and packaged into a single archive file.  

---
# `zip`

## Creating a zip file

### Syntax 

```console
$ zip <archive_name>.zip <file1> <file2> ... 
```

> Note: If your linux distribution does not have zip already installed, type in `sudo apt install zip unzip` 

To unzip a archived file, use the `unzip` command:

![image](https://user-images.githubusercontent.com/107522496/200820060-620adcc3-a9a8-4e7d-98c5-3a4dc94d6ff4.png)

Here, we compress and archive two files, test1.txt and test2.txt. We then move the archive file to the user directory and unzip it. 

---

# `zip -r` - Archiving Directories 

Can also compress and archive directories using the `-r` option with `zip`. For example:

![image](https://user-images.githubusercontent.com/107522496/200821406-23c3d84f-63b8-407f-a8c9-6d2d7718cc90.png)

---

# `tar`

`tar`stands for tape archive or tarball.

`zip` is more popular across platforms, however, `tar` is more used for when distributing archives among Linux systems. This is because `tar` archives store Unix file attributes, retaining file permissions and other metadata. 

# Syntax 

Compress files using `tar` with the `-cf` option

```yaml
$ tar -cf <archive_name>.tar <file_name/s or directories>
```

And to extract files in a `.tar` archive, we use the `-xf` option

```yaml
$ tar -xf <archive_name>.tar
```
For example:

![image](https://user-images.githubusercontent.com/107522496/200827986-7cdb1d3b-8d0e-41b4-9f59-67fd61278077.png)

--- 

# Compressing `.tar` Files

When the `-c` and `-f` options are used with `tar`, it allows to archive files or directories.

However, `tar` can also be used with other options to compress along with `-cf`:

* `-z` - compress the resulting archive using `gzip`. The resulting file extension will be `.tar.gz`
* `-j` - compress the resulting archive using `bzip2`. The resulting file extension will be `.tar.bz2`
* `-J` - compress the resulting archive using `xz`. The resulting file extension will be `.tar.xz`

![image](https://user-images.githubusercontent.com/107522496/200856481-a159671c-8de9-4d74-9912-ed8308ed5904.png)

The above will take the video1.mp4 and video2.mkv and compress them and archive called `zippedvideos.tar.gz`.

The reason why we combine compression and archiving utilities is because it is quicker. The longer way to achieve the above would have been:

![image](https://user-images.githubusercontent.com/107522496/200861977-57518b33-0667-4f67-ba60-02450a52142f.png)



---

# Decompressing & Extracting `.tar` files

In order to extract and decompress a `.tar` archive, change the `-c` to and `-x`. For example:


![image](https://user-images.githubusercontent.com/107522496/200859761-8154f603-cfd9-457f-91c9-4346b9e50073.png)

--- 

# Few More Examples 

Using `tar` command with `bzip2` compression to create a tarball of a directory using a single command. The desired name of the compressed archive will be compressedfootballteams.tar.bz2








