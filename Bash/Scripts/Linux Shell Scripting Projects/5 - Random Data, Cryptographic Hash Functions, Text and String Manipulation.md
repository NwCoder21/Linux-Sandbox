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

a quick way to execute a previous command that starts with a given string
---



