# Random Data, Cryptographic Hash Functions, Text and String Manipulation

Previously, we wrote a script that prompted the user to provide a password for the account that was being created. In this lesson, we will learn a few different ways to generate some random data, including how to automate the process of generating a random password.

---

![image](https://user-images.githubusercontent.com/107522496/207279396-591e70be-f7c7-48dd-8418-d1950a3f7b6d.png)

Firstly, will create a script called `vim luser-demo05.sh` in the `myscripts` folder

---

![image](https://user-images.githubusercontent.com/107522496/207279972-675f0120-a4ef-4617-8b07-ffeeaa1a89e4.png)

Then start our script with the SHEBANG (`#!/bin/bash`). And then some comments which lay out the objectives of this script.

---
Then let's take a look at bash man pages to see if it says anything on how to generate random data.  

```yaml
man bash
```

Then use:

```yaml
/RANDOM
```
to search for `RANDOM`.


Since `RANDOM` is in all capital letter, and by convention, variables are in all capital letters, we can probably assume that random is a bash built in variable. We can confirm this as if we scroll up and check the header, we will see that `RANDOM` is in the `Shell Variables` section.

---

![image](https://user-images.githubusercontent.com/107522496/207290284-91199e29-be21-4fc2-abe2-1a9ff5f4c9a0.png)

It says Each time this parameter is referenced, a random integer between zero and 32,767 is generated. Let's test this out in the terminal first.

---

![image](https://user-images.githubusercontent.com/107522496/207290647-35291958-0edd-4ea3-8793-dcb12d2f733a.png)

From this we can see that everytime we access it again, we get different numbers each time we echo the random variable to the screen here.

We can see that by using `RANDOM`, we can get random data.

---

![image](https://user-images.githubusercontent.com/107522496/207291426-228b9956-dc9d-4d84-abe6-df1e521f18ad.png)

The first typeof password we are generating is a random number as a password.

---

![image](https://user-images.githubusercontent.com/107522496/207291934-8ff55b95-b416-497c-b7ec-7718f1901478.png)

Here, I have given the script executable rights.

---

![image](https://user-images.githubusercontent.com/107522496/207292274-0a487380-27cc-4aa7-bd05-f8c2c0cff1ca.png)

From this, we can see that everytime we run the script, a new number is generated.

---

# Event Designator

```yaml
!v
```

This is a called an event designator. It uses the `!` symbol. So, `!v` will execute the most recent command which started with a v, in this case `vim luser-demo05.sh`.
Another example is, if the last command we ran which started with a `l` was `ls`, we can use `!l` to run it.

This is a quick way to execute a previous command that starts with a given string.

when you use this, it will also display underneath the command it is running and then under that, the output of that command.

---

So just using `"${RANDOM}"` might be good enough, especially if the user is forced to change their password on log in.

If you are concerned about security, perhaps you would like a fairly long password. So, let's do something like use two or three random numbers all together.

---

![image](https://user-images.githubusercontent.com/107522496/207295074-835a9f0a-d248-4fde-987b-d7741bd16ce1.png)

We'll reassign our `PASSWORD` variable to random and do this three times and then output that passwordto the screen.

---

![image](https://user-images.githubusercontent.com/107522496/207295609-cc67d645-9ffe-4d41-9e6a-a24efbc92158.png)

The first password is one random number and the second password is three random numbers together.

---

# `date`

We can also improve this script. Something that is always changing is time. It's never the same time ever again. This is some data which is always changing.

So let's use the current date and time as the basis for a password to generate. So, let's take a look at the `DATE` command and some of its options using:

```yaml
man date
```
---

![image](https://user-images.githubusercontent.com/107522496/207296482-9e1c6905-5a9c-4fe8-ba69-a128f0bb4844.png)


We can see that this command prints or sets the system date and time.

from the Synopsis we can see that it can be used with multiple options and also in brackets, which means it is optional, is some form of format.

So let's check out the different formats that are available to us. To do this, use:

```yaml
/FORMAT
```

---

![image](https://user-images.githubusercontent.com/107522496/207297377-65bcd3d1-1077-4516-aa4c-548ad1849763.png)

Here, it says format controls the output and each one of these looks like they begin with a percent sign.

For example, `%a` is the locale's abbreviated weekday name (e.g., Sun), and `%A` is locale's full weekday name (e.g., Sunday).

---

![image](https://user-images.githubusercontent.com/107522496/207298143-48df9381-0775-4d34-bfa0-d1e7a9549a4a.png)

If we look at `%s`, it says: seconds since 1970-01-01 00:00:00 UTC. This particular date is called **The Epoch** and some people actually call this epic time or **Unix time**. This is the number of seconds that have elapsed since January 1st, 1970. Let's take a look at this in the terminal

---

![image](https://user-images.githubusercontent.com/107522496/207298700-63244bfc-8bec-49ea-b1dc-87f2d33516cd.png)

The `+` means that we want to use a format with the `date` command. 

This is the number of second since January 1st, 1970. This number just continually increments every single second, so we could actually use this as a password.

---

![image](https://user-images.githubusercontent.com/107522496/207300374-87b6f7c4-fb54-4c46-abbc-0dd314e11b81.png)

 > Note: that the dollar sign, opening parentheses and then a command followed by the closing parentheses takes the output of that command within the parentheses and assigns it to the variable.

---

![image](https://user-images.githubusercontent.com/107522496/207300206-99631797-58d6-4e39-9f53-b1041ac449c4.png)

We can see that the last number, where we used the `date` command, is incrementing everytime.

---

Let's make this password even more secure. Lt's go back to the `date` man page using:

```yaml
man date
```
---

![image](https://user-images.githubusercontent.com/107522496/207300817-082b1f8f-248c-4e92-95a2-265824345e42.png)

Here we have the nanoseconds format. When you use this format, it prints the nanosecond that the date command was executed. So there's about nine digits here so that leaves us a lot more data to guess.It would be really hard to guess these nanosecond.

So if we actually combine that with the UNIX time we saw in the last section, then we can generate a long number.

---

![image](https://user-images.githubusercontent.com/107522496/207302983-58d75e7c-f62c-468c-9113-4090c94688fa.png)


Now, when we combine the UNIX time and nanoseconds, the first part (%s, UNIX time) changes slightly, however, the second part (%N, nanoseconds), chnages a lot.


Now let's use this pattern as a password in our script.

---

![image](https://user-images.githubusercontent.com/107522496/207303687-4c965678-902e-45e6-b040-f6b66282f97b.png)

This is what it look like now. 

---

![image](https://user-images.githubusercontent.com/107522496/207303919-14854d3a-d94a-4a33-8661-4c12159150e4.png)

---

# checksum

Let's take this one step further by using checksums or cryptographic hash functions. 

A checksum is a numeric value computed for a block of data that is relatively unique. Check sums were and are used to verify the integrity of data such as files. For example, if you download a file and you want to make sure that it's not corrupt in some way, you find the published checksum for the file and compare it to the file you downloaded.

<!-- 11:18 till 15:12: example of CENTOS --> 

---

![image](https://user-images.githubusercontent.com/107522496/207305027-29a3e117-3e08-4b46-953b-fdcd15362f66.png)

All these programs do pretty much the same thing. They take a big chunk of data and reduce it down to a single number or a string that represents that chunk of data to verify if it's the same or not.

---

# `sha256sum`

Let's get back to password generation. checksums are actually hexadecimal numbers with 0-9 representing 0 to 9, and A through to F representing the values from 10 to 16.

For example, if we were to use a sha256 sum as a password, that password would consist of 16 different characters, from 0 to 9, and A through to F and it would be be 64 characters in length.

Let's turn the current date and time into a sha256 sum by piping the output of the date command as the input into the sha256 sum command.

---

![image](https://user-images.githubusercontent.com/107522496/207308455-ec6e1957-e273-4b67-ad8f-bd487f5428aa.png)

This is the sha256sum of the output of the date command at the time this was executed.

> Pipe symbol takes the output of the preceding command and sends it as a standard input to the following command.

---

So, how does this work? Let's look at the man page for `sha256sum`:

![image](https://user-images.githubusercontent.com/107522496/207308847-1144430c-2c30-49e3-9171-b4e064537c76.png)

From the Synopsis, we can see that `sha256sum` can be used with optional options as well as optional files.

**"With no FILE, or when FILE is a -, read standard input." - this means a pipe turns the output of the previous command as standard input in the command that follows the pipe.**

**Most commands work like this. If they take a file as an argument, you can also not use the file and instead use standard input via a pipe and it will operate on that input.**

---

Becuase our objective is to generate a seemingly random set of characters as a password, we really don't care if the `sha256sum` remains intact or not. We're not going to be using that checksum to check it against another piece of data. We just want the output from the `sha256sum`.

---

<!-- 17:24 --> 

# The `head` command

So, if we want to control the size of this generated password, we will need to control the number of characters returned or displayed.

One way to do this is by ussing the `head` command. 

Question: how can you tell if `head` is a program on the system or if it's a shell built in?

Answer: use:

```yaml
type -a head
```
in the terminal.

---

![image](https://user-images.githubusercontent.com/107522496/207310760-53ffbf93-4876-426c-895a-ac1ee92703a5.png)

`/usr/bin/head` means `head` is a program. This means we can't use `help` with it, instead, we use `man head`.

---

![image](https://user-images.githubusercontent.com/107522496/207311122-9e2160fd-aef2-4166-a81c-0cdb3ad4394f.png)

`head` outputs the first part of files or the "head" portion of a file. Without any option specified with `head`, itwill print out the first 10 lines of a file.

Just like the `sha256sum` command, under `head`it also says "With  no  FILE, or  when FILE is -, read standard input.". So, we know we can use this `head` command in conjunction with the pipe.

`-c` option is used to print  the first K bytes of each file.
`-n` option print the first K lines instead of the first 10.

Let's try out these options in the terminal.

---

![image](https://user-images.githubusercontent.com/107522496/207312698-2248608a-09ac-44ba-8a76-1519385f0417.png)

Here, by using the `-n1` option, it will print out the first line of the `/etc/passwd` file.

Can use both styles, `head -n1` or `head -n 1`.

`head -1` is the older way of doing the above.

---

Another example is:

![image](https://user-images.githubusercontent.com/107522496/207312969-730e80a6-1cff-496d-afbb-c56098aea7be.png)

Here, we are printing out the first two lines from the `/etc/passwd` file.

Continue from `19:40`





















---


# Code

```bash

#!/bin/bash

# The aim of this script is to generate a list of random passwords

# A random number being set as the password 
PASSWORD="${RANDOM}"
echo "${PASSWORD}"

# Three random numbers together 
PASSWORD="${RANDOM}${RANDOM}${RANDOM}"
echo "${PASSWORD}"

# Use the current date/timeas the basis for the password.
PASSWORD=$(date +%s)
echo "${PASSWORD}"


# Use nanoseconds to act as randomization.
PASSWORD=$(date +%s%N)
echo "${PASSWORD}"

```





















