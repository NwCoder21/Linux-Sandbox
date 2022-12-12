# Project 2 - Creating Local Users

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

`-c`: here, we are using the `-c` option. We are supplying the name of the user or application that was given to us which was stored in the `COMMENT` variable. And we enclose that in quotes so that even if there will be spaces in this comment, it's all treated as the comment. So, for example, `James Smith` will be treated as one thinf, and won'tbe treated as two seperate things.

`-m`: we want to ensure that the Home Directory is also created.

`USER_NAME`: we also want to add the username to the `useradd` command, this is where we do that.

---

# Checking success of the above command.

![image](https://user-images.githubusercontent.com/107522496/205647690-d9728452-9019-44fd-8588-fe9287c090cc.png)

```bash
if [[ "${?}" -ne 0 ]]
then
        echo 'The account could not be created.'
        exit 1
fi

```

To check that this command (`useradd -c "${COMMENT}" -m ${USER_NAME}`) is a success, we can check the exit status of the `useradd` command.

`${?}`: We learnt is the previous lesson that the exit status of the most previously executed command, is stored in `${?}`.

If the exit status is 0, it means that everything went well and the command was a success.

`-ne 0` - and if the exit status is not equal to 0, it means something went wrong and we will display an error message saying "The account could not be created.".
`exit 1` - and we will exit this script with a non-zero exit status.


If we get passed this if statement, it means that the `useradd` command was a success.

---

<!-- 13:46 -->

# Setting the Password for the Account 

![image](https://user-images.githubusercontent.com/107522496/205682302-e99ef6ed-a677-4342-a0e7-2528058ec136.png)

Here, we are echoing the password and then pipe that output as as the input to the `passwd` command with the `--stdin` option. Here, we also supply the `USER_NAME` variable to the `passwd` command.

`if [[ "${?}" -ne 0 ]]` - here, we an also check to see if the password command succeeded and if the password was properly set on the account. 

---

<!-- 14:45 -->

# Forcing a Password Change on First Login.

![image](https://user-images.githubusercontent.com/107522496/205684226-6d349a0b-f051-4028-bd08-99886fa65c36.png)

Finally, we also want to force the password change on first login.
 
We can do this with the `passwd` command with the `-e` option and provide it with the username we want t do this with.

---

Now we have set the password and forced a change on the first login.

---
# Displaying Username, Password and Host Where User was Created

![image](https://user-images.githubusercontent.com/107522496/205685871-d0cddd9a-24f8-4455-bca1-b78f8aa67172.png)

What we want to do now is, display this information to the person running the script, so that they can then hand it off to the user that will be using the account.

To create a blank line in the output, we can use the `echo` statement on its own, without any options or arguments. The echo statement displays what is passed to it and a new line. So if you don't pass anything to `echo`, it's going to print a blank line.


--- 

# Getting the Host Name

To learn how to get the hostname, go to `man bash` page.

![image](https://user-images.githubusercontent.com/107522496/205686578-4d964a91-6df3-4769-bc4c-be47c62c72dc.png)

Once in the bash page, type `/hostname` and press enter. We will then see..

![image](https://user-images.githubusercontent.com/107522496/205686988-5655705f-9b5f-4949-9175-681f13b13c89.png)

As the hostname is in all ppercase letters, we konw that something in all uppercase letters can be a variable name. So this variable says, that it's automatically set to the name of the current host.

We also can check that it is a variable by scrilling up and checking what section it comes under. 

![image](https://user-images.githubusercontent.com/107522496/205687526-83448964-a890-45a3-92f9-954ca4e42677.png)

We can see that `HOSTNAME` is under the `Shell Variables` section.

---

![image](https://user-images.githubusercontent.com/107522496/205688010-f57cbedf-e4f9-4b78-92d8-2f0916342d81.png)

To check the value of `HOSTNAME`, we can type `echo ${HOSTNAME}`.

---

So let's get back into our shell script and add this last bit of information.

![image](https://user-images.githubusercontent.com/107522496/205688631-078588d6-04f4-4463-8e31-b5274fc15195.png)

So if we get to this point, the script is really complete and it's completed successfully. So, by convention we need to exit with a zero exit status. We can do this bu using `exit 0`.

---

# Testing the Script

To add a user with the above script, run it with `sudo`.

![image](https://user-images.githubusercontent.com/107522496/205692088-eff736ee-9a93-4dca-bd2f-144424559ec7.png)

---

![image](https://user-images.githubusercontent.com/107522496/205692570-5157ccbd-8b10-4242-84a7-cf5acc764ad4.png)

Looks like the script was executed successfully. We can check the exit status with `echo "${?}"`. 0 means it was successful. 

---

# Checking if the user was created

![image](https://user-images.githubusercontent.com/107522496/205693289-b94be94f-6cec-4662-979d-99b4605ab47b.png)

Use the `cat /etc/passwd` command or the tail `/etc/passwd` command to check if the user has been created. We can also see that the comment has been included in the account line.

---

![image](https://user-images.githubusercontent.com/107522496/205694606-e72c2b05-1bdc-42df-93c5-8a4d15b83449.png)

To check further that it has been created, use `su - <User_Name>`

`su` this is used to switch user.
`-` is used to get the user's login enviroment.
`guyCheshire` is the username

It then asks us for the password we initally used. And then forces it to be changed

This has shown that the script works as it should.

---

# Running the script without the correct privileges.

Type `add-local-users.sh`

Can also run `echo "${?}"` to see the exit status of the scrit. In this case, it is a non zero exit status, 




![image](https://user-images.githubusercontent.com/107522496/205695458-f0550abc-7ec5-4f32-b089-054cab3ec11c.png)

# Code 

```bash 
#!/bin/bash

# This script creates a new user on the local system.
# You will be asked to enter the username (login), the person's name, and a password.
# The username, password and host for the account will be displayed

# Make sure the script is being executed with superuser privileges.
if [[ "${UID}" -ne 0 ]]
then
        echo 'Please run as sudo or as root.'
        exit 1
fi

# Get the username (login) 
read -p 'Enter the username you want to create: ' USER_NAME

# Get the real name (contents for the description field) 
read -p 'Enter the name of the person or application that will be using this account: ' COMMENT

# Get the password 
read -p 'Enter the password to use for the account: ' PASSWORD

# Create the account 
useradd -c "${COMMENT}" -m ${USER_NAME}

# Check to see if the useradd command succeeded or not.
# We don't want to tell the user that an account was created when it was not.
if [[ "${?}" -ne 0 ]]
then
        echo 'The account could not be created.'
        exit 1
fi

# Set the password.
echo ${PASSWORD} | passwd --stdin ${USER_NAME}

# Check if the password command succeeded
if [[ "${?}" -ne 0 ]]
then
        echo 'The password for the account could not be set.'
        exit 1
fi

# Force password change on the first login.
passwd -e ${USER_NAME}

# Display the username, password, and the host where the user was created.
echo
echo 'Username:'
echo "${USER_NAME}"
echo
echo 'Password:'
echo "${PASSWORD}"
echo
echo 'Host name:'
echo "${HOSTNAME}"
exit 0


```










