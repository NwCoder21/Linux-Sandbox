# Exit Statuses, Return Codes, String Test Conditionals & Special Variables

In this lesson, we will be:

* using the logic that if a given expression is not true, then do something
* Will learn how to determine if a given command failed or succesed by checking the exit status of a command and how to control the exit status of our scripts.

---

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

By convention, when a script or program executes successfully, it returns an exit status of zero/0. If it does not execute successfully for whatever reason, it returns a non-zero exit status.
Most of time, that exit status is 1, however, it can be any number such as 2, 99, 457 etc. You can use a variety of different exit statuses if you want. 
















