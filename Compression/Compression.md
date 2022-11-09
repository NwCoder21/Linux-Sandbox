# Compression

## Archiving Files with TAR and gzip

In linux and Unix based systems, a common archive format is a TGZ file.

This section will be looking at how to create and extract such files. 

TGZ stands for TAR gzip. Archives are created using two different programs, TAR and gzip.

TAR (Tape Archive Utility) was initally designed to write files to tape - TAR would take multiple files and string them together into one file just like an archive does
> An archive, such as a zipped file, is a group of files inside one big file. 

So, TAR collects the files together and gzip takes the files and makes them smaller. 









---

# Compression Commands 


There are several compression commands which reduce the size of files. The three most popular compression commands are: 


* `gzip` - retains original file's ownership modes, access, and modification timestamps. Files which have been compressed using `gzip` have the `.gz` extension
* `bzip2` - Files which have been compressed using bzip2 will have the `.bz2` extension 
* `xz` - files which have been compressed using bzip2 will have the `.xz` extension 

# Syntax 

To compress a file using one of the three above compression commmands, 

```yaml
<compression_utility> [option] <file_name> 
```
For example:

```console
$ gzip test1.txt
```

will result in a compressed file calld test1.txt.gz AND **delete** the original file of test1.txt

# `-k` - Retaining Original Files

Using the `-k` option wiht any of the above three compression commands, compresses the file/s and also retains the original file/s.

Using the `-k` option in the above example:

```console
$ gzip -k test1.txt
```
will create a compressed file nameed test1.txt.gz AND **retain** the original file of test1.txt.

![image](https://user-images.githubusercontent.com/107522496/200800918-a8b837c6-d3bd-461e-b20b-c6b3c321204b.png)

--- 

# Compressiing Multiple Files

Two ways to compress multiplefiles at a time:

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

Archiving files allows to combibe mutiple files or directories into a single archived file. 

In linux, there are two main archive commands which have the ability to compress and archive files. They are:

* `zip`
* `tar`

The advantage of using of of the two above archive commands is that, in one command the file/s size will be reduced and packaged into a single archive file.  

---

## Creating a zip file

### Syntax 

```console
$ zip <archive_name>.zip <file1> <file2> ... 
```














