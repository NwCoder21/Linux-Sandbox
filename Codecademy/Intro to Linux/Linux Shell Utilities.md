# Linux Shell Utilities

## Network Utilities

Almost every computer in the world is now connected to a network. 
The Linux shell makes it easy to communicate with content on the Internet from the command line, and for the user to 
check on important network status information. In this exercise, we will introduce a few tools that you may find useful.


## Interacting with Files Hosted Online

Let’s start simple: how do we access files from the Internet in the command line? There are two commands that allow us to do just that: `curl` and `wget`. Either command lets us establish a connection with a server. We can also use them to download the file at the destination.

```yaml
$ curl <URL in quotes>
```

displays the contents of the file at the URL in terminal.

The option `-o` or `-output` combined with a desired name

```yaml
$ curl <URL> --output <desired_filename>
```

lets us write the contents of the online file to the filename! For example, `curl -O "https://www.google.com" --output frontpage.html` will download the HTML file of the Google homepage to a local file called `frontpage.html`.

There are more commands if we type `curl --help` or `wget --help`. As always, you can also use the `man` command to read about the commands.

---

## Checking Network Connectivity

How can we check whether two devices connected to the same network can communicate with one another? Simple! We use a command called `ping`, short for Packet INternet Groper. The command

```yaml
ping [options] <target domain or IP>
```

sends packets to the target host and waits for replies. If the ping command returns with a failure, that means the target is unreachable.

---

## DNS Resolution

What if we wanted to find out the IP address for any given domain name or vice versa? This process is known as DNS lookup or DNS resolution and the host command lets us do exactly that. The basic syntax for the host command is: `host <domain or IP>`.

For example, the command `host google.com` will generate the following output:

```yaml
google.com has address 142.250.72.238
google.com has IPv6 address 2607:f8b0:4007:817::200e
google.com mail is handled by 20 alt1.aspmx.l.google.com.
google.com mail is handled by 40 alt3.aspmx.l.google.com.
google.com mail is handled by 30 alt2.aspmx.l.google.com.
google.com mail is handled by 10 aspmx.l.google.com.
google.com mail is handled by 50 alt4.aspmx.l.google.com.
```

---

## Network Interface Status

The `ifconfig` command, or interface configurator, is one of the network inspection commands available on Linux. Running it will display IP addresses, MAC addresses, and some more relevant details.

These commands are really useful if you work with networks specifically! If you’d like to learn more about networks, check out our Introduction to [Network Basics lesson](https://www.codecademy.com/courses/introduction-to-cybersecurity/lessons/network-basics/exercises/introduction-to-network-basics). 

As always, we recommend using `man` or info for more detail on these commands as we are barely skimming the surface of what these commands can do!

---

# Practise 

Step 1: Use `wget` to download Codecademy’s homepage, www.codecademy.com.

Answer: 

![image](https://user-images.githubusercontent.com/107522496/212705330-b46c9a2a-8685-41ef-a5e3-b5151d80451e.png)

---

Step 2: Use `curl` to download the file from the URL, https://static-assets.codecademy.com/Courses/learn-linux/secret-file.txt.

Answer: 

![image](https://user-images.githubusercontent.com/107522496/212705643-39369cdc-e79a-424e-b593-dc321b66b25a.png)

---

Step 3: Use the `host` command to look up the IP address for the domain `codecademy.com`

Answer: 

![image](https://user-images.githubusercontent.com/107522496/212705756-59466ecd-d90d-4e07-ab95-e5d8d723aa7e.png)

---

Step 4: Use the `ping` command to ping one of the IP addresses you found from the last checkpoint.
Note: Make sure to interrupt ping with `CTRL` / `CMD` + `C`, otherwise it runs indefinitely. Alternatively, we can specify how many packets we wish to send using the `-c` option.

Answer: 

![image](https://user-images.githubusercontent.com/107522496/212706005-47a1fbbb-e4e3-494c-b040-bfc958f79b08.png)

---

Step 5: Run the `ifconfig` command and observe the result.

On the left, you will see all the available network interfaces, including virtual network interfaces. For each interface, you will see:

* `HWaddr`: MAC address of the ethernet interface
* `inet`: IPv4 address assigned to the interface
* `inet6`: IPv6 address assigned to the interface
* `MTU`: Maximum transmission unit

Answer: 

![image](https://user-images.githubusercontent.com/107522496/212706651-8a19c4a3-2ba0-4c59-86ee-f44d3cfd33da.png)

---

# Review

Good job on reaching the end of this lesson! You are now well-equipped or at least aware of the number of utilities available in the Linux shell. To review, we talked about:


## Documentation

Documentation is a great way to learn about installed utilities.

* The `/usr/share/doc/` directory contains README files and other documents for installed commands.
* `man` is a command to access reference manual pages for all installed commands. Usage: man <command_name>.
* `infois` a command to access full-detailed information pages for all installed commands. Usage `info <command_name>`.

## Compression

Compression reduces file sizes. Three popular compression commands are `gzip`, `bzip2`, and `xz`. To compress, run commands like so: 

```yaml
<compression_utility> [options] <file_name>. 
```

To decompress, include the `-d` option: 

```yaml
<compression_utility> -d <compressed_file_name>
```

`gzip` also supports the `-r` option to compress all files in a directory.

## Archive

`zip` and `tar` are two archiving utilities that package multiple files into a single archive file. `zip`: archives and compresses files.

* Archive: `zip <archive_name>.zip <file1> <file2>...` Use `-r` option for directories.
* Extract: `unzip <archive_name>.zip`.

`tar`: only archives files by default but has options to utilize compression utilities. Unlike `zip`, it preserves Unix file attributes like file permissions.

* Archive: 
 
```yaml
tar -cf <archive_name>.tar <files or directory>
```

* Extract: 

```yaml
tar -xf <archive_name>.tar
```

* Add options `-z`, `-j`, or `-J` to compress via `gzip`, `bzip2`, or `xz` respectively.

## Networking

Basic network commands:

* `curl` or `wget`: Interacts with a webpage or file hosted online.
* `ping <target domain or IP>`: Checks connectivity between two devices on the same network.
* `host <domain or IP>`: Performs DNS lookups.
* `ifconfig`: Shows network interface information

























