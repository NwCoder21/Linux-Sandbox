# Creating Nested Directories

![image](https://user-images.githubusercontent.com/107522496/196190161-fb71f490-64a2-476d-a141-1650658949a0.png)

The above one-line command creates a teachers directory within the Desktop directories and at the same time, also creates 3 folders within the teachers directory. 

---

Now lets say we want to create a documents folder for each teacher: 

![image](https://user-images.githubusercontent.com/107522496/196190952-8a03c109-0c85-448a-a692-7957a72d7121.png)

---

However, lets say we want to create a docs directory for a teacher, Helen, who does not exist, such as:

![image](https://user-images.githubusercontent.com/107522496/196191463-1474ecf5-c7db-4b16-bc64-d37809de8d28.png)

an error occues as the parent direcotry, in this case, the Helen folder does not exist. 

---
To address this issue, we can use the `-p` {parent} option with mkdir, which creates the parent directory too. For example:

![image](https://user-images.githubusercontent.com/107522496/196193119-864d0f27-659e-49d7-b2b8-d10e7db3965b.png)


`-p` allows to create nested folders. Can go several layers deep with `-p` 



