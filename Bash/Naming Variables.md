# Naming Variables

By convention, not by rule or syntax, variables are in all uppercase. The benefit of doing this is that way you 
can typically easily spot what is a variable and what is not.

But can still use all lowercase if you want to

![image](https://user-images.githubusercontent.com/107522496/201318445-2d42f658-3bce-4997-bf4e-610510fc1dcf.png)


---

Strings are enclosed in quotation marks, single or double quotation marks. 

Variable names can contain letters, numbers and underscores but they can’t start with a digit. For example, the following are all valid variable names:

•	WORD
•	WORD1
• _WORD

However, the following would not be valid names 
•	3WORD is not a valid variable name as variables can not start with a number
•	A-WORD is not a valid variable name as variables can not contain a dash. 
•	E@MAIL is not a is not a valid variable name as variables can not contain @ symbol 

--- 

# Difference between single and double quotes

![image](https://user-images.githubusercontent.com/107522496/201318470-16dda52d-93c5-40a9-b5d9-9a4a20a77247.png)


Single quotes prevent the expansion of variables. So, if you want echo to display exactly what you specify, put it in single quotes.
If you want variables to be interpreted, make sure that you use double quotes.
Can use this functionality with other commands, not just with Echo.

So: 

![image](https://user-images.githubusercontent.com/107522496/201318530-91431501-c047-4d0f-ac4a-3c71a41ef228.png)

Will output: $WORD

So, you can see, using single quotes, displays exactly what is in the single quotes. 
It doesn't do any expanding or interpreting of the variables. It's exactly what you specify.

So, just keep that in mind. If you're using variables, use double quotes. 
If you want to be very specific and make sure that nothing gets changed, use single quotes.

---

# Combining variables with hard-coded text 

![image](https://user-images.githubusercontent.com/107522496/201318858-504b93f2-7d63-466a-81ed-c5eb7fa6de39.png)

This outputs: `This is a shell script`

---

![image](https://user-images.githubusercontent.com/107522496/201318945-3dd8f394-c945-483e-bd76-7761ad91aa5c.png)

Can also enclose the variable name in curly braces and precede the opening brace with a dollar sign.
So, the syntax is dollar sign opening curly brace, then the variable name followed by a closing curly brace. 
Both types of syntax can be used. 

This also outputs: This is a shell script

> Note: Note: when you're reading scripts written by others, you'll see both types of syntax being used. 
> You'll see the dollar sign with the variable name as well as the dollar sign, including the braces in the variable name.

---

# Appending text to a variable 

To append text to the variable, we have to use the dollar sign brace syntax `${}`

![image](https://user-images.githubusercontent.com/107522496/201319202-3a943bab-be8c-4879-8c9f-de38c9e3c54b.png)

If we want to append “ing” directly after the output of the variable, we have to use the curly braces, 
otherwise, Bash doesn't know that the variable is actually “WORD” and that the part that's not the variable is “ing”.

It has no way of knowing that unless you use the braces to separate the variable from the preceding or following text 

This will output: `scripting is fun`

---

# How not to append text to a variable 

![image](https://user-images.githubusercontent.com/107522496/201319384-28fa0e7c-8672-4658-9afb-c3f37409cf4f.png)

This will output: `  is fun!`

---

![image](https://user-images.githubusercontent.com/107522496/201319484-d9cfc208-4f45-47ae-b9ec-2b359b83b9fb.png)

Here used single quotes as wont be doing any variable expansion here. We're just doing a straight assignment of “ed” to the variable ENDING. 
This will output: `This is scripted.`

---

# Reassignment – changing value of a variable

We can overwrite the contents of the variables just using assignments

![image](https://user-images.githubusercontent.com/107522496/201319614-86a984ff-c3d0-430b-b71e-a8eaf573b453.png)

This will output: `This is scripted. scripting is fun!`

---

![image](https://user-images.githubusercontent.com/107522496/201319715-380cb4af-2c02-4645-a067-15efe96422bf.png)

This will output: 
`scripting is fun`
`  is fun!`
`This is scripted.`
`scripting is fun`
`You are going to write many scripts in this class!`































