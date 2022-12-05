# Exercise 2

The following is the scenario and the requirements for this task:

![image](https://user-images.githubusercontent.com/107522496/205600222-cc8f7139-9302-49ca-819c-18835802d137.png)

---

<!-- 6:11 -->

Firstly, will be naming this script `add-local-users.sh`

![image](https://user-images.githubusercontent.com/107522496/205609183-6c07e7c3-ca34-47e5-8231-ac6d1ac5f22a.png)

---
![image](https://user-images.githubusercontent.com/107522496/205625155-15027ab0-8d12-41cf-879c-07108ad126fe.png)

Here, have added a header to tell anyone who accesses this script, what this scripts does.
Will also tell the user what they will need to provide.
Will also tell the user what information will be displayed to them at the end of the program.

---

#  Make sure the script is being executed with superuser privileges

We want to make sure that the script is being executed with superuser privileges, as no need to prompt the user for a username or password if we're not going to be able to use it anyway.

So, let's check that the script is being executed with superuser privileges.

---

![image](https://user-images.githubusercontent.com/107522496/205626140-847f862c-8e1b-4a11-8054-653b0e7f8c3e.png)

`if [[ "${UID}" -ne 0 ]]`

We're going to check the UID. This is set by bash. It's a shell variable that gets set any time bash is started and this variable UID is read only, so it can not be changed. 

We have also learnt that the root account always has a UID of 0, so we can test against the UID of 0. If the UID is not equal to zero, which means they're not executing with superuser privileges, then what we want to do is give them a message saying "Please run as sudo or as root."

`exit 1`: here, we are following convention and exiting with a non zero exit status. Since we're not doing anything specific with these exit statuses, we'll just use one.

```bash
if [[ "${UID}" -ne 0 ]]
then
        echo 'Please run as sudo or as root.'
        exit 1
fi
```

And that is our check for superuser privileges.

---

<!-- 10:10 --> 

# Getting the Username

![image](https://user-images.githubusercontent.com/107522496/205628455-e7031589-0447-490b-837f-c2a70e638df7.png)

Now, if the user has superuser privileges or is the root user, we need to start collecting information from the user.

We will do this by using `read` shel built-inn command.

`-p` stands for prompt. 

`USER_NAME`: we are going to assign what the user types into a variable called `USER_NAME`.

---

# Getting the user/appication's name 

![image](https://user-images.githubusercontent.com/107522496/205629678-9c4ecadb-4e2f-4533-802f-242d478e284e.png)

The next piece of information we need from the user is the account holder's real name. This is just going to be the contents for the description filled or comment filled in the password file. It does not have to be a real name, so, if someone is creating an account for an application, this might be the application name.

`COMMENT`: We are going to call this `COMMENT`.

---

# Getting the password 

![image](https://user-images.githubusercontent.com/107522496/205632113-a9437a90-f9fd-45a1-876b-14e33d396d4a.png)

Then we need to get the password from the user.

`PASSWORD`: we are going to assign the password to the `PASSWORD` variable.

--- 

# Creating the Account 

![image](https://user-images.githubusercontent.com/107522496/205632688-4f1636ef-1a1d-4ba9-b5ab-935f9fc74e37.png)

Now that we have all the information we need, we can no go ahead and create the account.

```bash
useradd -c "${COMMENT}" -m ${USER_NAME}
```

The `useradd` command requires root privileges. This is why we did the check at the start of this scriptto ensure user has these rights.

`-c`: here, we are using the `-c` option. We are supplying the name of the user or application that was given to us which was stored in the `COMMENT` variable. 

And we enclose that in quotes so that even if there will be spaces in this comment, it's all treated as the comment.

















