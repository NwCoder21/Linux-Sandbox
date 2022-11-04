# grep 

This is used to search for information within files by searching for patterns provided byt the user in each file's contents. `find` searches in filenames, whereas `grep` 
searches within files and text. 
* `grep` outputs each line which matches the pattern the user provides. 

Syntax
```yaml
$ grep <pattern> <file_name> 
```
![image](https://user-images.githubusercontent.com/107522496/199477920-fd97fb2c-8692-4f61-8bf1-a9df77805ef4.png)

In the above example, the `grep` command searches for the pattern london in the animalsandcities.txt file and prints it out.

---


# The `-i` option 

`grep` is case-sensitive. to make it not case insensitive, use the `-i` option. For example,

```yaml
$ grep -i "london" nameofcities.txt
```
---

# The `-w` option  

When using this with `grep`, it tells the grep commmand to look for the exact pattern provided and not for it to be part of a word. For example; 

```yaml
$ grep -w "man" cities.txt 
```
will match the word man but not mancity.

![image](https://user-images.githubusercontent.com/107522496/199530582-d5e30ed3-8a8c-44db-b61d-3fa656a7e4ef.png)

Here, we can see that `grep  "tree" shortstory.txt` looks for any words which contain the pattern tree. This includes words such as trees. Whereas, `grep -w  "tree" shortstory.txt` only returns words which match tree exactly.

---

# Using `grep` Recursive Search 

Can use the `-r` option to search the current directory and any nested directories and files for the pattern provided. 

![image](https://user-images.githubusercontent.com/107522496/199532774-cb2f4c09-0914-400c-9412-a43ad13bd4dc.png)

Can also provide the `grep` command a directory to search in if don't want to search in current directory. For example:

![image](https://user-images.githubusercontent.com/107522496/199534578-bf41f5a0-a2d8-4923-9cc2-19851959bc33.png)

--- 
# `-c` 

The `-c` option displays how  many matches have been found. 

![image](https://user-images.githubusercontent.com/107522496/199536906-8b1b972f-35ce-474d-8f06-2c630c8f82a8.png)

Here, the exact pattern of "tree" is situated in six locations within the shortstory.txt file. 

---

# Using `-A` and `-B` to display context

To display a certain amount of lines before or after a result, we can use the `-A` and `-B` options. 

![image](https://user-images.githubusercontent.com/107522496/199538274-fa06cf8e-39a1-477e-b988-7727590e668f.png)

The above example displays all results matching the pattern "tree" and one line before them

---

In the below example, the `-A2` has een used to display the matching results and two lines after them too. 

![image](https://user-images.githubusercontent.com/107522496/199677962-7e8f5126-3b5f-49c4-9e7e-51c16b90aa37.png)
 
 ---
# Using the `-C` option with `grep`
 
`-A` is used to display a certain amount of numbers after a match and `-B` is used to display a certain amount if lines after a match. However, we can use the `-C`. This allows to display a certain amount of numbers before and after a match. So, instead of doing:

```yaml
$ grep "tree" shortstory.txt -A1 -B1
```
we can do the following: 

![image](https://user-images.githubusercontent.com/107522496/199680555-6f43bd2a-e1a9-44fd-a4d6-98cb9dd0d8b2.png)

This displays the the line the match is foud on and also one line before and after the match result.

---

#  Using the `-n` option with `grep` to display the line numbers 

The `-n`  display the line numbers.

![image](https://user-images.githubusercontent.com/107522496/199683449-9db67ddd-1d98-42d2-bca3-ec21ea85e12e.png)

The reason why 

```yaml
$ grep "tree" shortstory.txt -C2n
```
would not work is because the `-C` would try to interpret the n as a number hence why can either put the `-n` seperate or place it before the `-C`, as has been shown in the example above.

---

#  Using the `-m` option with `grep` to limit the amount of matches displayed to the terminal

The `-m` can be used to limit the amount of matches displayed to the terminal to a certain number. For example:

![image](https://user-images.githubusercontent.com/107522496/199684813-1e783c5d-27f3-446f-93e3-2e21c09f65d0.png)

will only display the first three results. 

--- 


#  Using the `-l` option with `grep` to display the line numbers 
