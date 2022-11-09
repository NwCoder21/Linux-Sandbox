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






















