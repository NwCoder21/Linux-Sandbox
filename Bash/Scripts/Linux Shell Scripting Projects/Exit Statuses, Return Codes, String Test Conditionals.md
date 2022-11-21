# Exit Statuses, Return Codes, String Test Conditionals & Special Variables

In this lesson, we will be:

* using the logic that if a given expression is not true, then do something
* Will learn how to determine if a given command failed or succesed by checking the exit status of a command and how to control the exit status of our scripts.

---
# Displaying UID

![image](https://user-images.githubusercontent.com/107522496/203082522-2b5f43f9-a47b-453f-b194-7917354148c6.png)

UID is a shell variable that is set by default 

---

![image](https://user-images.githubusercontent.com/107522496/203084078-70dadffe-275f-4076-aa38-b4d3c0f7f4e7.png)

This line of code will display:

```yaml
Your UID is 1000
```
---

![image](https://user-images.githubusercontent.com/107522496/203085468-f8581d37-89cb-4ac9-986e-f4d7743d8141.png)

Here, we are following the concept of DRY (Don’t Repeat Yourself).
In this script, we will be referencing this variable multiple times, so, instead of writing the value of 1000 each time we need to, we will assign this value to a variable in one place and thereafter to it by using the variable name. This means if we ever need to change the value, only have to change it in one place

---

![image](https://user-images.githubusercontent.com/107522496/203089025-e52264e9-6627-4c17-a8c3-801c67e86ec2.png)

Here, if the UID is not 1000, the program will output "Your UID does not match 1000 "
Will use the `exit` command in order to stop the execution of the script. We can also supply an exit status after the exit command. We will supply one here.
The reason why we have specified 1 is because the script does not successfully execute all the way to the bottom as it should, so we will want to exit with a non-zero status.

---

# Exit Statuses

By convention, when a script or program executes successfully, it returns an exit status of zero/0. If it does not execute successfully for whatever reason, it returns a non-zero exit status.
Most of time, that exit status is 1, however, it can be any number such as 2, 99, 457 etc. You can use a variety of different exit statuses if you want. 

---

An example of this is the `useradd` command, which we will use later to add users: 

![image](https://user-images.githubusercontent.com/107522496/203090894-1ca9cf2d-4bb6-46b9-bc4f-b67a5d414583.png)

we can see from its man page that they are called exit values. 
For example, the exit status 9 means the username is already in use. So, if you write a script and you run the `useradd` command and you get an exit status of9, you know it means that , that username is already being used by someone else. 

---

![image](https://user-images.githubusercontent.com/107522496/203091060-78b9f6cb-ddab-4aa2-9993-8f73aa31faf7.png)

To see whay type of command `exit` is, we can use the `type -a` command. From this we can see that it is a shell built-in, so can use the `help` command to get more information on it.

![image](https://user-images.githubusercontent.com/107522496/203095322-4ddd725a-3423-45d0-ba30-c44788cfb557.png)

Here, we can see that we can use without any options. We know this because there is a ‘n’ in the brackets. That means it is optional.  This means if we just type `exit`, it will exit the shell. 
If you want to supply an exit status, can enter it after the `exit` keyword, such as `exit 1`.

If you omit the exit status, then the exit status is that of the last command executed. 

If you want to be explicit, then specify an exit status following the exit built-in command 

---

![image](https://user-images.githubusercontent.com/107522496/203095807-d0bb6209-d152-4a69-bec6-adb14888e64c.png)

If we test the script so far, this is what is printed:

![image](https://user-images.githubusercontent.com/107522496/203095927-06c84f80-078e-404f-97ca-37ee7ac1bf1b.png)

Your UID does not match 1000 is not printed because 

```yaml
if [[ "${UID}" -ne "${UID_T0_TEST_FOR}" ]]
```
is false.

---

Now let’s run the script with a different UID One way to do this is run the script using sudo privileges.
The root user always has the UID of 0.

![image](https://user-images.githubusercontent.com/107522496/203097393-bda54aa0-5cdb-46a8-ae53-cd8cccc50130.png)

Here, the `if [[ "${UID}" -ne "${UID_T0_TEST_FOR}" ]]` test equals true.

---

# Displaying Username 

![image](https://user-images.githubusercontent.com/107522496/203100394-e19ce88b-940e-4dcd-8a3d-f6b8a8e07108.png)

The `$()` syntax is used to capture the output of a command and send the output into a variable to be stored 

Then we want to test if that ID command successes using an IF Statement.
Bash has some special variables that it sets, and one of these special variables is `$?`. Can also enclose it within a pair of curly brackets  `{}` 

![image](https://user-images.githubusercontent.com/107522496/203103582-0ee64c24-7054-4931-b547-e36cb4c4698e.png)


`${?}` is a special variable which holds the exit status of the most recently executed command. 

In this case, the most recently executed command in out script is `id -un`. The status of that command is going to be stored in ${?}. Then we can use the `${?}` to do some comparisons and make a decision.
So, if `${?}` does not equal 0, it displays “the id command did not execute successfully."
Using `exit 1`, we will cause our script to exit too. 

If we pass this If Statement, it means the `id` command was successfully completed so we can display their username. 

---

![image](https://user-images.githubusercontent.com/107522496/203103844-7f70029f-853d-4306-abe3-1c504091b81a.png)

Let's execute this script.

![image](https://user-images.githubusercontent.com/107522496/203104413-01057f76-42dd-49cd-a421-12f6552702d5.png)

Here, we are using `id -un` to get the name of the current user.
The special variable `${?}` contains the exit code. From the above we can see it is 0.

We can  see that the exit stats of the `id -un` command is 0.

---

Now let's make the `id` command fail in some way. `id -unx` is not a valid option with `id`.

![image](https://user-images.githubusercontent.com/107522496/203105774-272b7aa3-e2ad-41f5-b124-ef4bdf52f61f.png)

We can see that the exit status, which is stored in `${?}`, of the failed command, `id -unx`, is 1.

If we want to test for success, we will want to test if it does not equal zero as that is the convention. 

---

# Testing Against a String 






















