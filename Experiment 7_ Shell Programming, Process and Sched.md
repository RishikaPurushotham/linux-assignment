
Experiment 7: Shell Programming, Process and Scheduling
* * *
Name: Rishika Purushotham Roll No.: 590029145 Date: 2025-09-23
* * *
Aim:
- To write shell scripts that demonstrate process management.
- To understand how to schedule processes using cron and at .
- To monitor running processes and practice job control commands.
  
* * *
Requirements
A Linux machine with bash shell.
Access to process management commands ( ps ,top , kill , jobs , fg , bg ).
Access to scheduling utilities ( cron , at ).
* * *
Theory
Every program running in Linux is a process identified by a unique process ID (PID). Shell programming allows automation of tasks including spawning and controlling processes. Process management commands like ps , top , kill , jobs , bg , and fg let users monitor and control execution. Scheduling utilities such as cron (repeated tasks) and at (one-time tasks) allow tasks to run automatically at defined times. Combining scripting with scheduling is a core system administration skill.
* * *
Procedure & Observations
Exercise 1: Writing a basic shell script
Task Statement:
Create a shell script that prints the current date, time, and the list of logged-in users.
Command(s):
#!/bin/bash
echo "Current date and time: $(date)"
echo "Logged in users:"
w

Output:
<p align="center">
<img src="/img/exp7-1.jpg" width="900">
</p>
Exercise 2: Background and foreground processes
Task Statement:
Run a process in background and bring it to the foreground.
Command(s):
#!/bin/bash
sleep 60 &
jobs
fg %1

Output:
<p align="center">
<img src="/img/exp7-2.jpg" width="900">
</p>

Exercise 3: Killing a process
Task Statement:
Start a process and terminate it using kill .
Command(s):
sleep 300 &
ps aux | grep sleep
kill <pid>

Output:
<p align="center">
<img src="/img/exp7-13.jpg" width="900">
</p>

Exercise 4: Monitoring processes
Task Statement:
Use ps and top to monitor processes.
Command(s):
ps aux | head -5
top

Output:
<p align="center">
<img src="/img/exp7-4.jpg" width="900">
</p>

Exercise 5: Using cron for scheduling
Task Statement:
Schedule a script to run every day at 7:00 AM using cron .
Command(s):
crontab -e
0 7 * * * /home/retr0/myscript.sh

Output:

exp7_cron
Exercise 6: Using at for one-time scheduling
Task Statement:
Schedule a script to run once at a specified time using at .
Command(s):
echo "/home/user/myscript.sh" | at 08:30
atq
* * *
**Result**:

Learned to create and run shell scripts.
Managed processes using background, foreground, and kill commands.
Monitored processes with ps and top .
Scheduled recurring tasks with cron and one-time tasks with at .
* * *
**Challenges Faced & Learning Outcomes**

Challenge 1: Remembering the crontab time format. Solved by using online crontab generators
and practice.
Challenge 2: Ensuring atd service is running for at command. Fixed by starting the service with
systemctl start atd .
* * *
**Learning**:
Gained hands-on knowledge of process creation and termination.
Learned job control and scheduling using cron and at .
* * *
**Conclusion**

This experiment provided practical experience with shell scripting, process management, andscheduling. These are critical skills for system administrators to automate and control Linux environments effectively.
* * *