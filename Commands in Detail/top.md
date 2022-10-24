# top 

This command is used to display the current system usage

![image](https://user-images.githubusercontent.com/107522496/197503567-830f5a35-19e6-4605-b6b0-7c4c56c3d495.png)

> Note: when the top command is executed, the terminal will display a new window in order to output the information. To quit this window, type either `q` or `ctrl-c`.

---

![image](https://user-images.githubusercontent.com/107522496/197504690-5d5915b8-b60d-4eb4-820a-9d08c9012327.png)

When using `top`, there are two sections displayed;

* Summary dashboard (highlighted in red)2
* Process List (highlighted in yellow)

# Summary Dashboard in More Detail 

The first line includes:

* Time
* How long computer has been running 
* Number of people logged in 
* Load average for the past 1, 5, and 15 minutes 

Second line contains:

* Number of tasks and what state they are in:
  * Running 
  * Sleeping 
  * Stopped
  * Zombie 

The third line contains CPU values for:

* us: the amount of time the CPU spends executing processes for people in the "user space"
* sy: amount of time spent running "system kernel" space processes
* ni: amount of time spent executing processes with a manually set nice value 
* id: amount of CPU idle time
* wa:  amount of time the CPU spends waiting for I/O to complete 
* hi: amount of time spent servicing hardware interrupts
* si: amount of time spent servicing software interrupts
* st: amount of time lost due to running virtual machines 

The fourth line contains:

* Total amount of physical memory (displayed in mebibytes)
* how much of it is free
* how much of it is used
* how much of it is buffered/cached

The fifth line contains:

* Total amount of swap memory (displayed in mebibytes)
* how much of it is free
* how much of it is used
* how much of it is available

# Changing Numerical Units

To change and cycle through different numerical units for the Summary Dashboard, enter `E`.
To change and cycle through different numerical units for the Process List, enter `e`.

These are the different types units which can be displayed:

* kibibytes
* mebibytes
* gibibytes
* tebibytes
* pebibytes
* exbibytes

---


# Process List in More Detail 


```diff
-To Be Completed 
```






Part of the information I have taken has been from https://www.howtogeek.com/668986/how-to-use-the-linux-top-command-and-understand-its-output/ 

